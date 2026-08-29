---
title: "تولیدکننده پرامپت ویدیوی تِرن‌تیبل لباس CLO 3D (دو مرحله‌ای)"
description: "سیستم دو مرحله‌ای: یک LLM چندوجهی عکس‌های مرجع لباس طراحی‌شده در CLO 3D را عمیق آنالیز می‌کند و یک پرامپت تصویر-به-ویدیوی اختصاصی می‌نویسد که هویت طراحی را در رندر تِرن‌تیبل ۳۶۰ درجه ثابت نگه می‌دارد."
category: خلاقیت و طراحی
platforms: [google-gems, gemini, generic]
tags: [clo3d, طراحی-لباس, تصویر-به-ویدیو, ترنتیبل, ویدیو-360, تولید-پرامپت, لباس, مد-سه‌بعدی]
language: fa
use_case: "تبدیل رندرهای لباس CLO 3D به ویدیوی تِرن‌تیبل ۳۶۰ درجه با حفظ هویت طراحی، با مدل‌های تصویر-به-ویدیو"
version: 1.0.0
author: "nimabhk"
date: 2026
---

## System Prompt

> **نکته:** متن پرامپت عمداً به انگلیسی حفظ شده است، چون خروجی مرحله دوم (پرامپت ویدیو) باید انگلیسی باشد تا با مدل‌های تصویر-به-ویدیو بهترین نتیجه را بدهد.

````
Act as a master 3D technical fashion designer and an elite Image-to-Video prompt engineer. I am providing you with multiple reference images of a single 3D garment designed in CLO 3D from different angles.

Step 1: Deep Visual Audit
Analyze all provided images simultaneously. Break down every single visual and structural feature into an exhaustive technical inventory:

- Fabric & Materiality: Exact weave, glossiness, weight, opacity, texture depth (e.g., brushed matte leather, ribbed knit, 4-way stretch nylon), and surface normals.
- Construction & Tailoring: Exact silhouette, paneling, seam placements, topstitching patterns, darts, hems, cuffs, and collar structure.
- Hardware & Accents: Exact positions, colors, and materials of zippers, buttons, rivets, eyelets, cords, buckles, and patches.
- Form & Silhouette: How the garment drapes, natural folds, creases, and structural volume.

Step 2: Generate the Final Image-to-Video Prompt
Using the exhaustive inventory from Step 1, generate a single, highly dense, ready-to-use Image-to-Video prompt (in English) designed for a 360-degree turntable video render (9:16 vertical ratio).

Requirements for the final prompt:
- Explicitly list every specific feature identified in Step 1 so the video model is semantically anchored to the exact design.
- Enforce a static 3D turntable / smooth 360-degree camera orbit around the asset.
- Include strict negative constraints explicitly prohibiting any morphing or alterations to the specific features you listed.

Output ONLY the finalized prompt ready to copy-paste, followed by a matching Negative Prompt.
````

## نحوه کار (روند دو مرحله‌ای)

این یک **متاپرامپت** است: به‌جای اینکه مستقیم ویدیو توصیف کند، کاری می‌کند که LLM خودش پرامپت ویدیو را برای تو بسازد — بر اساس همان لباس واقعی.

**گام اول — آنالیز و تولید**

1. سیستم پرامپت بالا را در یک LLM چندوجهی پیست کن (تست‌شده با Gemini 3.7 Flash).
2. چند **عکس مرجع از همان یک لباس** را پیوست کن (مثلاً رندرهای زاویه جلو / بغل / پشت خروجی CLO 3D).
3. LLM تک‌تک اجزا را ممیزی می‌کند و سپس یک **پرامپت دوم اختصاصی** می‌نویسد: به‌جای عبارات کلی، تک‌تک اجزای همان لباس خاص را نام می‌برد (مثلاً: «کت چرم مشکی پِبل‌گرین کافه‌ریسر با زیپ اریب نقره‌ای وسط جلو، دوخت دوبل یقه، دو جیب سینه زیپ‌دار»).

**گام دوم — ساخت ویدیو**

4. پرامپت تولیدشده را **عیناً** کپی کن و **همراه با عکس اصلی لباس** به مدل تصویر-به-ویدیو بده.
5. نتیجه، یک ویدیوی تِرن‌تیبل ۳۶۰ درجهٔ یکپارچه است که هویت طراحی لباس را حفظ می‌کند.

## متغیرها

| متغیر | توضیح | پیش‌فرض |
|-------|-------|---------|
| `{{REFERENCE_IMAGES}}` | ۲ تا ۸ رندر از همان لباس از زوایای مختلف | جلو، بغل، پشت |
| `{{ASPECT_RATIO}}` | نسبت تصویر ویدیو در پرامپت نهایی | 9:16 عمودی |
| `{{CAMERA_MOVE}}` | حرکت دورینی که در پرامپت نهایی اجباری می‌شود | مدار گردشی ثابت ۳۶۰ درجه |

## نمونه: کت چرم مشکی کافه‌ریسر

اجرای واقعی این پرامپت روی یک کت کافه‌ریسر طراحی‌شده در CLO 3D (فایل‌ها در پوشه [`examples/leather-cafe-racer-jacket/`](examples/leather-cafe-racer-jacket/)).

> **سیستم پرامپتِ بالا محصول اصلی است** — عکس‌های مرجع، پرامپت تولیدشده و ویدیوی زیر همه فقط یک نمونه اجرای واقعی از آن هستند.

**ورودی — عکس‌های مرجع:**

| جلو | بغل | پشت |
|-----|-----|-----|
| ![جلو](examples/leather-cafe-racer-jacket/input-front-view.png) | ![بغل](examples/leather-cafe-racer-jacket/input-side-view.png) | ![پشت](examples/leather-cafe-racer-jacket/input-back-view.png) |

**خروجی — پرامپت دومِ تولیدشده** (متن کامل: [`generated-video-prompt.md`](examples/leather-cafe-racer-jacket/generated-video-prompt.md)): پرامپتی که جزئیات همان کت را قدم‌به‌قدم نام می‌برد — چرم سنگین پِبل‌گرین، یقه بند ماندارین با دکمه فشاری، زیپ فلزی نقره‌ای وسط جلو که بالا باز است، دو جیب سینه افقی زیپ‌دار، دو جیب وِلت عمودی پایین جلو، پانل‌های شانه منحنی، درز ستون فقرات وسط پشت، یراق کمر با دو دکمه اسنپ نقره‌ای، آستین‌های دوتکه با چین آرنجی — به‌همراه یک Negative Prompt کامل که مورف شدن درزها، محو شدن زیپ‌ها و جابه‌جایی جیب‌ها را صریحاً ممنوع می‌کند.

**ویدیوی نهایی** — تِرن‌تیبل ۳۶۰ درجهٔ یکپارچه با حفظ هویت طراحی (رندرشده با **Gemini Omni** از پرامپت دوم + عکس مرجع جلو):
[`examples/leather-cafe-racer-jacket/output-seamless-360-turntable.mp4`](examples/leather-cafe-racer-jacket/output-seamless-360-turntable.mp4)

## نکات و بهترین شیوه‌ها

- **همه زوایا را پوشش بده**: پرامپت دوم فقط می‌تواند ویژگی‌هایی را نام ببرد که در عکس‌های مرجع دیده می‌شوند. هر چیزی که هیچ دورینی ندیده (آستر داخلی، یراق پنهان) را مدل ویدیوساز از خودش می‌سازد.
- **پرامپت دوم را همیشه با عکس اصلی بده**: پرامپت مدل ویدیوساز را از نظر معنایی لنگر می‌کند و عکس آن را از نظر هندسی. استفاده از هر دو است که هویت لباس را در طول چرخش ثابت نگه می‌دارد.
- **Negative Prompt را حذف نکن**: این پرامپت دقیقاً بر اساس ویژگی‌های لیست‌شده در پرامپت اصلی تولید می‌شود (مثلاً «disappearing zippers» برای کت پر از زیپ). مهم‌ترین سپر در برابر به‌هم‌ریختن درزها و جابه‌جا شدن جیب‌ها در میانه چرخش است.
- **لباس ثابت، دورین متحرک**: پرامپت عمداً لباس را «از نظر هندسی قفل‌شده» نگه می‌دارد و فقط دورین را می‌چرخاند — اگر باد، راه رفتن یا شبیه‌سازی پارچه بخواهی، هویت طراحی خراب می‌شود.
- گام اول با مدل‌های چندوجهیِ قوی در ورودی چندعکسی (مثل Gemini) بهترین نتیجه را می‌دهد؛ گام دوم با هر مدل تصویر-به-ویدیویی که پرامپت + عکس شروع بپذیرد کار می‌کند (اعتبارسنجی‌شده با Gemini Omni).

## اعتبارها

- طراحی سه‌بعدی لباس و آثار مرجع: **AMEEN** — [پورتفولیو CLO-SET](https://connect.clo-set.com/portfolio/794161/collection/allitems)

## تاریخچه نسخه‌ها

- v1.0.0 — انتشار اولیه: روند دو مرحله‌ای (ممیزی تصویر → پرامپت اختصاصی تِرن‌تیبل)، اعتبارسنجی‌شده به‌صورت سرتاسری روی کت چرم کافه‌ریسر CLO 3D با خروجی تِرن‌تیبل ۳۶۰ درجه.
