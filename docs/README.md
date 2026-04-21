# EventMaster Documentation Overview

Реалізація **Documentation as Code** для проєкту **EventMaster**.

## Призначення
Ця документація є частиною репозиторію та підтримує принцип **Single Source of Truth**. Усі ключові рішення щодо вимог, архітектури, тестування та інфраструктури описані в Markdown і версіонуються разом із кодом.

## Структура документації
- [System Specification Document](architecture/SSD.md)
- [System Design Document](architecture/SDD.md)
- [Infrastructure Specification Document](architecture/ISD.md)
- [Test Strategy](quality/test-strategy.md)
- [Traceability Matrix](quality/traceability-matrix.md)
- [Developer Onboarding](developer/onboarding.md)
- [Versioning Policy](versioning.md)

## Single Source of Truth
- **SSD** — єдине джерело істини для функціональних та нефункціональних вимог.
- **SDD** — єдине джерело істини для архітектурних рішень і структури компонентів.
- **ISD** — єдине джерело істини для середовищ, розгортання та інфраструктурних залежностей.
- **Test Strategy** та **Traceability Matrix** використовують посилання на ідентифікатори вимог із SSD.

## Правила оновлення
1. Будь-яка зміна функціоналу спочатку вноситься в **SSD**.
2. Якщо зміна впливає на компоненти або взаємодію модулів, оновлюється **SDD**.
3. Якщо зміна стосується середовища, CI/CD або БД — оновлюється **ISD**.
4. Після зміни вимоги перевіряється **Traceability Matrix**.
5. Документація змінюється в тій самій гілці та pull request, що і код.

## Навігація
- [Перейти до архітектури](architecture/SSD.md)
- [Перейти до тестування](quality/test-strategy.md)
- [Перейти до onboarding](developer/onboarding.md)
