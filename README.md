# A/B-тестирование для e-learning
### Задачи проекта:
1. Определение ключевых метрик, позводяющих оценить эффективность новой механики оплаты.
2. Анализ результатов A/B-тестирования.
3. Написание SQL-запросов:
    - оптимальный запрос дающий информацию о количестве усердных учеников;
    - запрос для расчета основных метрик для контрольной и тестовой группы.
4. Создание функций:
    - для подгрузки дополнительных данных и пересчета метрик;
    - для создания графиков на основе обновленных метрик.
### Этапы работы:
1. A/B-тестирование
      1. Предварительное исследование данных.
      2. Выявление багов и особенностей.
      3. Определение ключевых метрик (ARPPU, CR в покупку).
      4. Предобработка данных - создание итоговой таблицы для анализа.
      5. Проверка гипотез:
         - бутстрап для сравнение средних ARPPU в группах;
         - хи-квадрат для конверсии.
      6. Оценка результатов теста - выводы.
2. SQL:
   1. Создание и оптимизация запроса для определения количества усердных учеников.
   2. Вычисление метрик в отдельных запросах, а затем их объединение с помощью JOIN.
3. Автоматизация пересчета метрик и построяения графиков.
### Результат:
В результате A/B-теста различия в ARPPU обнаружены между контрольной и тестовой группами, но конверсия в покупку не изменилась. Пользователи, использующие новую механику оплаты, совершают больше покупок, но остальные, возможно, не осведомлены об этой опции. АБ-тест имеет недостатки, такие как несбалансированная выборка и обнаруженный баг в отображении активности пользователей. Рекомендации: исправить баг, выбрать более подходящие метрики, сбалансировать выборки и повторно провести тест.

С помощью одного SQL-запроса удалось получить таблицу, содержащую информацию обо всех ключевых метрикав в контрольной и тестовой группах.

Разработана функция автоматически подгружающая дополнительную информацию об участниках теста и пересчитывающая метрики, а также функция строящая по этим метрикам графики.