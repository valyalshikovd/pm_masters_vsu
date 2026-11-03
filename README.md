# Проектный менеджмент

Командный учебный репозиторий: выбор концепции, распределение учебных работ, оценка и планирование программного продукта.

## Команда

| Код | Участник | GitHub |
|---|---|---|
| E1 | Шестопалов Н. М. | [@Shest0pal0v](https://github.com/Shest0pal0v) |
| E2 | Михайлов Н. П. | [@nikhaylov](https://github.com/nikhaylov) |
| E3 | Валяльщиков Д. А. | [@valyalshikovd](https://github.com/valyalshikovd) |
| E4 | Мирошников А. С. | [@Arleqquinn](https://github.com/Arleqquinn) |

[План закрытия открытых работ](PLAN.md) · [Трекер фазы 1](https://github.com/users/valyalshikovd/projects/1)

## Фазы

| Фаза | Материалы | Статус |
|---|---|---|
| 1. Выбор концепции | [Фаза 1](phases/phase-01-concept-selection/README.md) | Выполнена: TOPSIS, производный МАИ и сравнение |
| 2. Распределение работы | [Фаза 2](phases/phase-02-work-distribution/README.md) | Не начата; заготовка |
| 3. Оценка проекта | [Фаза 3](phases/phase-03-project-estimation/README.md) | Не начата; заготовка |
| 4. Прогнозирование | [Фаза 4](phases/phase-04-forecasting/README.md) | Не начата; заготовка |
| 5. Планирование | [Фаза 5](phases/phase-05-planning/README.md) | Не начата; заготовка |

Расчёты обоих методов готовы. [МАИ и сопоставление](phases/phase-01-concept-selection/ahp.md) основаны на производных сравнениях центральных оценок. Для текущей версии приняты расчётная анкета E3 и описанное правило преобразования; выбор A1 проверен анализом чувствительности.

## Концепции

| Код | Концепция | Краткое описание |
|---|---|---|
| A1 | Запись на приём к врачу | Система для организации записи на врачебный приём. |
| A2 | Учёт вещей на хранении | Система учёта вещей, переданных на хранение. |
| A3 | Учёт обслуживания автомобиля | Система учёта обслуживания автомобиля. |
| A4 | Аренда инструментов между пользователями | Система организации аренды инструментов между пользователями. |

## Метод и результат

Нечёткий коллективный TOPSIS объединяет треугольные оценки четырёх анкет, нормализует их с учётом MIN/MAX, применяет нечёткие веса и ранжирует концепции по близости к идеалу. [Подробная методика](phases/phase-01-concept-selection/topsis.md).

| Место | Код | Концепция | CC |
|---:|---|---|---:|
| 1 | A1 | Запись на приём к врачу | 1,0000 |
| 2 | A3 | Учёт обслуживания автомобиля | 0,4841 |
| 2 | A4 | Аренда инструментов между пользователями | 0,4841 |
| 4 | A2 | Учёт вещей на хранении | 0,3504 |

Выбрана **A1 «Запись на приём к врачу»**. Результаты воспроизводят [исходную Google-таблицу](https://docs.google.com/spreadsheets/d/1eqROJSJggUz9f7V3TO8Hx18-0x1MoO2HRUv8ptMTKsc/edit), проверенную 02.11.2026. Значения округлены до четырёх знаков.

[MVP выбранной системы](phases/phase-01-concept-selection/mvp.md) определяет трёх акторов, 12 Use Cases, исключения и критерии приёмки.

Оценки E3 рассчитаны как медианы трёх остальных анкет; это производные оценки, а не независимо собранное четвёртое мнение. [Происхождение данных и ограничения](phases/phase-01-concept-selection/expert-ratings.md).

## Результат МАИ

| Код | Приоритет МАИ | Место |
|---|---:|---:|
| A1 | 0,399169 | 1 |
| A2 | 0,239806 | 2 |
| A3 | 0,180512 | 3 |
| A4 | 0,180512 | 3 |

Оба метода выбрали A1; положение остальных концепций различается. В XLSX добавлены три листа МАИ. [Методика и проверка CR](phases/phase-01-concept-selection/ahp.md).

## Структура

```text
project-management/
├── README.md
├── PLAN.md
├── RACI.md
├── TASKS.md
├── .gitignore
├── .github/ISSUE_TEMPLATE/task.md
├── docs/{README.md,verification.md}
├── meetings/README.md
├── phases/
│   ├── phase-01-concept-selection/
│   │   ├── README.md
│   │   ├── concepts.md
│   │   ├── criteria.md
│   │   ├── expert-ratings.md
│   │   ├── topsis.md
│   │   ├── ahp.md
│   │   ├── analysis.md
│   │   ├── mvp.md
│   │   └── artifacts/
│   │       ├── README.md
│   │       └── phase-01-topsis.xlsx
│   ├── phase-02-work-distribution/{README.md,artifacts/README.md}
│   ├── phase-03-project-estimation/{README.md,artifacts/README.md}
│   ├── phase-04-forecasting/{README.md,artifacts/README.md}
│   └── phase-05-planning/{README.md,artifacts/README.md}
└── report/README.md
```

## Организация работы

- Ветки: `phase-N/<номер>-<задача>`, например `phase-1/07-topsis`.
- Изменения проходят Pull Request с проверкой другим участником.
- Задачи фазы 1 ведутся в [GitHub Issues](https://github.com/valyalshikovd/pm_masters_vsu/issues) по [шаблону](.github/ISSUE_TEMPLATE/task.md), сводный статус — в [GitHub Projects](https://github.com/users/valyalshikovd/projects/1).
- [TASKS.md](TASKS.md) — перечень задач; [RACI.md](RACI.md) — черновик ответственности.
- Плановые часы и фактическое чистое время учитываются отдельно. Неизвестные даты и часы обозначены TODO.
- [Журнал работы](docs/README.md) нужен для недельной статистики фазы 4; [протоколы встреч](meetings/README.md) фиксируют решения.
- [Итоговый отчёт](report/README.md) пока является заготовкой.

Репозиторий опубликован: [valyalshikovd/pm_masters_vsu](https://github.com/valyalshikovd/pm_masters_vsu). Фактическая работа фиксируется через Issues, ветки, коммиты и Pull Requests.
