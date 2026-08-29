# System Prompt Bcuket - A Prompt Vault

> A curated, categorized collection of system prompts for LLMs, Custom GPTs, Google Gems, Claude Projects, and AI Agents.

This repo contains **no code** - only well-structured `.md` files you can copy-paste as system instructions.

**🌐 Languages: English, Persian (Farsi) & More** | **[🇮🇷 مستندات فارسی](#persian-documentation)**

---

## Table of Contents

- [Purpose](#purpose)
- [Quick Start](#quick-start)
- [Folder Structure & Categories](#folder-structure--categories)
- [Category Descriptions](#category-descriptions)
- [Standard Format](#standard-format)
- [How to Use Prompts](#how-to-use-prompts)
- [Platform-Specific Tips](#platform-specific-tips)
- [Using the Template](#using-the-template)
- [Contributing](#contributing)
- [Multi-Language Support](#multi-language-support)
- [FAQ](#faq)
- [Persian Documentation](#persian-documentation)

## Purpose

🎯 **Share & Discover**: Practical, tested system prompts for real-world use cases

📁 **Organized by Topic**: 10 carefully designed categories for quick discovery

📝 **Standardized Format**: Consistent structure with YAML frontmatter, system prompt, variables, and examples

🌐 **Multi-Platform**: Compatible with OpenAI GPTs, Google Gems, Claude Projects, Perplexity, and any Agent Framework

🌍 **Multi-Language**: Prompts available in multiple languages (English, Persian, and more coming soon)

🤝 **Community-Driven**: Built by contributors for contributors

## Quick Start

1. **Browse Categories**: Navigate to `/prompts/` and choose your category
2. **Find Your Prompt**: Look for descriptive filenames (e.g., `seo-blog-writer.md`)
3. **Copy System Prompt**: Open the file and copy the "System Prompt" section
4. **Paste in Platform**: Paste into ChatGPT Custom Instructions, Google Gem, Claude Project, etc.
5. **Customize**: Adjust variables or examples as needed for your use case

**Example**: Need an SEO blog writer?
```bash
cd prompts/03-writing-content/
cat seo-blog-writer.md
# Copy the System Prompt section
```

## Folder Structure & Categories

```
prompt-vault/
├── prompts/
│   ├── 01-core-roles/          # Base roles and fundamental personas
│   │   ├── critical-thinker.md
│   │   └── persian-critical-thinker.fa.md
│   ├── 02-coding-dev/          # Programming, debugging, code review
│   │   └── senior-code-reviewer.md
│   ├── 03-writing-content/     # Writing, editing, SEO content creation
│   │   ├── seo-blog-writer.md
│   │   └── persian-seo-blog-writer.fa.md
│   ├── 04-business-marketing/  # Business strategy, marketing, sales
│   ├── 05-education-tutor/     # Education, tutoring, learning assistance
│   ├── 06-productivity-life/   # Productivity, life hacks, planning
│   ├── 07-creative-design/     # Creativity, design thinking, art
│   │   ├── garment-turntable-video-prompt-generator.md
│   │   └── examples/leather-cafe-racer-jacket/  # Input images, generated prompt, output video
│   ├── 08-agents-automation/   # AI agents, automation workflows
│   │   ├── autonomous-research-agent.md
│   │   └── huggingface-model-extractor.md
│   ├── 09-platforms/           # Platform-specific (GPTs, Gems, etc.)
│   │   ├── google-gems/
│   │   │   ├── english-tutor-gem.md
│   │   │   └── english-tutor-gem.fa.md
│   │   ├── openai-gpts/
│   │   │   └── startup-validator-gpt.md
│   │   └── rtl-ltr-qa-stress-test.md
│   └── 10-translation-localization/  # Translation, localization, cultural adaptation
│       ├── persian-lyrics-diacritics-gem.md
│       ├── persian-lyrics-diacritics-gem.fa.md
│       └── tarane-irani.md  # knowledge base for the lyrics gem
├── templates/
│   ├── prompt-template.md      # English template
│   └── prompt-template.fa.md   # Persian template
├── README.md                   # This file (English + Persian)
├── CONTRIBUTING.md             # Contribution guide (English)
└── CONTRIBUTING.fa.md          # Contribution guide (Persian)
```

## Category Descriptions

| # | Category | Purpose | Example Prompts | When to Use |
|---|----------|---------|-----------------|-------------|
| **01** | Core Roles | Fundamental personas and base roles | Critical Thinker, Problem Solver, Analyst | When you need a general thinking framework |
| **02** | Coding & Dev | Programming, debugging, code review | Code Reviewer, Debug Assistant, Architecture Advisor | For software development tasks |
| **03** | Writing & Content | Content creation, editing, SEO | Blog Writer, Copywriter, Editor | For writing articles, posts, marketing copy |
| **04** | Business & Marketing | Strategy, marketing, sales, growth | Marketing Strategist, Sales Coach, Business Plan | For business planning and marketing |
| **05** | Education & Tutor | Teaching, tutoring, learning | Math Tutor, Language Teacher, Study Guide | For educational purposes and learning |
| **06** | Productivity & Life | Time management, planning, life hacks | Productivity Coach, Life Planner, Habit Builder | For personal organization and improvement |
| **07** | Creative & Design | Creativity, design thinking, art | Creative Director, Designer, Storyteller | For creative projects and design work |
| **08** | Agents & Automation | AI agents, workflows, automation | Research Agent, Auto-Researcher, Workflow Bot | For building autonomous agents |
| **09** | Platforms | Platform-specific customizations | GPTs, Gems, Claude Projects, Perplexity | When targeting specific platforms |
| **10** | Translation & Localization | Translation, cultural adaptation | Translator, Localizer, Cultural Advisor | For multilingual and cross-cultural tasks |

## Standard Format

Every prompt file follows this standardized structure:

### 1. YAML Frontmatter (Metadata)
```yaml
---
title: Prompt Title
description: One-line description
category: Category Name
platforms: [Platform1, Platform2]
tags: [tag1, tag2, tag3]
version: 1.0.0
author: "Nima Behkar"
date: 2024
---
```

### 2. System Prompt Section
The main instruction block that defines the AI's role, behavior, and task.

### 3. Variables (Optional)
Customizable parameters users can adjust:
```markdown
| Variable | Description | Default |
|----------|-------------|---------|
| `tone` | Communication style | professional |
```

### 4. Example Usage
Real-world examples of how to invoke the prompt.

### 5. Notes & Best Practices
Tips for optimal results and common pitfalls to avoid.

### 6. Version History
Track changes and improvements over time.

## How to Use Prompts

### Step 1: Choose Your Category
Browse the `/prompts/` folder and select the category matching your need.

### Step 2: Select a Prompt
Look at filenames to find the right prompt. Read the description in YAML frontmatter.

### Step 3: Open and Review
Open the `.md` file and read through:
- System Prompt (main instruction)
- Variables (customizable parts)
- Examples (usage patterns)

### Step 4: Copy System Prompt
Select and copy the entire "System Prompt" section.

### Step 5: Paste in Your Platform

**ChatGPT Custom Instructions**:
1. Go to Settings → Custom Instructions
2. Paste in "What would you like ChatGPT to know about you?"
3. Save

**Google Gems**:
1. Go to gems.google.com
2. Create new Gem or edit existing
3. Paste in "Instructions" field
4. Save

**Claude Projects**:
1. Create a new Project
2. Add custom instructions
3. Paste the system prompt

**Perplexity**:
1. Go to Library → Collections
2. Create new collection with prompt as description

**AI Agents/Automation**:
1. Integrate into your agent framework
2. Use as system message in API calls

### Step 6: Customize (Optional)
Adjust variables or add context specific to your use case.

## Platform-Specific Tips

| Platform | Best For | Tips |
|----------|----------|------|
| **ChatGPT (Custom Instructions)** | Personal assistant, daily tasks | Keep under 1500 characters for best results |
| **Google Gems** | Specialized tasks, recurring workflows | Use variables for dynamic behavior |
| **OpenAI Custom GPTs** | Public sharing, advanced features | Include conversation starters |
| **Claude Projects** | Long-context tasks, document analysis | Leverage Claude's large context window |
| **Perplexity** | Research, fact-based queries | Focus on search and citation behavior |
| **AI Agents** | Automation, workflows | Structure for programmatic access |
| **API Integration** | Production apps | Use system message role |

## Using the Template

We provide a blank template to help you create new prompts in the correct format.

### Location
- English: `templates/prompt-template.md`
- Persian: `templates/prompt-template.fa.md`

### Step-by-Step Guide

#### Step 1: Copy the Template
```bash
cp templates/prompt-template.md prompts/02-coding-dev/your-prompt-name.md
```

#### Step 2: Fill YAML Frontmatter
Update all metadata fields:
- `title`: Clear, descriptive title
- `description`: One-sentence summary
- `category`: Match folder name
- `platforms`: List compatible platforms
- `tags`: 5-10 relevant keywords
- `version`: Start with 1.0.0
- `author`: Your name (e.g., "Nima Behkar") or GitHub handle (e.g., "nimabhk")
- `date`: Current year

#### Step 3: Write System Prompt
Best practices:
- Start with "Act as..." or "You are..."
- Be specific about tasks and behaviors
- Include do's and don'ts
- Specify output format if needed
- Keep it concise but comprehensive (300-800 words ideal)

#### Step 4: Define Variables (Optional)
Create a table of customizable parameters:
```markdown
| Variable | Description | Default Value |
|----------|-------------|---------------|
| `tone` | Communication style | professional |
| `length` | Output length | medium |
```

#### Step 5: Add Example Usage
Provide 2-3 real examples:
```markdown
## Basic Usage
[Simple example]

## Advanced Usage
[With customization]

## Edge Cases
[Special scenarios]
```

#### Step 6: Add Notes & Version History
- Tips for best results
- Known limitations
- Version changelog

### Template Checklist

Before submitting your prompt:
- [ ] YAML frontmatter complete
- [ ] System prompt clear and actionable
- [ ] No typos or grammatical errors
- [ ] Variables defined (if applicable)
- [ ] At least 2 usage examples
- [ ] Version history included
- [ ] Filename follows convention (`descriptive-name.md`)
- [ ] Placed in correct category folder

## Contributing

We welcome contributions! Here's how to participate:

### Contribution Process

1. **Fork the Repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/prompt-vault.git
   cd prompt-vault
   ```

2. **Create a New Branch**
   ```bash
   git checkout -b feature/add-my-prompt
   ```

3. **Create Your Prompt**
   - Copy the template: `cp templates/prompt-template.md prompts/CATEGORY/your-prompt.md`
   - Follow the format guidelines above
   - Test your prompt with at least 2 different LLMs

4. **Commit Your Changes**
   ```bash
   git add prompts/CATEGORY/your-prompt.md
   git commit -m "Add: [Prompt Name] for [Use Case]"
   ```

5. **Push and Create Pull Request**
   ```bash
   git push origin feature/add-my-prompt
   ```
   Then open a PR on GitHub with:
   - Clear title
   - Description of what the prompt does
   - Example use cases
   - Testing notes

6. **Review Process**
   - Review will be completed within 1 week
   - Feedback will be provided if changes needed
   - Once approved, your prompt will be merged!

### Quality Standards

**✅ DO:**
- Write clear, actionable prompts
- Test before submitting
- Follow the standard format
- Use descriptive filenames
- Include examples
- Proofread for errors

**❌ DON'T:**
- Submit untested prompts
- Use vague or generic language
- Skip the template format
- Duplicate existing prompts
- Include harmful or biased content

### File Naming Convention

**Good**: `seo-blog-writer.md`, `code-reviewer.md`, `math-tutor.md`  
**Bad**: `prompt1.md`, `my-prompt.md`, `NEW.md`

For non-English versions, add language code before `.md`:
- Persian: `seo-blog-writer.fa.md`
- Spanish: `seo-blog-writer.es.md`
- French: `seo-blog-writer.fr.md`
- Arabic: `seo-blog-writer.ar.md`
- German: `seo-blog-writer.de.md`
- Chinese: `seo-blog-writer.zh.md`
- **Any language**: `prompt-name.[lang-code].md`

You can create prompts in **any language** - just use the appropriate ISO 639-1 language code!

---

## Multi-Language Support

This repository supports system prompts in **any language**! We encourage contributors to share prompts in their native languages.

### Language Code Convention

When creating a prompt in a language other than English:
1. Create the English version first (if possible): `prompt-name.md`
2. Create translated version with language code: `prompt-name.[code].md`

**Supported Language Codes:**
- `.fa.md` - Persian/Farsi
- `.es.md` - Spanish
- `.fr.md` - French
- `.de.md` - German
- `.ar.md` - Arabic
- `.zh.md` - Chinese
- `.ja.md` - Japanese
- `.ru.md` - Russian
- And any other ISO 639-1 language code

### Example Structure

```
prompts/01-core-roles/
├── critical-thinker.md          # English (default)
├── critical-thinker.fa.md       # Persian
├── critical-thinker.es.md       # Spanish
└── critical-thinker.ar.md       # Arabic
```

### Contributing Translations

You can contribute by:
1. **Translating existing prompts** to your native language
2. **Creating original prompts** in your language
3. **Improving translations** submitted by others

All prompts should follow the same structure regardless of language:
- YAML frontmatter (can include `language: fa` field)
- System Prompt section
- Variables (if applicable)
- Example Usage
- Notes & Version History

---

## FAQ

**Q: Can I submit prompts in languages other than English?**  
A: Yes! We welcome prompts in **any language**. Use the language code convention (e.g., `.fa.md` for Persian, `.es.md` for Spanish, `.fr.md` for French, etc.). See [Multi-Language Support](#multi-language-support) section.

**Q: Do I need to be an expert in prompt engineering?**  
A: No! If you have a prompt that works well for you, share it. The community will help improve it.

**Q: Can I update my prompt after submission?**  
A: Yes! Update the version number in YAML frontmatter and describe changes in Version History.

**Q: How do I request a prompt for a specific use case?**  
A: Open an Issue with the "Request" label describing what you need.

**Q: Are commercial prompts allowed?**  
A: Prompts should be free to use. You can mention your services in author field, but the prompt itself must be free.

**Q: What if someone copies my prompt elsewhere?**  
A: This is an open-source community project. Prompts are meant to be shared and used freely.

---

## Persian Documentation

📚 **برای مستندات کامل فارسی، به بخش‌های زیر مراجعه کنید:**

- **[CONTRIBUTING.fa.md](CONTRIBUTING.fa.md)** - راهنمای کامل مشارکت به فارسی
- **[templates/prompt-template.fa.md](templates/prompt-template.fa.md)** - تمپلیت فارسی برای ایجاد پرامپت جدید

### دسته‌بندی‌ها به فارسی

| شماره | دسته‌بندی | کاربرد | مثال |
|-------|-----------|--------|------|
| ۰۱ | نقش‌های پایه | شخصیت‌های اساسی | متفکر نقاد، حل‌کننده مسئله |
| ۰۲ | کدنویسی و توسعه | برنامه‌نویسی، دیباگ | ریویو کننده کد، دستیار دیباگ |
| ۰۳ | نویسندگی و محتوا | تولید محتوا، سئو | نویسنده وبلاگ، کپی‌رایتر |
| ۰۴ | بیزنس و مارکتینگ | استراتژی، فروش | استراتژیست مارکتینگ، کوچ فروش |
| ۰۵ | آموزش و تدریس | تدریس، یادگیری | معلم ریاضی، معلم زبان |
| ۰۶ | بهره‌وری و زندگی | مدیریت زمان، برنامه‌ریزی | کوچ بهره‌وری، برنامه‌ریز زندگی |
| ۰۷ | خلاقیت و طراحی | خلاقیت، دیزاین | مدیر خلاقیت، طراح، داستان‌سرا |
| ۰۸ | ایجنت‌ها و اتوماسیون | ایجنت‌های هوش مصنوعی | ایجنت تحقیق، اتوماسیون |
| ۰۹ | پلتفرم‌ها | مخصوص پلتفرم‌ها | GPTها، Gems، پروژه‌های Claude |
| ۱۰ | ترجمه و بومی‌سازی | ترجمه، تطبیق فرهنگی | مترجم، بومی‌ساز |

### شروع سریع (فارسی)

۱. **مرور دسته‌بندی‌ها**: به پوشه `/prompts/` بروید و دسته‌بندی مورد نظر را انتخاب کنید
۲. **انتخاب پرامپت**: فایل مناسب را پیدا کنید (مثلاً `seo-blog-writer.md`)
۳. **کپی سیستم پرامپت**: بخش "System Prompt" را کپی کنید
۴. **استفاده در پلتفرم**: در ChatGPT، Google Gems، Claude یا هر پلتفرم دیگری استفاده کنید
۵. **شخصی‌سازی**: متغیرها را بر اساس نیاز خود تنظیم کنید

### نحوه مشارکت (خلاصه)

۱. ریپازیتوری را فورک کنید
۲. برنچ جدید بسازید
۳. پرامپت خود را ایجاد کنید (از تمپلیت استفاده کنید)
۴. تست کنید (حداقل با ۲ مدل مختلف)
۵. کامیت و پوش کنید
۶. Pull Request باز کنید

📖 **برای راهنمای کامل مشارکت، فایل [CONTRIBUTING.fa.md](CONTRIBUTING.fa.md) را مطالعه کنید.**

### پشتیبانی از زبان‌های مختلف

این مخزن از پرامپت‌ها به **هر زبانی** پشتیبانی می‌کند! شما می‌توانید:
- پرامپت‌های موجود را به زبان مادری خود ترجمه کنید
- پرامپت‌های اصلی به زبان خودتان ایجاد کنید
- از کد زبان در نام فایل استفاده کنید (مثلاً `.fa.md` برای فارسی، `.es.md` برای اسپانیایی)

برای اطلاعات بیشتر، بخش [Multi-Language Support](#multi-language-support) را ببینید.

### سوالات متداول فارسی

**سوال**: آیا می‌توانم پرامپت به زبان‌های دیگر غیر از فارسی ارسال کنم؟  
**جواب**: بله! ما از پرامپت‌ها به هر زبانی استقبال می‌کنیم. فقط از کد زبان در نام فایل استفاده کنید.

**سوال**: آیا باید متخصص باشم؟  
**جواب**: خیر! اگر پرامپتی دارید که برایتان کار می‌کند، به اشتراک بگذارید.

**سوال**: چگونه می‌توانم پرامپت خاصی درخواست دهم؟  
**جواب**: یک Issue با لیبل "Request" باز کنید.

---

Made with ❤️ by **Nima Behkar** ([@nimabhk](https://github.com/nimabhk)) for the prompt engineering community

**Author**: Nima Behkar  
**Contributors**: [See all contributors](https://github.com/nimabhk/prompt-vault/graphs/contributors)  
**License**: MIT License  
**Version**: 1.0.0
