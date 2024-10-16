### RAG Пайплайн для Преобразования Каталога Товаров ОАО «РЖД»

---

#### Описание проблемы
Компания нуждается в структурировании своей базы данных по классификатору ОКПД 2 для точного прогнозирования спроса и эффективного управления запасами. Важно определить ключевые характеристики товаров на основе стандартов ГОСТ.

#### Решение с использованием RAG пайплайна
Retrieval-Augmented Generation (RAG) — это метод, который объединяет поиск информации и генеративные модели (LLM), что позволяет повысить точность и качество ответов, а также улучшить понимание контекста.

**Этапы решения:**
1. **Векторизация ГОСТа**: 
   - Разделение документа ГОСТ на части и преобразование этих частей в векторы (embeddings).
  
2. **Поиск релевантного контекста**:
   - С помощью косинусного расстояния между вектором запроса и векторами частей документа определяется наиболее важная информация.

3. **Интеграция с LLM**:
   - Находится релевантный контекст и передается в языковую модель, которая генерирует набор характеристик для товаров в данном контексте.

#### Входные данные
- PDF файлы ГОСТов.
- Агрегированный список товаров, классифицированный по ОКПД2 и ГОСТу.

#### Выходные данные
- Список параметров для каждой подгруппы ОКПД2.
- Таблица, которая отображает параметры для каждого товара в рамках данной группы.

#### Преимущества решения
1. Определение характеристик товаров по ГОСТам. 
2. Выделение ключевых характеристик товара на основе контекста.
3. Интерпретация непонятных для человека характеристик в понятные и удобные для анализа параметры.

**Данное решение сильно улучшается за счет других решений по типу парсинга сайтов (как прелварительный шаг забора контекста) или улучшением работы LLM, так как объединяет идеи других обособленных подходов.**


#### Недостатки решения
1. В данном ДЕМО примере отсутствие предобработки ГОСТов, что может снизить точность определения характеристик.
2. Требуется поддержка актуальности ГОСТов, в которых могут добавляться какие-либо характеристики.
3. Возможные ошибки интерпретации характеристик языковой моделью.

#### Возможные улучшения
1. Добавление этапа предобработки ГОСТ документов. Данное улучшение существенно повысит выделение нужных признаков.
2. Настройка параметров создания векторов для повышения точности. Поможет наполнить окно контекста ключевой информацией и урезать ненужную.
3. Донастройка LLM для более точных выводов.

#### Заключение
Реализация предложенного RAG решения позволит ОАО «РЖД» автоматизировать процесс определения ключевых характеристик товаров, улучшить структурирование базы данных и повысить точность прогнозирования спроса и других бизнес-процессов.
