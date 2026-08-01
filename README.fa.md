# اسکیل‌ها - مجموعه اسکیل‌های عامل هوش مصنوعی

مجموعه‌ای از **«اسکیل»های آماده** (دستورالعمل‌های تخصصی) که به هر عامل هوش مصنوعی یاد می‌دهد کارهای حرفه‌ای انجام دهد.

> **«اسکیل» چیست؟** مجموعه‌ای از دستورالعمل‌های تخصصی است که عامل هوش مصنوعی هنگام کمک به شما بارگذاری می‌کند تا دقیقاً بداند *چطور* کمک کند. به‌جای شروع از صفر، هوش مصنوعی از یک روند کاری حرفه‌ای و اثبات‌شده پیروی می‌کند. نیازی به نوشتن پرامپت نیست، همه‌چیز از قبل داخلش ساخته شده.

- **با هر عامل هوش مصنوعی کار می‌کند:** Hermes، Claude Code، Codex، Cursor، Goose، OpenCode، Zed و موارد دیگر.
- **مستقل از عامل:** همان اسکیل روی همه عامل‌ها اجرا می‌شود.
- **ترمینال ندارید؟ مشکلی نیست.** نسخه‌های پرامپت ساده «کپی و جای‌گذاری» (برای ChatGPT، Claude، Gemini) در [ریپازیتوری prompts](https://github.com/thatssoheil/prompts) موجود است.

---

## 📦 اسکیل‌های موجود در این مجموعه

پوشه [`skills/`](skills/) را ببینید. هر اسکیل یک روند کاری حرفه‌ای است که با یک دستور قابل نصب است. با گذشت زمان اسکیل‌های جدیدی اضافه می‌شوند، پس سر بزنید - این یک مجموعه در حال رشد است.

---

## 🚀 روش استفاده

### گزینه ۱: برای کاربران عادی (ساده‌ترین، بدون ترمینال)

کلاً نیازی به نصب نیست. از نسخه‌های «کپی و جای‌گذاری» استفاده کنید:
👉 [github.com/thatssoheil/prompts](https://github.com/thatssoheil/prompts)

کافیست متن را کپی کنید و داخل ChatGPT، Claude یا Gemini بچسبانید.

### گزینه ۲: برای توسعه‌دهندگان (نصب به‌صورت اسکیل عامل)

اسکیل‌ها مستقل از عامل هستند. اول ببینید چه چیزی موجود است، بعد موردنظرتان را نصب کنید:

```bash
# دیدن اسکیل‌های موجود در این ریپازیتوری
npx skills add thatssoheil/skills --list

# نصب یک اسکیل برای عامل خودتان (به‌جای <skill-name> یک نام واقعی از لیست بالا بگذارید)
npx skills add thatssoheil/skills --skill <skill-name> --agent hermes-agent -g -y
```

برای هر عامل دیگری هم همین‌طور کار می‌کند، فقط اسم `--agent` را عوض کنید:

```bash
# مثال‌ها
npx skills add thatssoheil/skills --skill <skill-name> --agent claude-code -g -y
npx skills add thatssoheil/skills --skill <skill-name> --agent codex -g -y
npx skills add thatssoheil/skills --skill <skill-name> --agent cursor -g -y
npx skills add thatssoheil/skills --skill <skill-name> --agent goose -g -y
npx skills add thatssoheil/skills --skill <skill-name> --agent opencode -g -y
npx skills add thatssoheil/skills --skill <skill-name> --agent zed -g -y
```

### نصب یک اسکیل برای همه عامل‌ها یکجا

```bash
npx skills add thatssoheil/skills --skill <skill-name> --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
```

**توضیح گزینه‌ها:**
- `-g` -> نصب سراسری (برای همه پروژه‌های شما روی این سیستم در دسترس است).
- `-y` -> ردشدن از پیام‌های تأیید.
- `--skill <name>` -> کدام اسکیل نصب شود (یا `*` برای همه).

### دیدن اسکیل بدون نصب

```bash
npx skills use thatssoheil/skills --skill <skill-name>
```

---

## 🗂 ساختار ریپازیتوری

```
skills/
├── skills/
│   └── <skill-name>/
│       └── SKILL.md          # اسکیل (دستورالعمل + راه‌اندازی)
├── skills.sh.json            # مانیفست گروه‌بندی skills.sh
├── package.json
└── README.md
```

مطابق استاندارد [skills.sh / Agent Skills](https://skills.sh): برای هر اسکیل یک پوشه زیر `skills/` که شامل `SKILL.md` است.

---

## 🌍 زبان‌ها

- [English](README.md)
- [فارسی](README.fa.md)

---

## 📄 مجوز

MIT
