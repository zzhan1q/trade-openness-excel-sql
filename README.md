# Внешняя торговля: экспорт и импорт к ВВП

В 2023 году в Люксембурге экспорт составил 217,38% ВВП, импорт — 185,19%. Сумма долей — 402,57% ВВП. В расчёт вошли 176 экономик с обеими сериями; высокий оборот не равен высокому торговому сальдо.

[Книга Excel](report.xlsx) · [Запрос SQLite](analysis.sql) · [Результаты CSV](summary.csv)

SQL соединяет экспорт и импорт по экономике и году. Формула Excel складывает две доли. Лист «Сверка» показывает пропуски по году и расхождения между формулами и SQL.

Оборот — сумма двух долей за 2023 год. Может превышать 100% ВВП и не означает торговый профицит.

**Источник.** Всемирный банк, World Development Indicators: [`NE.EXP.GNFS.ZS`](https://data.worldbank.org/indicator/NE.EXP.GNFS.ZS), [`NE.IMP.GNFS.ZS`](https://data.worldbank.org/indicator/NE.IMP.GNFS.ZS). В `source.csv` оставлены национальные ряды за 2010–2023 годы; региональные и глобальные агрегаты исключены. [Лицензия набора](https://datacatalog.worldbank.org/infrastructure-data/search/dataset/0037712/world-development-indicators). Дата выгрузки: 23 ноября 2026 года. Пустая ячейка означает отсутствие наблюдения.

Готовая книга открывается без установки Python. Чтобы пересобрать её из `source.csv` и проверить результат:

```sh
uv run --with-requirements requirements.txt python build.py
uv run --with-requirements requirements.txt python -m unittest -v
```
