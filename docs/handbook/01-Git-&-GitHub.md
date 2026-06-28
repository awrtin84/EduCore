# فصل ۱ - راهنمای Git و GitHub در پروژه EduCore

---

## مقدمه

در پروژه EduCore تمام اعضای تیم موظف هستند از یک Workflow یکسان استفاده کنند.

هدف از این قوانین این است که:

- تاریخچه پروژه همیشه مرتب باشد.
- هیچ تغییر مهمی گم نشود.
- بتوانیم به راحتی تغییرات هر Feature را پیگیری کنیم.
- توسعه پروژه برای تمام اعضای تیم قابل فهم باشد.

در این پروژه هیچ توسعه‌ای خارج از این فرآیند انجام نخواهد شد.

---

# آشنایی با Branchهای پروژه

در EduCore سه نوع Branch اصلی داریم.

---

## Main

Branch اصلی پروژه است.

این Branch همیشه باید پایدار باشد.

نسخه‌هایی که روی Main قرار می‌گیرند، آماده انتشار هستند.

### قوانین Main

- هیچ Commit مستقیمی روی Main انجام نمی‌شود.
- هیچ Push مستقیمی روی Main انجام نمی‌شود.
- Merge به Main فقط از طریق Pull Request انجام می‌شود.

به زبان ساده:

Main ویترین پروژه است.

---

## Develop

Develop محل تجمیع تمام Featureهای پروژه است.

تمام Featureها بعد از تکمیل شدن وارد این Branch می‌شوند.

### قوانین Develop

- هیچ توسعه مستقیمی روی Develop انجام نمی‌شود.
- هیچ Commit مستقیمی روی Develop انجام نمی‌شود.
- Develop فقط محل ادغام Featureها است.

---

## Feature Branch

هر قابلیت جدید پروژه باید Branch مخصوص خودش را داشته باشد.

برای مثال:

```
feature/authentication

feature/student-module

feature/backend-refactor

feature/dashboard

feature/course-management
```

هر Branch فقط مربوط به یک Feature است.

بعد از پایان آن Feature نیز حذف خواهد شد.

---

# ساختار کلی پروژه

Workflow کلی پروژه به شکل زیر است.

```
Issue

↓

Feature Branch

↓

Development

↓

Commit

↓

Push

↓

Pull Request

↓

Code Review

↓

Merge into Develop

↓

Delete Branch
```

این روند برای تمام Featureها یکسان است.

---

# شروع یک Feature جدید

فرض کنید قصد دارید سیستم ورود کاربران را پیاده‌سازی کنید.

مراحل کار به ترتیب زیر خواهد بود.

---

## مرحله اول

ابتدا وارد Branch Develop شوید.

```
git checkout develop
```

---

## مرحله دوم

آخرین تغییرات پروژه را دریافت کنید.

```
git pull origin develop
```

دلیل این کار:

ممکن است یکی دیگر از اعضای تیم تغییراتی را روی Develop قرار داده باشد.

همیشه قبل از شروع توسعه باید آخرین نسخه پروژه را دریافت کنید.

---

## مرحله سوم

Branch جدید بسازید.

```
git checkout -b feature/authentication
```

نکته مهم:

Branch جدید همیشه باید از روی Develop ساخته شود.

هرگز از روی Main Branch جدید ایجاد نکنید.

---

# شروع توسعه

اکنون روی Branch جدید قرار دارید.

تمام توسعه مربوط به Feature فقط روی همین Branch انجام می‌شود.

برای مشاهده Branch فعلی:

```
git branch
```

اگر خروجی به شکل زیر بود:

```
* feature/authentication
develop
main
```

یعنی روی Branch صحیح قرار دارید.

---

# ثبت تغییرات (Commit)

بعد از انجام بخشی از توسعه:

ابتدا فایل‌ها را آماده Commit کنید.

```
git add .
```

سپس Commit ایجاد کنید.

```
git commit -m "feat(auth): add login endpoint"
```

Commit باید معنی‌دار باشد.

از نوشتن Commitهایی مانند:

```
update

test

123

final

new
```

خودداری کنید.

---

# ارسال تغییرات به GitHub

بعد از Commit:

```
git push origin feature/authentication
```

اکنون تغییرات روی GitHub نیز قرار گرفته‌اند.

---

# ساخت Pull Request

پس از پایان توسعه:

در GitHub یک Pull Request ایجاد کنید.

مبدأ:

```
feature/authentication
```

مقصد:

```
develop
```

سپس منتظر بررسی و تأیید Pull Request بمانید.

---

# پایان Feature

بعد از Merge شدن Pull Request

Branch دیگر کاربردی ندارد.

ابتدا Branch محلی را حذف کنید.

```
git branch -d feature/authentication
```

سپس Branch موجود در GitHub را حذف کنید.

```
git push origin --delete feature/authentication
```

---

# تفاوت Branchهای Local و Remote

هنگام مشاهده Branchها ممکن است دو نوع Branch ببینید.

مثلاً:

```
develop
```

و

```
origin/develop
```

این دو یکسان نیستند.

---

## Local Branch

Branchهایی هستند که روی کامپیوتر شما قرار دارند.

برای مثال:

```
main

develop

feature/backend-refactor
```

تمام توسعه روی این Branchها انجام می‌شود.

---

## Remote Branch

Branchهایی هستند که روی GitHub قرار دارند.

برای مثال:

```
origin/main

origin/develop
```

وجود عبارت origin به معنی GitHub است.

بنابراین:

```
origin/develop
```

یعنی Branch Develop روی GitHub

و

```
develop
```

یعنی Branch Develop روی کامپیوتر شما.

شما همیشه روی Branchهای Local کار می‌کنید.

---

# تفاوت Fetch و Pull

گاهی اوقات اعضای دیگر تیم تغییراتی روی GitHub قرار می‌دهند.

برای دریافت اطلاعات جدید دو دستور وجود دارد.

---

## Fetch

```
git fetch
```

این دستور فقط اطلاعات جدید GitHub را دریافت می‌کند.

هیچ تغییری در فایل‌های پروژه ایجاد نمی‌کند.

---

## Pull

```
git pull origin develop
```

این دستور علاوه بر دریافت تغییرات، آن‌ها را وارد Branch فعلی نیز می‌کند.

به همین دلیل همیشه قبل از شروع کار:

ابتدا Pull انجام دهید.

---

# قوانین Commit

در پروژه EduCore از Conventional Commit استفاده می‌کنیم.

نمونه‌ها:

```
feat(auth): add JWT authentication

feat(student): implement CRUD endpoints

fix(course): resolve duplicate registration bug

refactor(database): simplify repository layer

docs: update handbook

test(auth): add login tests

chore: update dependencies
```

---

# قوانین مهم تیم

قبل از شروع هر Feature:

✅ روی Develop بروید.

✅ آخرین تغییرات را دریافت کنید.

✅ Branch جدید بسازید.

---

هنگام توسعه:

✅ فقط روی Feature Branch کار کنید.

✅ Commitهای معنی‌دار بنویسید.

---

بعد از پایان توسعه:

✅ Push انجام دهید.

✅ Pull Request بسازید.

✅ منتظر Review بمانید.

✅ بعد از Merge، Branch را حذف کنید.

---

# اشتباهات رایج

❌ Commit روی Main

❌ Commit روی Develop

❌ ساخت Branch از روی Main

❌ Push بدون Commit مناسب

❌ Commit با نام‌های نامفهوم

❌ انجام چند Feature مختلف در یک Branch

---

# Workflow روزانه اعضای تیم

هر روز قبل از شروع توسعه، این مراحل را انجام دهید.

1. وارد Branch Develop شوید.

```
git checkout develop
```

2. آخرین تغییرات پروژه را دریافت کنید.

```
git pull origin develop
```

3. Branch جدید بسازید.

```
git checkout -b feature/نام-feature
```

4. توسعه را آغاز کنید.

5. Commit بزنید.

6. تغییرات را Push کنید.

7. Pull Request بسازید.

8. بعد از تأیید، Branch را حذف کنید.

---

# جمع‌بندی

در پروژه EduCore هیچ توسعه‌ای مستقیماً روی Main یا Develop انجام نمی‌شود.

هر قابلیت جدید مسیر مشخصی را طی می‌کند:

Issue → Feature Branch → Commit → Push → Pull Request → Review → Merge → Delete Branch

رعایت این فرآیند باعث می‌شود پروژه همیشه منظم، قابل توسعه و قابل پیگیری باقی بماند.