# 🧠 اسکیل‌ها — اسکیل‌های عامل هوش مصنوعی

مجموعه‌ای از **«اسکیل»های آماده** (دستورالعمل‌های تخصصی) که به هر عامل هوش مصنوعی یاد می‌دهد کارهای حرفه‌ای انجام دهد — **تحلیل سرمایه‌گذاری ارز دیجیتال** و **مربیگری تناسب اندام با هوش مصنوعی**.

> **«اسکیل» چیست؟** مجموعه‌ای از دستورالعمل‌های تخصصی است که عامل هوش مصنوعی هنگام کمک به شما بارگذاری می‌کند تا دقیقاً بداند *چطور* کمک کند. به‌جای شروع از صفر، هوش مصنوعی از یک روند کاری حرفه‌ای و اثبات‌شده پیروی می‌کند. نیازی به نوشتن پرامپت نیست — همه‌چیز از قبل داخلش ساخته شده.

- **با هر عامل هوش مصنوعی کار می‌کند:** Hermes، Claude Code، Codex، Cursor، Goose، OpenCode، Zed و موارد دیگر.
- **مستقل از عامل:** همان اسکیل روی همه عامل‌ها اجرا می‌شود.
- **ترمینال ندارید؟ مشکلی نیست.** نسخه‌های پرامپت ساده «کپی و جای‌گذاری» (برای ChatGPT، Claude، Gemini) در [ریپازیتوری prompts](https://github.com/thatssoheil/prompts) موجود است.

---

## 📦 چه چیزهایی داخلش هست

| اسکیل | چه کاری انجام می‌دهد |
|---|---|
| **crypto-investment-analysis** | تحلیل حرفه‌ای ۴‌لایه ارز دیجیتال — بنیادی، آن‌چین، تکنیکال و کلان — هم برای معامله کوتاه‌مدت و هم برای نگهداری بلندمدت. |
| **fitness-program** | روند کاری کامل مربیگری تناسب اندام — مصاحبه اولیه، تحلیل بدن از روی عکس، برنامه تمرینی اختصاصی، چک‌این هفتگی. چندزبانه. |

---

## 🚀 روش نصب

### گزینه ۱: برای کاربران عادی (ساده‌ترین — بدون ترمینال)

کلاً نیازی به نصب نیست. از نسخه‌های «کپی و جای‌گذاری» استفاده کنید:
👉 [github.com/thatssoheil/prompts](https://github.com/thatssoheil/prompts)

کافیست متن را کپی کنید و داخل ChatGPT، Claude یا Gemini بچسبانید.

### گزینه ۲: برای توسعه‌دهندگان (نصب به‌صورت اسکیل عامل)

اسکیل‌ها مستقل از عامل هستند. اسکیل موردنظرتان را برای عامل خودتان نصب کنید:

```bash
# Hermes Agent
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent hermes-agent -g -y
npx skills add thatssoheil/skills --skill fitness-program --agent hermes-agent -g -y
```

برای هر عامل دیگری هم همین‌طور کار می‌کند — فقط اسم `--agent` را عوض کنید:

```bash
# Claude Code
npx skills add thatssoheil/skills --skill fitness-program --agent claude-code -g -y

# OpenAI Codex
npx skills add thatssoheil/skills --skill fitness-program --agent codex -g -y

# Cursor
npx skills add thatssoheil/skills --skill fitness-program --agent cursor -g -y

# Goose
npx skills add thatssoheil/skills --skill fitness-program --agent goose -g -y

# OpenCode
npx skills add thatssoheil/skills --skill fitness-program --agent opencode -g -y

# Zed
npx skills add thatssoheil/skills --skill fitness-program --agent zed -g -y
```

### نصب یک اسکیل برای همه عامل‌ها یکجا

```bash
npx skills add thatssoheil/skills --skill crypto-investment-analysis --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
npx skills add thatssoheil/skills --skill fitness-program --agent hermes-agent claude-code codex cursor goose opencode zed -g -y
```

**توضیح گزینه‌ها:**
- `-g` → نصب سراسری (برای همه پروژه‌های شما روی این سیستم در دسترس است).
- `-y` → ردشدن از پیام‌های تأیید.
- `--skill <name>` → کدام اسکیل نصب شود (یا `*` برای همه).

### دیدن اسکیل بدون نصب

```bash
# چاپ دستورالعمل‌های اسکیل روی صفحه
npx skills use thatssoheil/skills --skill fitness-program
```

---

## 🗂 ساختار ریپازیتوری

```
skills/
├── skills/
│   ├── crypto-investment-analysis/
│   │   └── SKILL.md          # اسکیل (دستورالعمل + راه‌اندازی)
│   └── fitness-program/
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
