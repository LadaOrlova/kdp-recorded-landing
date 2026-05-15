# SEO-аудит лендинга «Как делать продукт» в записи

**Дата:** 2026-05-07
**Файл:** `index.html`
**URL после деплоя:** `school.zamesin.ru/courses/ajtbd`

## Score Card

```
Overall Score: 58/100

On-Page SEO:     65/100  ██████░░░░  H1+H2 ок, нет «Advanced JTBD» в title
Content Quality: 88/100  █████████░  3069 слов, отличная структура, E-E-A-T
Technical:       30/100  ███░░░░░░░  Нет canonical, нет OG, нет Twitter
Schema:          0/100   ░░░░░░░░░░  Schema markup полностью отсутствует
Images:          70/100  ███████░░░  Alt+lazy есть, но 2.1 MB PNG критично большой
```

---

## Issues

### 🔴 Critical

1. **Schema markup отсутствует** (0 JSON-LD). Нужны: `Course`, `Organization`, `Person`, `Offer`. Без этого нет rich snippets в Google и Яндексе.
2. **Нет Open Graph и Twitter Card.** При расшаривании в TG/ВК/LinkedIn — нет картинки, нет описания.
3. **`ivan-zamesin.png` весит 2.1 MB.** PNG для фото — антипаттерн. Должен быть WebP/JPEG <200 KB. Критично для LCP.

### 🟠 High

4. **Title без «Advanced JTBD»** — главного ключевика. Сейчас: «Как делать продукт — курс Ивана Замесина в записи».
5. **Canonical URL отсутствует.** После деплоя обязателен `<link rel="canonical">`.
6. **Description 126 символов** — есть запас до 155-160 для ключевиков.
7. **Alt у фото слишком общий** — «Ваня Замесин». Должен описывать роль и контекст.

### 🟡 Medium

8. **H1 «Как делать продукт» — без ключевика.** Семантически расширить (визуально оставить как есть).
9. **Breadcrumbs отсутствуют** — нужен `BreadcrumbList` Schema.
10. **Дата публикации не указана.**

### 🟢 Low

11. Favicon отсутствует.
12. `<meta name="last-modified">` не задан.

---

## Schema-предложения (JSON-LD для копипасты в `<head>`)

### Course schema

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Как делать продукт — курс Advanced JTBD",
  "description": "Учим мыслить системно и строить продукты, которыми пользуются миллионы. Авторская методология Advanced JTBD от Вани Замесина.",
  "provider": {
    "@type": "Organization",
    "name": "Школа Вани Замесина",
    "url": "https://school.zamesin.ru"
  },
  "educationalLevel": "Professional",
  "inLanguage": "ru",
  "teaches": "Advanced JTBD, юнит-экономика, RAT-фреймворк, ABCDX-сегментация, продуктовая стратегия",
  "instructor": {
    "@type": "Person",
    "name": "Ваня Замесин",
    "description": "Автор методологии Advanced JTBD и фреймворка AURA. Эксперт #1 среди российских IT-продактов.",
    "sameAs": "https://t.me/zamesin"
  },
  "hasCourseInstance": [
    {
      "@type": "CourseInstance",
      "name": "Самостоятельный",
      "courseMode": "Online",
      "courseWorkload": "PT49H",
      "offers": {
        "@type": "Offer",
        "price": "69900",
        "priceCurrency": "RUB",
        "availability": "https://schema.org/InStock"
      }
    },
    {
      "@type": "CourseInstance",
      "name": "С практикой",
      "courseMode": "Online",
      "courseWorkload": "P7W",
      "offers": {
        "@type": "Offer",
        "price": "99900",
        "priceCurrency": "RUB",
        "availability": "https://schema.org/PreOrder"
      }
    }
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "9.2",
    "bestRating": "10",
    "ratingCount": "13000"
  }
}
</script>
```

### Organization schema

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "EducationalOrganization",
  "name": "Школа Вани Замесина",
  "url": "https://school.zamesin.ru",
  "founder": {
    "@type": "Person",
    "name": "Ваня Замесин"
  },
  "sameAs": [
    "https://t.me/zamesin",
    "https://zamesin.ru"
  ]
}
</script>
```

### BreadcrumbList schema

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Школа Вани Замесина", "item": "https://school.zamesin.ru" },
    { "@type": "ListItem", "position": 2, "name": "Курсы", "item": "https://school.zamesin.ru/courses" },
    { "@type": "ListItem", "position": 3, "name": "Как делать продукт" }
  ]
}
</script>
```

### Open Graph (для расшаривания в соцсетях)

```html
<meta property="og:title" content="Курс «Как делать продукт» Вани Замесина — Advanced JTBD в записи">
<meta property="og:description" content="Учим мыслить системно и строить продукты, которыми пользуются миллионы. 13 000+ выпускников, оценка 9,2/10.">
<meta property="og:image" content="https://school.zamesin.ru/courses/ajtbd/og-image.png">
<meta property="og:url" content="https://school.zamesin.ru/courses/ajtbd">
<meta property="og:type" content="website">
<meta property="og:locale" content="ru_RU">
<meta property="og:site_name" content="Школа Вани Замесина">

<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Курс «Как делать продукт» Вани Замесина — Advanced JTBD в записи">
<meta name="twitter:description" content="Учим мыслить системно и строить продукты, которыми пользуются миллионы.">
<meta name="twitter:image" content="https://school.zamesin.ru/courses/ajtbd/og-image.png">
```

### Canonical (после деплоя)

```html
<link rel="canonical" href="https://school.zamesin.ru/courses/ajtbd">
```

### Title + Description (расширенные)

```html
<title>Advanced JTBD: курс «Как делать продукт» от Вани Замесина в записи</title>
<meta name="description" content="Учим мыслить системно и строить продукты, которыми пользуются миллионы. Авторская методология Advanced JTBD: 8 модулей за 7 недель, 13 000+ выпускников, оценка 9,2/10.">
```

---

## Action items

| Приоритет | Что | Где сделать |
|---|---|---|
| 🔴 Critical | Сжать `ivan-zamesin.png` → WebP <200 KB | вне репо (Squoosh, ImageOptim) |
| 🔴 Critical | Добавить Course + Organization + Person Schema | `<head>` в index.html |
| 🔴 Critical | Добавить Open Graph + Twitter Card | `<head>` в index.html |
| 🟠 High | Создать `og-image.png` (1200×630) для расшаривания | дизайн |
| 🟠 High | Расширить title и description с Advanced JTBD | `<head>` |
| 🟠 High | Расширить alt у фото Вани | в index.html |
| 🟠 High | Canonical URL | после деплоя |
| 🟡 Medium | BreadcrumbList Schema | `<head>` |
| 🟡 Medium | Favicon | `<head>` |

---

## Что меняла в самом лендинге по итогам аудита

> Этот раздел заполняется по мере внесения правок. Дата → пункт.

(пусто — правки ещё не внесены)
