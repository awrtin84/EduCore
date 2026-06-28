# 📚 راهنمای کار با Git و GitHub در پروژه EduCore

اگر به تازگی به تیم EduCore اضافه شده‌ای، قبل از شروع توسعه حتماً این فایل را مطالعه کن.

هدف ما این است که همه اعضای تیم با یک روش یکسان روی پروژه کار کنند تا تاریخچه پروژه مرتب، قابل فهم و بدون مشکل باشد.

---

# ساختار Branchهای پروژه

در این پروژه سه نوع Branch داریم.

## 1- main

این Branch نسخه پایدار پروژه است.

قوانین:

- هیچ‌کس حق Commit مستقیم روی main را ندارد.
- هیچ‌کس حق Push مستقیم روی main را ندارد.
- فقط نسخه‌های پایدار وارد main می‌شوند.

---

## 2- develop

این Branch محل تجمیع Featureها است.

قوانین:

- هیچ‌کس مستقیماً روی develop کدنویسی نمی‌کند.
- Featureها بعد از تکمیل شدن وارد develop می‌شوند.
- develop همیشه آخرین نسخه توسعه پروژه است.

---

## 3- Feature Branch

هر قابلیت جدید باید Branch مخصوص خودش را داشته باشد.

مثال:

feature/authentication

feature/student-module

feature/backend-refactor

feature/dashboard

feature/course-management

---

# Workflow پروژه

تمام توسعه پروژه فقط به این صورت انجام می‌شود.

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

Review

↓

Merge into develop

↓

Delete Branch

---

# قبل از شروع هر Feature

ابتدا مطمئن شوید روی Branch develop قرار دارید.

سپس آخرین تغییرات پروژه را دریافت کنید.

```bash
git checkout develop
git pull origin develop
```

بعد Branch جدید را از روی develop بسازید.

```bash
git checkout -b feature/backend-refactor
```

یا

```bash
git checkout -b feature/student-module
```

دقت کنید:

همیشه Branch جدید باید از روی develop ساخته شود.

---

# شروع توسعه

بعد از ساخت Branch

کدنویسی را شروع کنید.

تمام Commitها روی همان Feature Branch انجام می‌شود.

هرگز روی main یا develop Commit نزنید.

---

# مشاهده Branch فعلی

برای مشاهده Branch فعلی:

```bash
git branch
```

Branch فعلی با علامت *

مشخص می‌شود.

مثال:

```
* feature/backend-refactor
develop
main
```

---

# مشاهده تمام Branchها

```bash
git branch -a
```

این دستور هم Branchهای Local و هم Branchهای Remote را نمایش می‌دهد.

---

# فرق Local و Remote

Local Branch

Branchهایی هستند که روی کامپیوتر شما قرار دارند.

مثال:

```
main
develop
feature/backend-refactor
```

---

Remote Branch

Branchهایی هستند که روی GitHub قرار دارند.

مثال:

```
origin/main
origin/develop
```

دقت کنید:

origin/develop

یعنی Branch develop روی GitHub

و

develop

یعنی Branch develop روی کامپیوتر شما.

همیشه روی Branchهای Local کار می‌کنیم.

---

# دریافت تغییرات جدید پروژه

قبل از شروع کار همیشه:

```bash
git fetch
```

سپس:

```bash
git pull origin develop
```

تا آخرین تغییرات تیم را دریافت کنید.

---

# ثبت تغییرات

بعد از پایان بخشی از کار:

```bash
git add .
```

سپس:

```bash
git commit -m "feat(auth): add login endpoint"
```

سپس:

```bash
git push origin feature/backend-refactor
```

---

# ساخت Pull Request

بعد از Push

وارد GitHub شوید.

از Branch خود

به

develop

Pull Request بسازید.

هر Feature فقط یک Pull Request دارد.

---

# حذف Branch بعد از Merge

بعد از اینکه Pull Request تایید شد و Merge انجام شد

Branch دیگر نیازی نیست.

حذف Branch Local

```bash
git branch -d feature/backend-refactor
```

حذف Branch Remote

```bash
git push origin --delete feature/backend-refactor
```

---

# ساخت Branch جدید

همیشه ابتدا:

```bash
git checkout develop
```

سپس:

```bash
git pull origin develop
```

بعد:

```bash
git checkout -b feature/new-feature
```

هرگز از روی main Branch جدید نسازید.

---

# قوانین Commit

از Conventional Commit استفاده می‌کنیم.

نمونه‌ها:

```text
feat(auth): add JWT authentication

feat(student): implement CRUD

fix(course): resolve duplicate registration

refactor(database): simplify repository layer

docs: update contributing guide

test(auth): add login tests

chore: update dependencies
```

---

# قوانین مهم پروژه

✅ هر Feature یک Issue دارد.

✅ هر Issue یک Branch دارد.

✅ هر Branch یک Pull Request دارد.

✅ هیچ Commit مستقیمی روی main انجام نمی‌شود.

✅ هیچ Commit مستقیمی روی develop انجام نمی‌شود.

✅ همیشه قبل از شروع کار git pull انجام دهید.

✅ همیشه بعد از پایان کار Pull Request بسازید.

✅ بعد از Merge شدن Branch را حذف کنید.

---

# اشتباهات رایج

❌ کار کردن روی main

❌ Commit روی develop

❌ ساخت Branch از روی main

❌ Push بدون Commit مناسب

❌ Commitهای بی‌معنی مثل

```
update

test

123

final

new
```

---

# نامگذاری Branchها

Feature

```
feature/authentication

feature/backend-refactor

feature/dashboard
```

Bug

```
fix/login

fix/student-registration
```

Documentation

```
docs/readme

docs/api-guidelines
```

Refactor

```
refactor/database

refactor/router
```

Test

```
test/authentication
```

---

# نامگذاری Commitها

Feature

```
feat(auth): add JWT login
```

Bug

```
fix(course): prevent duplicate registration
```

Refactor

```
refactor(api): split routers
```

Documentation

```
docs: update architecture
```

Testing

```
test(auth): add unit tests
```

Chore

```
chore: update dependencies
```

---

# خلاصه Workflow

شروع روز

↓

git checkout develop

↓

git pull origin develop

↓

ساخت Branch جدید

↓

کدنویسی

↓

Commit

↓

Push

↓

Pull Request

↓

Review

↓

Merge به develop

↓

حذف Branch

↓

شروع Feature بعدی

---

هدف ما فقط نوشتن کد نیست.

هدف ما ساختن یک محصول حرفه‌ای با استانداردهای واقعی توسعه نرم‌افزار است.