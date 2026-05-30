C* Language Reference
## Предисловие

---

*C* Language Reference — First Edition*
*Авторы: независимые разработчики*

---

## Откуда появился C*

Большинство языков программирования рождаются из одного вопроса: "Как сделать это проще?"

C* родился из другого вопроса.

**"Почему мы соглашаемся с тем что не понимаем?"**

Программист пишет код. Код компилируется. Программа падает. Где ошибка? Никто не знает точно — потому что язык позволил написать код который выглядит правильно но не является правильным. Компилятор промолчал. Программист не заметил. Пользователь пострадал.

Это происходит каждый день. В каждом языке семейства C. Мы привыкли считать это нормой.

C* считает это неприемлемым.

---

## Философия

### Явность — не многословность

C* требует больше слов. Это правда. Код на C* длиннее эквивалентного кода на C в два или три раза. Начинающие видят это как недостаток. Опытные разработчики понимают — это цена которую стоит платить.

Каждое лишнее слово в C* несёт информацию. Не для компилятора — для человека который будет читать этот код через год. Явность — это уважение к читателю.

### Детерминизм — не ограничение

Всё в C* определено. Порядок вычислений. Поведение при переполнении. Момент освобождения памяти. Реакция на ошибку. Ни одного места где программа может повести себя "по-разному в зависимости от обстоятельств".

Это не ограничение свободы программиста. Это свобода от неопределённости. Программист знает точно что произойдёт — потому что сам это написал.

### Компилятор — не враг

В большинстве языков компилятор — это инструмент который превращает текст в машинный код. В C* компилятор — это партнёр который проверяет что программист не противоречит сам себе.

Если компилятор отклонил код — это не неудача. Это разговор. Компилятор говорит: "Здесь есть противоречие. Давай разберёмся." Сообщения компилятора C* написаны как объяснения — не как приговоры.

И если компилятор принял код — это гарантия. Не надежда. Не вероятность. Гарантия.

### Уровень — сердце языка

Главная идея C* проста и красива.

Представь путь от начала до конца компиляции. Без правил — широкий открытый коридор. Любой код проходит. Никаких препятствий. Никаких гарантий.

Каждое правило языка сужает этот коридор. Создаёт узкое место которое код обязан пройти. Владение памятью. Время жизни переменных. Пользовательские инварианты. Правила модулей. Каждое правило — новое узкое место.

Если код проходит через все узкие места — уровень пройден. Компиляция разрешена. Гарантии даны.

Если хотя бы в одном месте нет выхода — уровень умирает там. Компилятор точно показывает где и почему. Программист исправляет и пробует снова.

Эта метафора — не просто объяснение. Это буквальное описание того как работает компилятор C* внутри.

### Железо — не враг абстракции

C* близок к железу. Ближе чем любой другой язык с такими гарантиями безопасности. Регистры, порты, прерывания, прямые адреса памяти — всё это часть языка. Не исключения. Не unsafe блоки с отключёнными проверками.

C* верит что работа с железом и безопасность совместимы. Нужно только сказать компилятору что происходит. Явно. Подробно. С объяснением.

Взамен компилятор даёт гарантии — даже там где железо.

### Сложность — честная сделка

C* — сложный язык. Самый сложный в семействе C. Это не недостаток дизайна — это осознанное решение.

Сделка такова: программист берёт на себя сложность явного описания каждой детали. Компилятор берёт на себя гарантию что эти детали не противоречат друг другу и не приведут к ошибке.

Чем больше программист вложил в описание — тем больше компилятор может гарантировать. Это честный обмен.

Язык который скрывает сложность не делает её меньше — он просто прячет её туда где труднее найти. C* предпочитает честность.

---

## Кому предназначен C*

C* предназначен программистам которые хотят понимать что происходит.

Не угадывать. Не надеяться. Не отлаживать часами то что компилятор мог бы поймать за секунды.

Программистам которые пишут системы реального времени где ошибка стоит дорого. Драйверы где неопределённое поведение недопустимо. Встроенные системы где памяти мало и каждый байт на счету. Критическую инфраструктуру где надёжность важнее скорости разработки.

И просто программистам которые устали от магии и хотят видеть что происходит.

---

## Как читать эту книгу

Книга построена слоями. Каждый раздел опирается на предыдущий.

```
Раздел 1 — Синтаксис
    Как выглядит C* и почему именно так

Раздел 2 — Память и владение
    Фундамент всех гарантий языка

Раздел 3 — Управление потоком
    Как программа принимает решения

Раздел 4 — Типы и структуры данных
    Как описываются данные

Раздел 5 — Система и железо
    Как C* работает с реальным миром

Раздел 6 — Компилятор и уровень
    Как работают гарантии изнутри

Раздел 7 — Стандартная библиотека
    Что C* даёт из коробки

Раздел 8 — Инструменты и практика
    Как писать хороший код на C*
```

Читать можно последовательно — для изучения языка с нуля. Или использовать как справочник — открывать нужный раздел когда возникает вопрос.

Предметный указатель и глоссарий находятся в конце книги.

---

## Последнее слово перед началом

Программирование — это разговор. Программист говорит с машиной через язык. Каждый язык определяет правила этого разговора.

Большинство языков говорят программисту: "Мы упростим разговор. Скажи нам главное — остальное мы угадаем."

C* говорит другое: "Скажи нам всё. Не угадывай — знай. Не надейся — гарантируй."

Это другой разговор. Более длинный. Более требовательный. Но в конце этого разговора стоит кое-что ценное.

Уверенность.

---

*Независимые разработчики*
*C* Language Reference — First Edition*
# C* Language Reference
## Раздел 1 — Синтаксис
### 1.1 Алфавит языка

---

## Разрешённые символы

**Буквы**
C* использует только латинский алфавит. Никаких символов других языков в коде — только в строках текста и комментариях.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
```

**Цифры**
```
0 1 2 3 4 5 6 7 8 9
```

**Разрешённые символы пунктуации**
```
[ ]   — описание свойств типа
( )   — группировка условий
" "   — текстовые строки
_     — разделитель в именах
.     — доступ к полю структуры
,     — перечисление
:     — начало блока значений
;     — никогда. Запрещена.
```

---

## Запрещённые символы и причины

| Символ | Где используется в C | Почему запрещён в C* |
|---|---|---|
| `*` | Указатели, умножение | Два смысла — путаница |
| `&` | Адрес, логическое И | Два смысла — путаница |
| `->` | Доступ через указатель | Заменён словом |
| `#` | Препроцессор | Препроцессора нет |
| `;` | Конец строки | Заменён структурой блоков |
| `?:` | Тернарный оператор | Заменён явным условием |
| `++` `--` | Инкремент | Заменён словом |
| `<<` `>>` | Битовый сдвиг | Заменён словом |
| `!` | Логическое НЕ | Заменён словом |

---

## Главное правило алфавита

> Каждый символ в C* имеет **ровно один смысл.** Если символ может означать две разные вещи — он заменяется словом.

---

## Комментарии

```
-- Это однострочный комментарий

--[
    Это многострочный комментарий.
    Можно писать сколько угодно строк.
]--
```

Символ `--` выбран потому что не используется ни в одной операции языка и читается как пауза — горизонтальная черта перед пояснением.

---

## Пробелы и отступы

C* не считает отступы значимыми как Python. Но **требует** их для читаемости — компилятор предупредит если код не отформатирован.

Одна инструкция — одна строка. Разбить на две строки можно только внутри блока.

---

# C* Language Reference
## Раздел 1 — Синтаксис
### 1.2 Слова языка

---

## Главное правило слов

> Каждое слово в C* — это полное английское слово. Никаких сокращений, никаких аббревиатур, никаких символов вместо слов.

Это не стиль — это требование компилятора. `int` не существует. `ptr` не существует. `buf` не существует.

---

## Ключевые слова — Структура

Слова которые создают блоки и границы программы.

```
function        — объявление функции
end             — закрытие любого блока
module          — объявление модуля
program         — точка входа программы
body            — начало тела функции
returns         — что функция возвращает
receives        — что функция принимает
nothing         — функция ничего не возвращает
```

---

## Ключевые слова — Переменные

```
declare         — объявить переменную
named           — дать имя
is              — присвоить значение
as              — преобразовать тип явно
constant        — значение никогда не изменится
```

---

## Ключевые слова — Типы

```
integer         — целое число
float           — число с плавающей точкой
byte            — один байт
boolean         — истина или ложь
text            — строка символов
pointer         — ссылка на адрес памяти
address         — конкретный адрес в памяти
nothing         — отсутствие значения
```

Свойства типов пишутся в скобках:
```
integer[signed, 32bit]
integer[unsigned, 8bit]
float[64bit]
pointer[to integer[signed, 32bit]]
```

---

## Ключевые слова — Арифметика

```
plus            — сложение
minus           — вычитание
multiply        — умножение
divide          — деление
remainder       — остаток от деления
```

Пример:
```
result is first_number plus second_number
result is total multiply by factor
result is value remainder 8
```

---

## Ключевые слова — Логика

```
is equal to         — равно
is not equal to     — не равно
is greater than     — больше
is less than        — меньше
is greater or equal — больше или равно
is less or equal    — меньше или равно
and                 — логическое И
or                  — логическое ИЛИ
not                 — логическое НЕ
```

---

## Ключевые слова — Управление потоком

```
if              — если условие истинно
otherwise       — иначе
repeat          — цикл
while           — пока условие истинно
stop            — выйти из цикла
skip            — перейти к следующей итерации
return          — вернуть значение из функции
```

---

## Ключевые слова — Память

```
allocate        — выделить память
release         — освободить память
transfer        — передать владение
copy            — скопировать данные
address of      — получить адрес переменной
value at        — получить значение по адресу
```

---

## Ключевые слова — Ошибки

```
on              — описание реакции на событие
reject          — отклонить выполнение
with error      — указать тип ошибки
handle          — обработать ошибку
recover         — продолжить после ошибки
```

---

## Правила именования

Имена которые даёт программист — переменные, функции, модули — подчиняются строгим правилам.

**Разрешено:**
```
audio_buffer
first_number
write_audio
memory_model_ring
```

**Запрещено:**

| Пример | Причина |
|---|---|
| `audioBuffer` | Верхний регистр в середине — скрытая граница слова |
| `ab` | Непонятное сокращение |
| `temp` | Что значит temp — температура или временный? |
| `data` | Слишком широко — данные чего? |
| `x` | Ничего не говорит о содержимом |

**Главное правило имён:**
> Имя должно описывать **что это есть**, а не **что с этим делают**. Читатель кода должен понять смысл имени без контекста.

---

## Зарезервированные слова

Эти слова нельзя использовать как имена переменных или функций — они принадлежат языку:

```
function, end, module, program, body, returns, receives,
declare, named, is, as, constant, nothing, integer, float,
byte, boolean, text, pointer, address, plus, minus, multiply,
divide, remainder, if, otherwise, repeat, while, stop, skip,
return, allocate, release, transfer, copy, on, reject, with,
error, handle, recover, and, or, not, uses, memory, define,
rule, gateway, step, true, false
```

---

# C* Language Reference
## Раздел 1 — Синтаксис
### 1.2 Слова языка

---

## Главное правило слов

> Каждое слово в C* — это полное английское слово. Никаких сокращений, никаких аббревиатур, никаких символов вместо слов.

Это не стиль — это требование компилятора. `int` не существует. `ptr` не существует. `buf` не существует.

---

## Ключевые слова — Структура

Слова которые создают блоки и границы программы.

```
function        — объявление функции
end             — закрытие любого блока
module          — объявление модуля
program         — точка входа программы
body            — начало тела функции
returns         — что функция возвращает
receives        — что функция принимает
nothing         — функция ничего не возвращает
```

---

## Ключевые слова — Переменные

```
declare         — объявить переменную
named           — дать имя
is              — присвоить значение
as              — преобразовать тип явно
constant        — значение никогда не изменится
```

---

## Ключевые слова — Типы

```
integer         — целое число
float           — число с плавающей точкой
byte            — один байт
boolean         — истина или ложь
text            — строка символов
pointer         — ссылка на адрес памяти
address         — конкретный адрес в памяти
nothing         — отсутствие значения
```

Свойства типов пишутся в скобках:
```
integer[signed, 32bit]
integer[unsigned, 8bit]
float[64bit]
pointer[to integer[signed, 32bit]]
```

---

## Ключевые слова — Арифметика

```
plus            — сложение
minus           — вычитание
multiply        — умножение
divide          — деление
remainder       — остаток от деления
```

Пример:
```
result is first_number plus second_number
result is total multiply by factor
result is value remainder 8
```

---

## Ключевые слова — Логика

```
is equal to         — равно
is not equal to     — не равно
is greater than     — больше
is less than        — меньше
is greater or equal — больше или равно
is less or equal    — меньше или равно
and                 — логическое И
or                  — логическое ИЛИ
not                 — логическое НЕ
```

---

## Ключевые слова — Управление потоком

```
if              — если условие истинно
otherwise       — иначе
repeat          — цикл
while           — пока условие истинно
stop            — выйти из цикла
skip            — перейти к следующей итерации
return          — вернуть значение из функции
```

---

## Ключевые слова — Память

```
allocate        — выделить память
release         — освободить память
transfer        — передать владение
copy            — скопировать данные
address of      — получить адрес переменной
value at        — получить значение по адресу
```

---

## Ключевые слова — Ошибки

```
on              — описание реакции на событие
reject          — отклонить выполнение
with error      — указать тип ошибки
handle          — обработать ошибку
recover         — продолжить после ошибки
```

---

## Правила именования

Имена которые даёт программист — переменные, функции, модули — подчиняются строгим правилам.

**Разрешено:**
```
audio_buffer
first_number
write_audio
memory_model_ring
```

**Запрещено:**

| Пример | Причина |
|---|---|
| `audioBuffer` | Верхний регистр в середине — скрытая граница слова |
| `ab` | Непонятное сокращение |
| `temp` | Что значит temp — температура или временный? |
| `data` | Слишком широко — данные чего? |
| `x` | Ничего не говорит о содержимом |

**Главное правило имён:**
> Имя должно описывать **что это есть**, а не **что с этим делают**. Читатель кода должен понять смысл имени без контекста.

---

## Зарезервированные слова

Эти слова нельзя использовать как имена переменных или функций — они принадлежат языку:

```
function, end, module, program, body, returns, receives,
declare, named, is, as, constant, nothing, integer, float,
byte, boolean, text, pointer, address, plus, minus, multiply,
divide, remainder, if, otherwise, repeat, while, stop, skip,
return, allocate, release, transfer, copy, on, reject, with,
error, handle, recover, and, or, not, uses, memory, define,
rule, gateway, step, true, false
```

---

# C* Language Reference
## Раздел 1 — Синтаксис
### 1.4 Переменные

---

## Главное правило переменных

> Переменная в C* никогда не существует в неопределённом состоянии. Каждая переменная в момент объявления обязана иметь тип, имя и начальное значение.

В C можно написать:
```c
int x;  // что внутри? никто не знает
```

В C* это невозможно. Компилятор отклонит.

---

## Объявление переменной

Полная форма объявления:

```
declare integer[signed, 32bit] named counter is 0
declare boolean named is_running is false
declare text named user_name is "unknown"
declare float[64bit] named temperature is 0.0
```

Структура всегда одна:
```
declare [тип] named [имя] is [начальное значение]
```

Все четыре части обязательны. Пропустить любую — отклонение компиляции.

---

## Объявление константы

Если значение никогда не изменится — это обязано быть объявлено явно:

```
declare constant integer[unsigned, 32bit] named max_size is 1024
declare constant float[64bit] named gravity is 9.81
declare constant text named error_prefix is "FATAL"
```

Попытка изменить константу после объявления:
```
max_size is 2048  -- ОШИБКА. Компилятор отклоняет.
```

Сообщение компилятора:
```
COMPILATION REJECTED
Attempted to modify constant named [max_size]
Declared as constant at: line 4
Modification attempted at: line 17
Constants cannot be modified after declaration.
```

---

## Изменение переменной

```
declare integer[signed, 32bit] named score is 0

-- Присвоить новое значение
score is 100

-- Присвоить результат вычисления
score is score plus 50

-- Присвоить результат функции
score is calculate_bonus receives current_level
```

Слово `is` всегда означает присвоение. Одно слово — один смысл.

---

## Область видимости

Переменная живёт только внутри блока где объявлена. За пределами блока она не существует.

```
program Example

    body

        declare integer[signed, 32bit] named outer is 10

        if outer is greater than 5
            declare integer[signed, 32bit] named inner is 20
            -- здесь видны и outer и inner
        end if

        -- здесь inner не существует
        -- попытка использовать inner — отклонение компиляции

    end body

end program
```

Сообщение компилятора при попытке использовать `inner` снаружи:
```
COMPILATION REJECTED
Variable named [inner] does not exist at this scope.
Variable [inner] was declared inside block at: line 8
Current scope is outside that block at: line 13
```

---

## Переменная внутри функции

Каждая функция имеет свои переменные. Они не видны снаружи и не влияют на переменные других функций.

```
function calculate_total
    receives
        integer[signed, 32bit] named base_price
        integer[signed, 32bit] named tax_rate
    returns
        integer[signed, 32bit] named total_price
    body
        declare integer[signed, 32bit] named tax_amount is 0
        tax_amount is base_price multiply by tax_rate
        tax_amount is tax_amount divide by 100
        total_price is base_price plus tax_amount
    end body
end function
```

Переменная `tax_amount` существует только внутри этой функции. Снаружи она недоступна и недостижима.

---

## Несколько переменных одного типа

Каждая переменная объявляется отдельной строкой. Никаких объявлений через запятую.

```
-- Запрещено:
declare integer[signed, 32bit] named x is 0, y is 0, z is 0

-- Правильно:
declare integer[signed, 32bit] named x is 0
declare integer[signed, 32bit] named y is 0
declare integer[signed, 32bit] named z is 0
```

Одна строка — одно объявление. Всегда.

---

## Преобразование типов

Переменная не может молча сменить тип. Любое преобразование — явное и видимое.

```
declare integer[signed, 32bit] named big_number is 1000
declare integer[unsigned, 8bit] named small_number is 0

-- Запрещено — неявное преобразование:
small_number is big_number

-- Правильно — явное преобразование:
small_number is convert big_number to integer[unsigned, 8bit]
```

При явном преобразовании компилятор требует обработки потери данных:

```
small_number is convert big_number to integer[unsigned, 8bit]
    on overflow
        reject with error[value_too_large]
```

Без блока `on overflow` — отклонение компиляции. Ты обязан сказать что делать если число не помещается.

---

## Что компилятор проверяет в переменных

```
✓ Каждая переменная имеет тип, имя и начальное значение
✓ Константы никогда не изменяются
✓ Переменная не используется за пределами своего блока
✓ Любое преобразование типов явное
✓ При преобразовании описана обработка переполнения
✓ Одно объявление — одна строка
✓ Имя описывает содержимое, не действие
```

---

# C* Language Reference
## Раздел 1 — Синтаксис
### 1.5 Типы

---

## Главное правило типов

> Каждый тип в C* описывает не только **что хранится** но и **как хранится** и **какие операции допустимы**. Компилятор знает о типе всё. Программист обязан сказать компилятору всё.

---

## Встроенные типы

### Целые числа — integer

```
integer[signed, 8bit]       -- от -128 до 127
integer[unsigned, 8bit]     -- от 0 до 255
integer[signed, 16bit]      -- от -32768 до 32767
integer[unsigned, 16bit]    -- от 0 до 65535
integer[signed, 32bit]      -- от -2147483648 до 2147483647
integer[unsigned, 32bit]    -- от 0 до 4294967295
integer[signed, 64bit]      -- очень большое со знаком
integer[unsigned, 64bit]    -- очень большое без знака
```

Знак и размер обязательны всегда. Просто `integer` без свойств — отклонение компиляции.

---

### Числа с плавающей точкой — float

```
float[32bit]    -- одинарная точность
float[64bit]    -- двойная точность
```

```
declare float[64bit] named precise_value is 3.14159265358979
declare float[32bit] named rough_value is 3.14
```

---

### Булево значение — boolean

```
declare boolean named is_active is true
declare boolean named has_error is false
```

Допустимые значения только два: `true` и `false`. Никаких `1` и `0` вместо булевых значений — компилятор отклонит.

```
-- Запрещено:
declare boolean named flag is 1

-- Правильно:
declare boolean named flag is true
```

---

### Один байт — byte

```
declare byte named raw_data is 0
declare byte named checksum is 255
```

`byte` — это всегда ровно 8 бит без знака. Никаких свойств не требует. Используется для работы с сырыми данными.

---

### Текст — text

```
declare text named greeting is "Hello"
declare text named empty_line is ""
```

`text` в C* — это всегда последовательность байт в кодировке UTF-8. Размер не указывается при объявлении переменной — только при выделении памяти.

---

### Указатель — pointer

Указатель в C* всегда говорит на что он указывает:

```
declare pointer[to integer[signed, 32bit]] named number_address is null
declare pointer[to byte] named raw_address is null
declare pointer[to text] named text_address is null
```

Просто `pointer` без указания типа — отклонение компиляции. Компилятор обязан знать что находится по адресу.

Единственное допустимое начальное значение для указателя без выделения памяти — `null`. И использование `null` указателя всегда требует проверки:

```
declare pointer[to integer[signed, 32bit]] named number_address is null

-- Запрещено — использовать без проверки:
value at number_address is 42

-- Правильно:
if number_address is not null
    value at number_address is 42
otherwise
    reject with error[null_pointer_access]
end if
```

---

### Отсутствие значения — nothing

```
function print_message
    receives
        text named message
    returns
        nothing
    body
        -- функция ничего не возвращает
    end body
end function
```

`nothing` не является типом переменной — только возвращаемым типом функции. Объявить переменную типа `nothing` невозможно.

---

## Пользовательские типы

Программист может определить собственный тип на основе существующих.

### Простой псевдоним

```
define type[PlayerScore] as integer[unsigned, 32bit]

declare PlayerScore named current_score is 0
declare PlayerScore named high_score is 9999
```

Псевдоним создаёт новый тип. `PlayerScore` и `integer[unsigned, 32bit]` — разные типы. Смешивать без явного преобразования запрещено.

---

### Составной тип — структура

```
define type[AudioSample]
    contains
        integer[signed, 16bit] named left_channel
        integer[signed, 16bit] named right_channel
        integer[unsigned, 32bit] named timestamp
        boolean named is_silent
    alignment 4 bytes
end type
```

Поле `alignment` обязательно — программист явно говорит как структура выравнивается в памяти. Компилятор не решает это сам.

Использование:

```
declare AudioSample named current_sample is
    left_channel: 0
    right_channel: 0
    timestamp: 0
    is_silent: true
end declare
```

Все поля обязаны быть инициализированы. Пропустить поле — отклонение компиляции.

Доступ к полям:

```
current_sample.left_channel is 1024
current_sample.is_silent is false
```

---

### Перечисление — набор допустимых значений

```
define type[ConnectionState]
    can be
        disconnected
        connecting
        connected
        error
    end can be
end type

declare ConnectionState named current_state is disconnected
```

Присвоить значение не из списка — отклонение компиляции:

```
-- Запрещено:
current_state is "active"

-- Правильно:
current_state is connected
```

---

## Размер типов в памяти

Программист всегда может узнать сколько байт занимает тип:

```
declare integer[unsigned, 32bit] named type_size is size of integer[signed, 32bit]
declare integer[unsigned, 32bit] named struct_size is size of AudioSample
```

---

## Совместимость типов

Два типа совместимы только если они **идентичны**. Никакой неявной совместимости.

```
declare integer[signed, 32bit] named first is 100
declare integer[unsigned, 32bit] named second is 100

-- Запрещено — разные типы:
first is second

-- Правильно — явное преобразование:
first is convert second to integer[signed, 32bit]
    on overflow
        reject with error[value_too_large]
```

---

## Что компилятор проверяет в типах

```
✓ integer всегда имеет знак и размер
✓ float всегда имеет размер
✓ pointer всегда указывает на конкретный тип
✓ null указатель всегда проверяется перед использованием
✓ boolean принимает только true и false
✓ структуры имеют явное выравнивание
✓ все поля структуры инициализированы
✓ перечисление принимает только объявленные значения
✓ любое преобразование типов явное и обработанное
```

---

# C* Language Reference
## Раздел 1 — Синтаксис
### 1.6 Функции

---

## Главное правило функций

> Функция в C* — это контракт. Она явно объявляет что получает, что возвращает, и что может пойти не так. Компилятор проверяет соблюдение контракта на каждом вызове.

---

## Полная структура функции

```
function [имя]
    receives
        [тип] named [имя параметра]
        [тип] named [имя параметра]
    returns
        [тип] named [имя результата]
    on [событие]
        [реакция]
    body
        [код]
    end body
end function
```

Порядок блоков обязателен. Менять местами — отклонение компиляции.

---

## Функция без параметров

```
function get_system_time
    receives
        nothing
    returns
        integer[unsigned, 64bit] named current_time
    body
        current_time is read_hardware_clock
    end body
end function
```

Если функция ничего не получает — это обязано быть написано явно через `nothing`. Пропустить блок `receives` полностью — отклонение компиляции.

---

## Функция без возвращаемого значения

```
function log_message
    receives
        text named message
        integer[unsigned, 8bit] named severity_level
    returns
        nothing
    body
        write_to_log receives message and severity_level
    end body
end function
```

---

## Функция с обработкой ошибок

```
function divide_numbers
    receives
        integer[signed, 32bit] named dividend
        integer[signed, 32bit] named divisor
    returns
        integer[signed, 32bit] named result
    on divisor is equal to 0
        reject with error[division_by_zero]
    on overflow
        reject with error[arithmetic_overflow]
    body
        result is dividend divide by divisor
    end body
end function
```

Блоки `on` описывают все ситуации которые могут пойти не так. Компилятор анализирует тело функции и требует блок `on` для каждой потенциальной проблемы. Пропустить — отклонение компиляции.

---

## Вызов функции

### Простой вызов

```
declare integer[signed, 32bit] named total is 0
total is calculate_total receives base_price and tax_rate
```

### Вызов функции которая возвращает nothing

```
log_message receives "Program started" and 1
```

### Вызов с обработкой ошибок

Каждый вызов функции которая может вернуть ошибку обязан иметь обработку:

```
declare integer[signed, 32bit] named answer is 0

call divide_numbers receives 100 and divisor
    on error[division_by_zero]
        log_message receives "Cannot divide by zero" and 3
        answer is 0
    on error[arithmetic_overflow]
        log_message receives "Number too large" and 3
        answer is 0
    on success
        answer is result
end call
```

Написать вызов без блоков `on error` и `on success` — отклонение компиляции. Ты обязан описать оба исхода.

---

## Несколько параметров — порядок важен

```
function calculate_rectangle_area
    receives
        integer[unsigned, 32bit] named width
        integer[unsigned, 32bit] named height
    returns
        integer[unsigned, 32bit] named area
    on overflow
        reject with error[arithmetic_overflow]
    body
        area is width multiply by height
    end body
end function
```

Вызов — параметры передаются по именам, не по позиции:

```
declare integer[unsigned, 32bit] named room_area is 0

call calculate_rectangle_area
    with width: 12
    with height: 8
    on error[arithmetic_overflow]
        reject with error[room_too_large]
    on success
        room_area is area
end call
```

Передача по именам означает что порядок при вызове не важен. Но все параметры обязательны. Пропустить параметр — отклонение компиляции.

---

## Вложенные вызовы — запрещены

В C можно написать:
```c
result = add(multiply(a, b), divide(c, d));
```

В C* это запрещено. Каждый вызов — отдельная строка:

```
declare integer[signed, 32bit] named product is 0
declare integer[signed, 32bit] named quotient is 0
declare integer[signed, 32bit] named final_result is 0

call multiply_numbers
    with first_number: a
    with second_number: b
    on error[arithmetic_overflow]
        reject with error[calculation_failed]
    on success
        product is result
end call

call divide_numbers
    with dividend: c
    with divisor: d
    on error[division_by_zero]
        reject with error[calculation_failed]
    on error[arithmetic_overflow]
        reject with error[calculation_failed]
    on success
        quotient is result
end call

call add_numbers
    with first_number: product
    with second_number: quotient
    on error[arithmetic_overflow]
        reject with error[calculation_failed]
    on success
        final_result is result
end call
```

Код длиннее. Зато каждый шаг виден. Каждая ошибка обработана. Никакой магии.

---

## Рекурсия

Рекурсия в C* разрешена но обязана иметь явное условие остановки объявленное до тела функции:

```
function calculate_factorial
    receives
        integer[unsigned, 32bit] named number
    returns
        integer[unsigned, 64bit] named factorial_result
    stops when number is equal to 0
    on overflow
        reject with error[arithmetic_overflow]
    body
        if number is equal to 0
            factorial_result is 1
        otherwise
            declare integer[unsigned, 32bit] named previous_number is 0
            previous_number is number minus 1

            call calculate_factorial
                with number: previous_number
                on error[arithmetic_overflow]
                    reject with error[arithmetic_overflow]
                on success
                    factorial_result is factorial_result multiply by factorial_result
            end call
        end if
    end body
end function
```

Блок `stops when` обязателен для рекурсивных функций. Компилятор проверяет что условие остановки достижимо.

---

## Что компилятор проверяет в функциях

```
✓ Блоки receives, returns, body присутствуют всегда
✓ nothing написано явно если параметров или результата нет
✓ Все потенциальные ошибки имеют блок on
✓ Каждый вызов имеет обработку on error и on success
✓ Параметры передаются по именам
✓ Все параметры переданы при вызове
✓ Вложенные вызовы запрещены
✓ Рекурсия имеет явное условие остановки
✓ Условие остановки рекурсии достижимо
```

---

# C* Language Reference
## Раздел 1 — Синтаксис
### 1.7 Блоки и границы

---

## Главное правило блоков

> Каждый блок в C* имеет явное начало и явный конец. Компилятор никогда не определяет границы блока по отступам или скобкам. Границы всегда написаны словами.

---

## Таблица всех блоков языка

| Открытие | Закрытие |
|---|---|
| `program [имя]` | `end program` |
| `module [имя]` | `end module` |
| `function [имя]` | `end function` |
| `body` | `end body` |
| `if [условие]` | `end if` |
| `otherwise` | `end otherwise` |
| `repeat while [условие]` | `end repeat` |
| `on [событие]` | `end on` |
| `call [функция]` | `end call` |
| `define type[имя]` | `end type` |
| `define memory_model[имя]` | `end memory_model` |
| `gateway [откуда] to [куда]` | `end gateway` |
| `contains` | `end contains` |
| `can be` | `end can be` |

---

## Условный блок

```
if current_temperature is greater than 100
    log_message receives "Temperature critical" and 3
    reject with error[overheating]
end if
```

С альтернативой:

```
if user_score is greater or equal to passing_score
    declare text named status is "passed"
    log_message receives status and 1
otherwise
    declare text named status is "failed"
    log_message receives status and 2
end otherwise
end if
```

Блок `otherwise` закрывается своим `end otherwise` до закрытия `end if`. Каждый блок закрывается отдельно — никакой общей скобки для нескольких блоков.

---

## Цепочка условий

```
if connection_state is equal to connected
    process_incoming_data
otherwise if connection_state is equal to connecting
    wait_for_connection
otherwise if connection_state is equal to disconnected
    attempt_reconnection
otherwise
    reject with error[unknown_connection_state]
end otherwise
end otherwise if
end otherwise if
end if
```

Каждое `otherwise if` закрывается своим `end otherwise if`. Порядок закрытия — от внутреннего к внешнему.

---

## Блок повторения

### Повторение пока условие истинно

```
declare integer[unsigned, 32bit] named attempt_count is 0
declare boolean named connection_established is false

repeat while connection_established is equal to false
    attempt_reconnection
    attempt_count is attempt_count plus 1

    if attempt_count is greater or equal to max_attempts
        stop
    end if
end repeat
```

### Повторение с известным числом шагов

```
declare integer[unsigned, 32bit] named current_index is 0

repeat while current_index is less than buffer_size
    process_byte receives buffer at current_index
    current_index is current_index plus 1
end repeat
```

C* не имеет специального блока `for` — только `repeat while`. Это одна конструкция с одним смыслом.

---

## Управление повторением

```
repeat while has_more_data is equal to true

    declare byte named current_byte is read_next_byte

    if current_byte is equal to end_marker
        stop        -- выйти из repeat немедленно
    end if

    if current_byte is equal to skip_marker
        skip        -- перейти к следующей итерации
    end if

    process_byte receives current_byte

end repeat
```

`stop` — выход из ближайшего `repeat while`.
`skip` — переход к следующей итерации ближайшего `repeat while`.

Оба слова действуют только на ближайший блок повторения. Выйти сразу из двух вложенных циклов одним `stop` — невозможно. Это сделано намеренно.

---

## Вложенные блоки

```
program DataProcessor

    function process_all_buffers
        receives
            integer[unsigned, 32bit] named buffer_count
        returns
            nothing
        on error[processing_failed]
            reject with error[processing_failed]
        body

            declare integer[unsigned, 32bit] named current_buffer is 0

            repeat while current_buffer is less than buffer_count

                declare boolean named buffer_is_valid is false

                call validate_buffer
                    with buffer_index: current_buffer
                    on error[processing_failed]
                        skip
                    on success
                        buffer_is_valid is true
                end call

                if buffer_is_valid is equal to true
                    call process_single_buffer
                        with buffer_index: current_buffer
                        on error[processing_failed]
                            reject with error[processing_failed]
                        on success
                            -- продолжаем
                    end call
                end if

                current_buffer is current_buffer plus 1

            end repeat

        end body
    end function

    body
        call process_all_buffers
            with buffer_count: 16
            on error[processing_failed]
                log_message receives "Processing failed" and 3
            on success
                log_message receives "All buffers processed" and 1
        end call
    end body

end program
```

---

## Правило закрытия блоков

Блоки закрываются в обратном порядке открытия. Последний открытый — первый закрытый.

```
program Example           -- открыт 1й
    function do_work      -- открыт 2й
        body              -- открыт 3й
            if condition  -- открыт 4й
            end if        -- закрыт 4й
        end body          -- закрыт 3й
    end function          -- закрыт 2й
end program               -- закрыт 1й
```

Нарушить этот порядок — отклонение компиляции.

---

## Пустые блоки

Пустой блок обязан содержать явный комментарий объясняющий почему он пуст:

```
if error_count is greater than 0
    -- обработка ошибок будет добавлена в версии 2
end if
```

Пустой блок без комментария — отклонение компиляции. Компилятор не допускает блоков о которых неизвестно — они пусты намеренно или по ошибке.

---

## Что компилятор проверяет в блоках

```
✓ Каждый открытый блок имеет закрытие
✓ Порядок закрытия обратен порядку открытия
✓ otherwise и otherwise if закрываются до end if
✓ stop и skip действуют только на ближайший repeat
✓ Пустые блоки содержат объясняющий комментарий
✓ Отступы кратны четырём пробелам на каждом уровне
```

---

## Раздел 1 завершён

Мы описали полный синтаксис C*:

```
1.1 Алфавит языка         ✓
1.2 Слова языка           ✓
1.3 Структура программы   ✓
1.4 Переменные            ✓
1.5 Типы                  ✓
1.6 Функции               ✓
1.7 Блоки и границы       ✓
```

---

# C* Language Reference
## Раздел 2 — Память и владение
### 2.1 Модель памяти C*

---

## Главное правило памяти

> В C* каждая переменная имеет явно объявленное место жизни, явно объявленного владельца, и явно объявленный момент смерти. Компилятор знает всё это до запуска программы.

---

## Два места памяти

Память в компьютере с точки зрения C* делится на два места. Программист выбирает место при объявлении каждой переменной.

### Стек

Представь стек как **стопку листов бумаги.** Когда входишь в функцию — кладёшь лист сверху. Когда выходишь из функции — лист снимается и выбрасывается. Всё что было написано на листе — исчезает.

```
function calculate_area
    receives
        integer[unsigned, 32bit] named width
        integer[unsigned, 32bit] named height
    returns
        integer[unsigned, 32bit] named area
    on overflow
        reject with error[arithmetic_overflow]
    body
        declare integer[unsigned, 32bit] named temp_result on stack is 0
        temp_result is width multiply by height
        area is temp_result
    end body
end function
-- temp_result исчез. Лист выброшен.
```

Стек быстрый. Стек автоматический. Но стек ограничен — большие данные туда не помещаются.

### Куча

Представь кучу как **склад с ячейками.** Ты просишь ячейку — тебе дают адрес. Ячейка твоя пока ты явно не скажешь её освободить. Никто не освободит её за тебя.

```
declare integer[signed, 32bit] named sensor_value on heap is 0
-- sensor_value живёт на складе
-- ячейка твоя до явного release

release sensor_value
-- ячейка освобождена. Использовать sensor_value дальше — невозможно.
```

Куча большая. Куча гибкая. Но куча требует ответственности — забыл освободить, получил утечку памяти. C* делает забывание невозможным.

---

## Правила стека

```
✓ Переменная на стеке умирает при выходе из блока где объявлена
✓ Переменная на стеке не может быть передана как owner
✓ Указатель на переменную стека не может пережить эту переменную
✓ Размер переменной на стеке должен быть известен на этапе компиляции
```

Попытка нарушить любое правило — отклонение компиляции:

```
function bad_example
    receives
        nothing
    returns
        pointer[to integer[signed, 32bit]] named result_ptr
    body
        declare integer[signed, 32bit] named local_value on stack is 42
        result_ptr is address of local_value as access

        -- ОШИБКА. result_ptr переживёт local_value.
        -- local_value умрёт при выходе из функции.
        -- Компилятор видит это и отклоняет.

    end body
end function
```

Сообщение компилятора:
```
COMPILATION REJECTED
Lifetime violation detected.

Variable [local_value] lives on stack.
Declared at: line 8
Dies at: end of function body, line 11

Pointer [result_ptr] is returned from function.
Pointer would outlive its target.

Stack variables cannot be pointed to beyond their block.
```

---

## Правила кучи

```
✓ Переменная на куче живёт до явного release или передачи as owner
✓ Каждая переменная на куче обязана иметь достижимый release
✓ После release переменная не существует
✓ Передача as owner освобождает оригинал автоматически
✓ Размер переменной на куче может быть неизвестен до запуска
```

Компилятор проверяет достижимость `release` через уровень:

```
function load_audio_file
    receives
        text named file_path
    returns
        nothing
    on error[file_not_found]
        reject with error[file_not_found]
    on error[out_of_memory]
        reject with error[out_of_memory]
    body
        declare byte named audio_data on heap is 0

        call read_file
            with path as copy: file_path
            on error[file_not_found]
                release audio_data
                reject with error[file_not_found]
            on success
                audio_data is result
        end call

        call process_audio
            with data as owner: audio_data
            on error[processing_failed]
                -- audio_data передан as owner
                -- он уже не наш. release запрещён.
                reject with error[processing_failed]
            on success
                -- audio_data передан as owner
                -- освобождение произошло автоматически
        end call

    end body
end function
```

Компилятор прослеживает все пути через блоки. На каждом пути переменная кучи обязана либо получить `release` либо быть передана `as owner`. Путь без одного из этих исходов — смерть на уровне.

---

## Выбор места — практическое правило

C* не навязывает выбор но даёт чёткие критерии:

| Ситуация | Место |
|---|---|
| Временный результат вычисления | stack |
| Счётчик цикла | stack |
| Маленькая структура только для этой функции | stack |
| Данные которые переживут функцию | heap |
| Большой буфер или массив | heap |
| Данные размер которых неизвестен заранее | heap |
| Данные которые передаются между модулями | heap |

---

# C* Language Reference
## Раздел 2 — Память и владение
### 2.2 Встроенные модели памяти

---

## Главное правило встроенных моделей

> C* поставляется с двумя встроенными моделями памяти. Они покрывают большинство задач. Пользовательские модели строятся поверх них или независимо от них — но компилятор всегда знает по каким правилам работает каждый модуль.

---

## Модель первая — Manual

Ручное управление памятью. Программист контролирует всё сам. Максимальная близость к железу.

### Объявление

```
module LowLevelDriver uses memory[Manual]
    -- весь код внутри живёт по правилам Manual
end module
```

### Правила модели Manual

```
Правило 1: Каждый allocate обязан иметь парный release
Правило 2: release можно вызвать только один раз
Правило 3: После release переменная не существует
Правило 4: Передача as owner считается неявным release
Правило 5: Передача as access не меняет владельца
Правило 6: Владелец всегда один
```

### Пример работы

```
module LowLevelDriver uses memory[Manual]

    function initialize_device
        receives
            integer[unsigned, 32bit] named device_id
        returns
            pointer[to byte] named device_buffer
        on error[out_of_memory]
            reject with error[out_of_memory]
        on error[device_not_found]
            reject with error[device_not_found]
        body

            declare pointer[to byte] named buffer on heap is null

            call allocate_memory
                with size: 4096
                on error[out_of_memory]
                    reject with error[out_of_memory]
                on success
                    buffer is result
            end call

            call verify_device
                with id as copy: device_id
                with buffer as access: buffer
                on error[device_not_found]
                    release buffer
                    reject with error[device_not_found]
                on success
                    -- продолжаем
            end call

            device_buffer is buffer as owner
            -- владение передано наружу
            -- buffer здесь больше не наш

        end body
    end function

end module
```

### Что компилятор проверяет в Manual

```
✓ Каждый путь через блоки ведёт к release или передаче as owner
✓ release вызывается ровно один раз на каждом пути
✓ После release переменная не используется
✓ Одновременно существует только один владелец
✓ access указатель не переживает оригинал
```

---

## Модель вторая — Region

Память выделяется в именованных регионах. Регион уничтожается — вся память внутри уничтожается автоматически. Утечки памяти невозможны структурно.

### Объявление

```
module AudioProcessor uses memory[Region]
    -- весь код внутри живёт по правилам Region
end module
```

### Правила модели Region

```
Правило 1: Каждая переменная кучи принадлежит региону
Правило 2: Регион создаётся явно с именем
Правило 3: При закрытии региона вся его память освобождается
Правило 4: Переменная не может пережить свой регион
Правило 5: Передача as owner между регионами запрещена
Правило 6: Передача as access между регионами разрешена
            если получатель живёт меньше отдающего региона
```

### Пример работы

```
module AudioProcessor uses memory[Region]

    function process_audio_frame
        receives
            pointer[to byte] named raw_input as access
            integer[unsigned, 32bit] named input_size
        returns
            nothing
        on error[processing_failed]
            reject with error[processing_failed]
        body

            open region named frame_region

                declare byte named decoded_audio
                    on heap in region[frame_region] is 0

                declare byte named equalized_audio
                    on heap in region[frame_region] is 0

                call decode_audio
                    with input as access: raw_input
                    with size as copy: input_size
                    with output as access: decoded_audio
                    on error[processing_failed]
                        close region[frame_region]
                        reject with error[processing_failed]
                    on success
                        -- продолжаем
                end call

                call equalize_audio
                    with input as access: decoded_audio
                    with output as access: equalized_audio
                    on error[processing_failed]
                        close region[frame_region]
                        reject with error[processing_failed]
                    on success
                        -- продолжаем
                end call

                call send_to_output
                    with data as access: equalized_audio
                    on error[processing_failed]
                        close region[frame_region]
                        reject with error[processing_failed]
                    on success
                        -- продолжаем
                end call

            close region[frame_region]
            -- decoded_audio и equalized_audio освобождены автоматически

        end body
    end function

end module
```

### Что компилятор проверяет в Region

```
✓ Каждая переменная кучи объявлена в конкретном регионе
✓ Каждый открытый регион имеет закрытие на каждом пути
✓ Переменная не используется после закрытия её региона
✓ access между регионами существует только пока оба региона живы
✓ owner между регионами запрещён
```

---

## Сравнение двух моделей

| | Manual | Region |
|---|---|---|
| Контроль | Максимальный | Средний |
| Безопасность | Высокая при соблюдении правил | Максимальная структурно |
| Утечки памяти | Невозможны если компилятор пропустил | Невозможны структурно |
| Передача между модулями | as owner, as copy, as access | только as access или as copy |
| Подходит для | Драйверы, железо, критичный код | Обработка данных, UI, сети |
| Сложность кода | Выше | Ниже |

---

## Смешение моделей

Модуль написанный на Manual может говорить с модулем на Region — но только через явный шлюз. Это разбирается в разделе 2.3.

Без шлюза — отклонение компиляции:

```
COMPILATION REJECTED
Memory model mismatch detected.

Module [LowLevelDriver] uses memory[Manual]
Module [AudioProcessor] uses memory[Region]

Direct data transfer between different memory models is forbidden.
Declare a gateway between these modules.
See section 2.3
```

---

# C* Language Reference
## Раздел 2 — Память и владение
### 2.3 Владение

---

## Главное правило владения

> В каждый момент времени у каждого куска данных есть ровно один владелец. Всегда. Компилятор отслеживает владельца через весь код. Ситуация когда владельца нет или владельцев двое — невозможна синтаксически.

---

## Три вида отношений с данными

### as copy — получатель получает независимую копию

```
declare integer[signed, 32bit] named original on stack is 42

call process_number
    with value as copy: original
    on error[processing_failed]
        reject with error[processing_failed]
    on success
        -- original всё ещё существует
        -- original всё ещё равен 42
        -- функция работала с копией
end call
```

Владелец `original` не изменился. Функция получила свою копию и владеет ею. Два владельца — но двух разных объектов.

---

### as owner — получатель забирает данные

```
declare integer[signed, 32bit] named buffer on heap is 0

call consume_buffer
    with data as owner: buffer
    on error[processing_failed]
        -- buffer уже не наш. release запрещён.
        reject with error[processing_failed]
    on success
        -- buffer уже не наш. Он живёт внутри функции.
end call

-- Здесь buffer не существует с нашей точки зрения.
-- Попытка использовать buffer — отклонение компиляции.
```

Владение передано. Оригинал мёртв для передающего. Получатель теперь единственный владелец.

---

### as access — получатель получает временный доступ

```
declare byte named audio_data on heap is 0

call analyze_audio
    with data as access: audio_data
    on error[analysis_failed]
        reject with error[analysis_failed]
    on success
        -- audio_data всё ещё наш
        -- функция использовала его но не забрала
end call

-- audio_data живёт. Мы всё ещё владельцы.
release audio_data
```

Владелец не изменился. Функция получила доступ на время своей жизни. Когда функция завершилась — доступ исчез автоматически.

---

## Правила передачи владения

### Правило 1 — Передача as owner необратима

```
declare integer[signed, 32bit] named value on heap is 100

call first_function
    with data as owner: value
    on success
        -- продолжаем
    on error[failed]
        reject with error[failed]
end call

-- value передан. Он не наш.

call second_function
    with data as owner: value   -- ОШИБКА
    on success
        -- сюда не дойдём
    on error[failed]
        reject with error[failed]
end call
```

Сообщение компилятора:
```
COMPILATION REJECTED
Ownership violation detected.

Variable [value] was transferred as owner at: line 4
Variable [value] no longer exists at this scope.
Second transfer attempted at: line 14

A variable can only be transferred once.
```

---

### Правило 2 — access не переживает владельца

```
function bad_access_example
    receives
        nothing
    returns
        pointer[to integer[signed, 32bit]] named dangling_ptr
    body
        declare integer[signed, 32bit] named local on stack is 42
        dangling_ptr is address of local as access

        -- ОШИБКА. dangling_ptr вернётся из функции.
        -- local умрёт при выходе из функции.
        -- access не может пережить владельца.

    end body
end function
```

Сообщение компилятора:
```
COMPILATION REJECTED
Lifetime violation detected.

Variable [local] lives on stack inside function [bad_access_example].
Dies at: end of function body, line 9

Pointer [dangling_ptr] declared as access to [local].
Pointer is returned from function — outlives its target.

access pointers cannot outlive their owner.
```

---

### Правило 3 — Одновременных владельцев не существует

```
declare integer[signed, 32bit] named data on heap is 0

declare pointer[to integer[signed, 32bit]] named ptr_one on stack is null
declare pointer[to integer[signed, 32bit]] named ptr_two on stack is null

ptr_one is address of data as owner
ptr_two is address of data as owner   -- ОШИБКА. data уже передан.
```

Сообщение компилятора:
```
COMPILATION REJECTED
Double ownership detected.

Variable [data] transferred as owner to [ptr_one] at: line 6
Variable [data] no longer exists after line 6.
Second ownership transfer attempted at: line 7.

Only one owner can exist at any moment.
```

---

## Передача владения между функциями

### Функция принимает владение

```
function consume_audio_buffer
    receives
        byte named buffer as owner
    returns
        nothing
    body
        -- buffer наш. Мы обязаны его освободить
        -- или передать дальше as owner.

        call process_raw_bytes
            with data as owner: buffer
            on error[processing_failed]
                -- buffer уже передан. release невозможен.
                reject with error[processing_failed]
            on success
                -- buffer передан дальше. Наша ответственность закончена.
        end call

    end body
end function
```

### Функция возвращает владение

```
function create_audio_buffer
    receives
        integer[unsigned, 32bit] named buffer_size
    returns
        byte named new_buffer as owner
    on error[out_of_memory]
        reject with error[out_of_memory]
    body
        declare byte named buffer on heap is 0

        call allocate_memory
            with size as copy: buffer_size
            on error[out_of_memory]
                reject with error[out_of_memory]
            on success
                buffer is result
        end call

        new_buffer is buffer as owner
        -- владение передано вызывающему коду

    end body
end function
```

Вызов функции которая возвращает владение:

```
declare byte named my_buffer on heap is 0

call create_audio_buffer
    with buffer_size as copy: 4096
    on error[out_of_memory]
        reject with error[out_of_memory]
    on success
        my_buffer is new_buffer as owner
end call

-- my_buffer наш. Мы владельцы. Мы обязаны освободить.
release my_buffer
```

---

## Шлюзы между моделями памяти

Когда два модуля с разными моделями памяти передают данные — нужен шлюз. Шлюз явно описывает как владение переходит из одной модели в другую.

```
gateway LowLevelDriver to AudioProcessor
    transfers
        pointer[to byte] named device_data
    from memory[Manual]
    to memory[Region]
    using region[AudioProcessor.frame_region]
    as access
    on lifetime mismatch
        reject with error[lifetime_incompatible]
end gateway
```

Шлюз проверяет:

```
✓ Тип данных совместим с обеих сторон
✓ Время жизни данных в Manual перекрывает время жизни в Region
✓ Модель передачи совместима с правилами обеих моделей
✓ Если передача невозможна — отклонение с точным указанием причины
```

Без объявленного шлюза — прямая передача между модулями с разными моделями невозможна синтаксически.

---

## Итог — полная картина владения

```
Данные рождаются        → владелец объявлен при создании
Данные передаются       → явно: as copy, as owner, as access
as copy                 → два независимых объекта, два владельца
as owner                → один владелец, оригинал мёртв
as access               → один владелец, получатель имеет доступ
Данные умирают          → release, передача as owner, или конец региона
Между моделями          → только через шлюз
```

Компилятор знает состояние каждой переменной в каждой точке программы. Неопределённого владения не существует.

---
# C* Language Reference
## Раздел 2 — Память и владение
### 2.4 Пользовательские модели памяти

---

## Главное правило пользовательских моделей

> Программист может описать собственную модель памяти. Компилятор строит уровень из этих правил и проходит его. Если на любом пути через код нет выхода — модель отклоняется до компиляции программы.

---

## Структура объявления модели

```
define memory_model[ИмяМодели]

    rules
        rule [имя_правила]
            [описание правила]
        end rule
    end rules

    violations
        on violation[имя_правила]
            reject with error[имя_ошибки]
        end on
    end violations

    transitions
        transition from[состояние_а] to[состояние_б]
            when [условие]
        end transition
    end transitions

end memory_model
```

Три обязательных блока: `rules`, `violations`, `transitions`. Пропустить любой — отклонение компиляции.

---

## Пример — модель RingBuffer

Кольцевой буфер. Фиксированный размер. Новые данные перезаписывают старые при переполнении или останавливаются — программист выбирает.

```
define memory_model[RingBuffer]

    rules

        rule single_owner
            at every moment exactly one owner exists
        end rule

        rule fixed_capacity
            capacity must be declared at model creation
            capacity cannot change after declaration
        end rule

        rule write_position
            write position advances by one after each write
            write position wraps to zero when reaching capacity
        end rule

        rule read_position
            read position advances by one after each read
            read position cannot exceed write position
        end rule

        rule overflow_behavior
            programmer must declare one of
                on overflow: overwrite oldest
                on overflow: reject with error[buffer_full]
                on overflow: block until space available
            end one of
        end rule

        rule release_condition
            buffer releases when owner leaves scope
            all unread data is lost on release
            programmer must acknowledge this explicitly
        end rule

    end rules

    violations

        on violation[single_owner]
            reject with error[double_ownership]
        end on

        on violation[fixed_capacity]
            reject with error[capacity_modification]
        end on

        on violation[read_position]
            reject with error[read_ahead_of_write]
        end on

        on violation[overflow_behavior]
            reject with error[undefined_overflow]
        end on

        on violation[release_condition]
            reject with error[unacknowledged_data_loss]
        end on

    end violations

    transitions

        transition from[empty] to[has_data]
            when write occurs and buffer was empty
        end transition

        transition from[has_data] to[full]
            when write position reaches capacity
        end transition

        transition from[full] to[has_data]
            when overflow_behavior is overwrite oldest
            and write occurs
        end transition

        transition from[full] to[full]
            when overflow_behavior is reject with error[buffer_full]
            and write occurs
            then reject with error[buffer_full]
        end transition

        transition from[has_data] to[empty]
            when read position reaches write position
        end transition

        transition from[any] to[dead]
            when owner leaves scope
            then release all memory
        end transition

    end transitions

end memory_model
```

---

## Как компилятор строит уровень из этих правил

Когда компилятор видит модуль использующий `RingBuffer` — он строит уровень:

```
[Старт]
    ↓
[Узкое место 1] — объявлен ли единственный владелец?
    ↓ да
[Узкое место 2] — объявлена ли ёмкость и неизменна ли она?
    ↓ да
[Узкое место 3] — объявлено ли поведение при переполнении?
    ↓ да
[Узкое место 4] — все пути через код ведут к release?
    ↓ да
[Узкое место 5] — программист подтвердил потерю данных при release?
    ↓ да
[Компиляция разрешена]
```

Если на любом шаге ответ "нет" — уровень умирает там. Компилятор сообщает точно где и почему.

---

## Использование пользовательской модели

```
module AudioEngine uses memory[RingBuffer]
    with capacity: 4096
    with overflow: reject with error[buffer_full]
    acknowledges data loss on release

    function write_audio_sample
        receives
            integer[signed, 16bit] named left_channel
            integer[signed, 16bit] named right_channel
        returns
            nothing
        on error[buffer_full]
            reject with error[buffer_full]
        body

            call write_to_buffer
                with left as copy: left_channel
                on error[buffer_full]
                    reject with error[buffer_full]
                on success
                    -- продолжаем
            end call

            call write_to_buffer
                with right as copy: right_channel
                on error[buffer_full]
                    reject with error[buffer_full]
                on success
                    -- продолжаем
            end call

        end body
    end function

    function read_audio_sample
        receives
            nothing
        returns
            integer[signed, 16bit] named left_channel
            integer[signed, 16bit] named right_channel
        on error[buffer_empty]
            reject with error[buffer_empty]
        body

            call read_from_buffer
                on error[read_ahead_of_write]
                    reject with error[buffer_empty]
                on success
                    left_channel is result
            end call

            call read_from_buffer
                on error[read_ahead_of_write]
                    reject with error[buffer_empty]
                on success
                    right_channel is result
            end call

        end body
    end function

end module
```

---

## Конфликт правил — смерть на уровне

Если правила противоречат друг другу — компилятор находит это до компиляции программы:

```
define memory_model[BadModel]

    rules

        rule single_owner
            at every moment exactly one owner exists
        end rule

        rule free_copying
            data can be copied to any number of receivers as owner
        end rule

    end rules

    -- остальные блоки опущены для краткости

end memory_model
```

Сообщение компилятора:
```
MEMORY MODEL REJECTED
Model named [BadModel] contains conflicting rules.

Level died at step 2 of validation.

Rule [single_owner] requires: exactly one owner at all times.
Rule [free_copying] requires: unlimited owner transfers as owner.

Each copy as owner creates a new owner.
Multiple owners violate rule [single_owner].

These rules cannot coexist.
Remove one rule or redefine ownership in your model.
```

---

## Совместимость пользовательской модели со встроенными

Пользовательская модель может быть объявлена совместимой с встроенной. Это означает что шлюз между ними строится автоматически:

```
define memory_model[RingBuffer]
    compatible with memory[Manual]
        as access only
    compatible with memory[Region]
        as access only
        lifetime of access bounded by region lifetime

    -- правила и переходы...

end memory_model
```

Без объявления совместимости — шлюз строится вручную как в разделе 2.3.

---

## Что компилятор проверяет в пользовательских моделях

```
✓ Три обязательных блока присутствуют: rules, violations, transitions
✓ Каждое правило имеет соответствующее нарушение в блоке violations
✓ Переходы покрывают все возможные состояния
✓ Правила не противоречат друг другу — уровень проходим
✓ Все состояния достижимы хотя бы одним переходом
✓ Существует переход в состояние dead для освобождения памяти
✓ При объявлении совместимости — правила совместимы с целевой моделью
```

---

*# C* Language Reference
## Раздел 2 — Память и владение
### 2.5 Работа с указателями

---

## Главное правило указателей

> Указатель в C* — это не просто адрес. Это адрес плюс знание о том что там живёт, кто владеет, и как долго доступ действителен. Компилятор знает все три вещи в каждой точке программы.

---

## Объявление указателя

Указатель всегда говорит на что он указывает:

```
declare pointer[to integer[signed, 32bit]] named number_ptr on stack is null
declare pointer[to byte] named raw_ptr on heap is null
declare pointer[to AudioSample] named sample_ptr on stack is null
```

Три части обязательны:
```
pointer[to ТИП]     — что живёт по адресу
named ИМЯ           — имя указателя
is null             — начальное значение если адрес неизвестен
```

Просто `pointer` без типа — отклонение компиляции.

---

## Получение адреса

```
declare integer[signed, 32bit] named value on stack is 42
declare pointer[to integer[signed, 32bit]] named value_ptr on stack is null

value_ptr is address of value as access
```

Слова `address of` всегда идут вместе. Получить адрес без указания вида отношения — отклонение компиляции.

Три варианта получения адреса:

```
-- Временный доступ — владелец не меняется
value_ptr is address of value as access

-- Передача владения — оригинал умирает
value_ptr is address of value as owner

-- Копия значения через адрес — создаётся независимая копия
value_ptr is address of value as copy
```

---

## Чтение значения по адресу

```
declare integer[signed, 32bit] named value on stack is 42
declare pointer[to integer[signed, 32bit]] named value_ptr on stack is null
declare integer[signed, 32bit] named read_result on stack is 0

value_ptr is address of value as access

-- Читаем значение по адресу
read_result is value at value_ptr
```

Слова `value at` всегда идут вместе. Это замена оператора `*` из языка C. Один смысл — одно выражение.

---

## Запись значения по адресу

```
declare integer[signed, 32bit] named target on stack is 0
declare pointer[to integer[signed, 32bit]] named target_ptr on stack is null

target_ptr is address of target as access

-- Записываем значение по адресу
value at target_ptr is 100

-- target теперь равен 100
```

---

## Обязательная проверка на null

Каждый раз перед использованием указателя — проверка. Без исключений.

```
declare pointer[to integer[signed, 32bit]] named data_ptr on stack is null

-- Использование без проверки — отклонение компиляции:
read_result is value at data_ptr

-- Правильно:
if data_ptr is null
    reject with error[null_pointer_access]
end if

read_result is value at data_ptr
```

Компилятор отслеживает была ли проверка на null перед каждым использованием. Это часть уровня — узкое место которое нельзя обойти.

Сообщение компилятора при отсутствии проверки:
```
COMPILATION REJECTED
Null check missing.

Pointer [data_ptr] declared as null at: line 1
Pointer used without null check at: line 4

Every pointer must be checked for null before use.
```

---

## Указатель после проверки

Если компилятор видит проверку на null — внутри блока проверки повторная проверка не нужна:

```
if data_ptr is not null

    -- здесь компилятор знает что data_ptr не null
    -- повторная проверка не требуется

    read_result is value at data_ptr
    value at data_ptr is read_result plus 1

end if
```

За пределами блока `if` — снова требуется проверка если указатель мог измениться.

---

## Арифметика адресов

Арифметика адресов — перемещение указателя по памяти — разрешена только явно и только для указателей на массивы или сырые байты.

### Объявление указателя с арифметикой

```
declare pointer[to byte, arithmetic allowed] named buffer_ptr on stack is null
```

Без слов `arithmetic allowed` — арифметика запрещена. Попытка сдвинуть обычный указатель — отклонение компиляции.

### Перемещение указателя

```
declare byte named audio_buffer on heap is 0
declare pointer[to byte, arithmetic allowed] named read_ptr on stack is null
declare integer[unsigned, 32bit] named offset on stack is 0

read_ptr is address of audio_buffer as access

-- Сдвиг вперёд
move read_ptr forward by 1
move read_ptr forward by offset

-- Сдвиг назад
move read_ptr backward by 1
move read_ptr backward by offset
```

Слово `move` всегда с направлением и величиной. Никакого `ptr++` или `ptr + n`.

### Проверка границ при арифметике

Каждое перемещение указателя обязано иметь проверку границ:

```
declare byte named audio_buffer on heap is 0
declare pointer[to byte, arithmetic allowed] named read_ptr on stack is null
declare integer[unsigned, 32bit] named buffer_end on stack is 4096

read_ptr is address of audio_buffer as access

move read_ptr forward by 512
    on out of bounds[buffer_end]
        reject with error[buffer_overflow]
```

Блок `on out of bounds` обязателен при каждом `move`. Пропустить — отклонение компиляции.

---

## Указатель на структуру

```
declare AudioSample named current_sample on heap is
    left_channel: 0
    right_channel: 0
    timestamp: 0
    is_silent: true
end declare

declare pointer[to AudioSample] named sample_ptr on stack is null

sample_ptr is address of current_sample as access

if sample_ptr is not null

    -- Доступ к полям через указатель
    declare integer[signed, 16bit] named left on stack is 0
    left is field left_channel at sample_ptr

    -- Запись в поле через указатель
    field left_channel at sample_ptr is 1024
    field is_silent at sample_ptr is false

end if
```

Слова `field [имя] at` заменяют оператор `->` из языка C. Один смысл — одно выражение.

---

## Указатель на функцию

Указатель может хранить адрес функции. Это позволяет передавать функции как параметры.

```
-- Объявление типа функции
define type[AudioProcessor] as function
    receives
        pointer[to byte] named data as access
        integer[unsigned, 32bit] named size
    returns
        nothing
    on error[processing_failed]
        reject with error[processing_failed]
end type

-- Объявление указателя на функцию
declare pointer[to AudioProcessor] named processor_ptr on stack is null

-- Присвоение адреса функции
processor_ptr is address of process_raw_audio

-- Вызов через указатель
if processor_ptr is not null
    call via processor_ptr
        with data as access: audio_buffer
        with size as copy: buffer_size
        on error[processing_failed]
            reject with error[processing_failed]
        on success
            -- продолжаем
    end call
end if
```

Слова `call via` означают вызов через указатель. Отличается от обычного `call` — компилятор знает что это косвенный вызов.

---

## Что компилятор проверяет в указателях

```
✓ Каждый указатель объявлен с конкретным типом
✓ Каждый указатель проверен на null перед использованием
✓ access указатель не переживает владельца
✓ owner указатель единственный владелец
✓ Арифметика разрешена только при явном объявлении
✓ Каждое перемещение имеет проверку границ
✓ Доступ к полям структуры через field [имя] at
✓ Вызов через указатель через call via
```

---

## Раздел 2 завершён

```
2.1 Модель памяти C*              ✓
2.2 Встроенные модели памяти      ✓
2.3 Владение                      ✓
2.4 Пользовательские модели       ✓
2.5 Работа с указателями          ✓
```

Мы описали полную систему памяти C*. Каждая переменная имеет место, владельца и момент смерти. Компилятор знает всё это до запуска.

---
# C* Language Reference
## Раздел 3 — Управление потоком и логика
### 3.1 Условия и ветвление

---

## Главное правило условий

> Каждое условие в C* читается как утверждение на естественном языке. Компилятор не допускает условий которые можно понять двояко. Сложные условия разбиваются на именованные части.

---

## Простое условие

```
if current_temperature is greater than 100
    reject with error[overheating]
end if
```

Одно условие — одна строка. Читается вслух без запинки.

---

## Все операторы сравнения

```
if value is equal to 0
if value is not equal to 0
if value is greater than 0
if value is less than 0
if value is greater or equal to 0
if value is less or equal to 0
if value is null
if value is not null
if value is true
if value is false
```

Каждый оператор — полная фраза. Никаких символов. Никаких сокращений.

---

## Сложное условие — блок check

Когда условий несколько — они выносятся в блок `check`. Каждое условие на отдельной строке:

```
if check
    current_temperature is greater than 0
    and current_temperature is less than 100
    and sensor_status is equal to active
    and last_reading_age is less or equal to max_reading_age
end check
    log_message receives "All sensors normal" and 1
end if
```

Читается как список требований. Все требования должны быть выполнены одновременно.

### check с логическим ИЛИ

```
if check
    connection_state is equal to connected
    or connection_state is equal to reconnecting
end check
    process_incoming_data
end if
```

### Смешение И и ИЛИ — вложенный check

```
if check
    device_is_ready is equal to true
    and check
        input_mode is equal to analog
        or input_mode is equal to digital
    end check
    and buffer_size is greater than 0
end check
    begin_data_acquisition
end if
```

Вложенный `check` — это группа. Читается как:
"устройство готово И (режим аналоговый ИЛИ цифровой) И буфер не пуст"

---

## Именованные условия

Если одно и то же сложное условие используется в нескольких местах — оно получает имя:

```
define condition[SystemIsReady]
    check
        device_is_ready is equal to true
        and connection_state is equal to connected
        and buffer_size is greater than 0
        and error_count is equal to 0
    end check
end condition

-- Использование:
if condition[SystemIsReady]
    begin_processing
end if

-- В другом месте:
if not condition[SystemIsReady]
    reject with error[system_not_ready]
end if
```

Именованное условие читается как слово. Детали скрыты в объявлении — но всегда доступны для чтения.

---

## Ветвление — if с otherwise

```
if audio_level is greater than max_safe_level
    log_message receives "Audio clipping detected" and 2
    reduce_audio_level receives max_safe_level
otherwise
    log_message receives "Audio level normal" and 1
end otherwise
end if
```

### Цепочка условий

```
if connection_state is equal to connected
    process_incoming_data
otherwise if connection_state is equal to connecting
    log_message receives "Waiting for connection" and 1
    wait_for_connection
otherwise if connection_state is equal to disconnected
    log_message receives "Connection lost" and 2
    attempt_reconnection
otherwise
    reject with error[unknown_connection_state]
end otherwise
end otherwise if
end otherwise if
end if
```

Каждый блок закрывается отдельно. Порядок закрытия — от внутреннего к внешнему.

---

## Условие на перечислении

Когда переменная является перечислением — C* требует покрытия всех значений:

```
define type[DeviceState]
    can be
        initializing
        ready
        processing
        error
        shutdown
    end can be
end type

declare DeviceState named current_state is initializing

match current_state
    when initializing
        run_initialization_sequence
    when ready
        await_commands
    when processing
        continue_processing
    when error
        handle_device_error
    when shutdown
        release_all_resources
end match
```

Блок `match` требует ветки для каждого значения перечисления. Пропустить хотя бы одно — отклонение компиляции:

```
COMPILATION REJECTED
Incomplete match detected.

Type [DeviceState] has 5 possible values.
match block covers 4 values.
Missing branch for value: shutdown

Every possible value must have a branch in match.
```

---

## Условие с проверкой типа

Когда указатель может указывать на разные типы — проверка типа обязательна:

```
declare pointer[to AudioSample] named sample_ptr on stack is null

if sample_ptr is not null
    if type at sample_ptr is equal to AudioSample
        declare integer[signed, 16bit] named left on stack is 0
        left is field left_channel at sample_ptr
    otherwise
        reject with error[unexpected_type]
    end otherwise
    end if
end if
```

---

## Что компилятор проверяет в условиях

```
✓ Каждое условие читается однозначно
✓ Смешение and и or только через вложенный check
✓ match покрывает все значения перечисления
✓ Именованные условия объявлены до использования
✓ Каждый блок otherwise закрыт до закрытия if
✓ Условие на null всегда предшествует использованию указателя
```

---
# C* Language Reference
## Раздел 3 — Управление потоком и логика
### 3.2 Циклы и повторение

---

## Главное правило циклов

> Каждый цикл в C* имеет явно объявленное условие остановки. Бесконечный цикл без явного объявления — отклонение компиляции. Компилятор должен знать как и когда цикл завершится.

---

## Базовый цикл — repeat while

```
declare integer[unsigned, 32bit] named current_index on stack is 0
declare integer[unsigned, 32bit] named total_count on stack is 100

repeat while current_index is less than total_count
    process_item receives current_index
    current_index is current_index plus 1
end repeat
```

Условие проверяется до каждой итерации. Если условие ложно с самого начала — тело цикла не выполняется ни разу.

---

## Цикл с проверкой после итерации

Иногда нужно выполнить тело хотя бы один раз:

```
declare boolean named data_is_valid on stack is false

repeat
    declare byte named incoming_byte on stack is 0
    incoming_byte is read_next_byte
    data_is_valid is validate_byte receives incoming_byte
until data_is_valid is equal to true
```

Условие проверяется после каждой итерации. Тело выполняется минимум один раз.

---

## Явно бесконечный цикл

Бесконечный цикл разрешён но обязан быть объявлен явно:

```
repeat forever
    stops when check
        shutdown_signal is equal to true
        or critical_error is equal to true
    end check

    declare byte named audio_sample on stack is 0
    audio_sample is read_audio_input
    process_audio_sample receives audio_sample

end repeat
```

Блок `stops when` обязателен внутри `repeat forever`. Без него — отклонение компиляции. Программист обязан описать условие при котором цикл завершится даже если оно никогда не наступит.

Сообщение компилятора:
```
COMPILATION REJECTED
Infinite loop without stop condition.

repeat forever at: line 4
No stops when block declared.

Infinite loops must declare a stop condition.
Even if the condition is never expected to trigger.
```

---

## Цикл по диапазону

Когда нужно пройти по числовому диапазону:

```
repeat for current_index
    from 0
    to buffer_size
    step 1
    stops when current_index is equal to buffer_size
    body
        process_byte receives buffer at current_index
    end body
end repeat
```

Все четыре части обязательны: `from`, `to`, `step`, `stops when`. Пропустить любую — отклонение компиляции.

Шаг может быть отрицательным — обратный проход:

```
repeat for current_index
    from buffer_size
    to 0
    step minus 1
    stops when current_index is equal to 0
    body
        process_byte receives buffer at current_index
    end body
end repeat
```

---

## Цикл по коллекции

Когда нужно пройти по всем элементам:

```
declare AudioSample named sample_collection on heap is 0
declare integer[unsigned, 32bit] named collection_size on stack is 64

repeat for each current_sample
    in collection[sample_collection]
    of size collection_size
    body
        if check
            current_sample.is_silent is equal to false
            and current_sample.left_channel is not equal to 0
        end check
            process_audio_sample receives current_sample as access
        end if
    end body
end repeat
```

Компилятор знает размер коллекции и гарантирует что цикл не выйдет за её границы.

---

## Управление циклом

### Выход из цикла — stop

```
declare integer[unsigned, 32bit] named search_index on stack is 0
declare boolean named target_found on stack is false

repeat while search_index is less than buffer_size
    if buffer at search_index is equal to target_value
        target_found is true
        stop
    end if
    search_index is search_index plus 1
end repeat
```

`stop` немедленно завершает ближайший цикл. Выполнение продолжается после `end repeat`.

### Переход к следующей итерации — skip

```
declare integer[unsigned, 32bit] named current_index on stack is 0

repeat while current_index is less than buffer_size
    if buffer at current_index is equal to padding_byte
        current_index is current_index plus 1
        skip
    end if
    process_byte receives buffer at current_index
    current_index is current_index plus 1
end repeat
```

`skip` немедленно переходит к проверке условия следующей итерации.

### Выход из вложенных циклов

Выйти из двух циклов одним `stop` запрещено. Вместо этого — именованный выход:

```
declare integer[unsigned, 32bit] named outer_index on stack is 0
declare integer[unsigned, 32bit] named inner_index on stack is 0
declare boolean named target_found on stack is false

repeat while outer_index is less than row_count
    named outer_loop

    inner_index is 0

    repeat while inner_index is less than column_count
        named inner_loop

        if check
            matrix at outer_index at inner_index
            is equal to target_value
        end check
            target_found is true
            stop loop[outer_loop]
        end if

        inner_index is inner_index plus 1
    end repeat

    outer_index is outer_index plus 1
end repeat
```

Слова `stop loop[имя]` — выход из конкретного именованного цикла. Читается явно. Никакой магии с `goto`.

---

## Счётчик итераций

Каждый цикл имеет встроенный счётчик итераций:

```
repeat while has_more_data is equal to true

    if iteration count is greater than max_iterations
        reject with error[iteration_limit_exceeded]
    end if

    process_next_data_chunk

end repeat
```

`iteration count` — зарезервированное выражение внутри любого цикла. Всегда доступно. Всегда точно.

---

## Защита от бесконечного выполнения

Для критичных циклов можно объявить максимальное число итераций:

```
repeat while sensor_is_calibrating is equal to true
    maximum iterations 1000
    on limit reached
        reject with error[calibration_timeout]

    read_sensor_data
    adjust_calibration_parameters

end repeat
```

Блок `maximum iterations` необязателен — но если объявлен, компилятор гарантирует что блок `on limit reached` присутствует. Без него — отклонение компиляции.

---

## Что компилятор проверяет в циклах

```
✓ repeat while имеет достижимое условие остановки
✓ repeat forever имеет блок stops when
✓ repeat for имеет from, to, step и stops when
✓ repeat for each знает размер коллекции
✓ stop и skip действуют на ближайший цикл
✓ stop loop[имя] действует на именованный цикл
✓ maximum iterations всегда имеет on limit reached
✓ Счётчик итераций доступен внутри любого цикла
✓ Вложенные циклы выходят только через именованный stop
```

---

*# C* Language Reference
## Раздел 3 — Управление потоком и логика
### 3.3 Система ошибок

---

## Главное правило системы ошибок

> В C* ошибка — это не катастрофа. Это запланированное событие которое программист описал заранее. Если программа скомпилировалась — каждая возможная ошибка уже имеет обработчик. Неожиданных ошибок не существует.

---

## Два вида проблем

### Ошибки компиляции — уровень не пройден

Программа не скомпилировалась. Код содержит нарушения правил языка. Делятся на два типа:

**Синтаксическая ошибка** — компилятор не понимает что написано. Остановка немедленная. Одна ошибка. Жди исправления.

```
SYNTAX ERROR
Cannot parse expression at: line 14

Expected: named
Found: "="

declare integer[signed, 32bit] = counter is 0
                               ^
Correct form: declare integer[signed, 32bit] named counter is 0
```

**Ошибка уровня** — код понятен но правила нарушены. Компилятор показывает все нарушения уровня за один проход:

```
LEVEL VIOLATIONS FOUND — 3 errors

Error 1: Null check missing
    Pointer [buffer_ptr] used without null check at: line 23

Error 2: Ownership violation
    Variable [audio_data] transferred as owner at: line 31
    Second transfer attempted at: line 47

Error 3: Lifetime violation
    Variable [local_value] on stack dies at: line 38
    Pointer [result_ptr] outlives it — returned at: line 40

Fix all violations before compilation can proceed.
```

Все три показаны сразу. Программист видит полную картину.

---

### Ошибки выполнения — запланированные события

Программа скомпилировалась и работает. Что-то пошло не так — но это было предусмотрено. Каждая ошибка выполнения это событие которое программист описал в блоке `on error`.

---

## Встроенные ошибки

C* поставляется с набором встроенных ошибок покрывающих основные ситуации:

```
-- Память
error[OutOfMemory]
error[NullPointerAccess]
error[BufferOverflow]
error[DoubleFree]
error[LifetimeViolation]

-- Арифметика
error[ArithmeticOverflow]
error[DivisionByZero]
error[ValueTooLarge]
error[ValueTooSmall]

-- Данные
error[InvalidValue]
error[TypeMismatch]
error[UnexpectedType]

-- Система
error[ResourceUnavailable]
error[DeviceNotFound]
error[PermissionDenied]
error[Timeout]

-- Логика
error[InvalidState]
error[UnknownState]
error[IterationLimitExceeded]
```

---

## Пользовательские ошибки

Программист создаёт свои ошибки явным объявлением:

```
define error[AudioDeviceNotFound]
    message "Audio device was not found in the system"
    severity critical
    recoverable false
end error

define error[BufferUnderrun]
    message "Audio buffer ran out of data during playback"
    severity warning
    recoverable true
end error

define error[CalibrationTimeout]
    message "Sensor calibration did not complete in time"
    severity critical
    recoverable true
end error
```

Три обязательных поля:

**message** — человекочитаемое описание. Попадёт в лог и отчёт об ошибке.

**severity** — важность. Четыре уровня:
```
severity info        -- информация, не проблема
severity warning     -- предупреждение, можно продолжать
severity critical    -- серьёзная проблема, требует внимания
severity fatal       -- невозможно продолжать
```

**recoverable** — можно ли продолжить работу после этой ошибки:
```
recoverable true     -- программа может продолжить
recoverable false    -- программа должна остановиться
```

---

## Иерархия ошибок

Ошибки могут наследоваться. Родительская ошибка объединяет группу похожих ошибок:

```
define error[ResourceUnavailable]
    message "A required resource is unavailable"
    severity critical
    recoverable false
end error

define error[AudioDeviceNotFound]
    extends error[ResourceUnavailable]
    message "Audio device was not found in the system"
end error

define error[MicrophoneNotFound]
    extends error[AudioDeviceNotFound]
    message "Microphone was not found in the system"
end error

define error[SpeakerNotFound]
    extends error[AudioDeviceNotFound]
    message "Speaker was not found in the system"
end error
```

Дочерняя ошибка наследует `severity` и `recoverable` от родителя если не переопределяет их.

Обработка родительской ошибки ловит все дочерние:

```
call initialize_audio_system
    on error[ResourceUnavailable]
        -- поймает AudioDeviceNotFound
        -- поймает MicrophoneNotFound
        -- поймает SpeakerNotFound
        -- и любую другую дочернюю ошибку
        log_message receives "Audio resource unavailable" and 3
        reject with error[SystemInitializationFailed]
    on success
        -- продолжаем
end call
```

---

## Распространение ошибок

Когда функция A вызывает функцию B которая вызывает функцию C — и C выбрасывает ошибку — ошибка распространяется явно через каждый уровень.

### Явная передача ошибки наверх

```
function initialize_microphone
    receives
        nothing
    returns
        nothing
    on error[MicrophoneNotFound]
        reject with error[MicrophoneNotFound]
    body
        call detect_audio_device
            with device_type as copy: microphone
            on error[AudioDeviceNotFound]
                reject with error[MicrophoneNotFound]
            on success
                -- продолжаем
        end call
    end body
end function
```

### Преобразование ошибки

Иногда нужно поймать одну ошибку и выбросить другую:

```
function load_configuration
    receives
        text named config_path
    returns
        nothing
    on error[ConfigurationInvalid]
        reject with error[ConfigurationInvalid]
    on error[SystemInitializationFailed]
        reject with error[SystemInitializationFailed]
    body
        call open_file
            with path as copy: config_path
            on error[FileNotFound]
                -- преобразуем ошибку файла в ошибку конфигурации
                reject with error[ConfigurationInvalid]
            on error[PermissionDenied]
                reject with error[SystemInitializationFailed]
            on success
                -- продолжаем
        end call
    end body
end function
```

---

## Обработка ошибок — полная картина

### Обработка с восстановлением

```
declare integer[unsigned, 32bit] named retry_count on stack is 0
declare boolean named connected on stack is false

repeat while connected is equal to false
    maximum iterations 3
    on limit reached
        reject with error[ConnectionFailed]

    call connect_to_device
        on error[DeviceNotFound]
            if retry_count is less than 3
                retry_count is retry_count plus 1
                wait_milliseconds receives 1000
                skip
            end if
            reject with error[ConnectionFailed]
        on error[Timeout]
            retry_count is retry_count plus 1
            skip
        on success
            connected is true
    end call

end repeat
```

### Обработка с контекстом

Ошибка может нести дополнительную информацию:

```
define error[ValueOutOfRange]
    message "Value is outside acceptable range"
    severity warning
    recoverable true
    carries
        integer[signed, 32bit] named actual_value
        integer[signed, 32bit] named minimum_allowed
        integer[signed, 32bit] named maximum_allowed
    end carries
end error

-- Выброс ошибки с контекстом:
reject with error[ValueOutOfRange]
    actual_value: current_reading
    minimum_allowed: min_threshold
    maximum_allowed: max_threshold
end reject

-- Обработка ошибки с контекстом:
call validate_sensor_reading
    on error[ValueOutOfRange]
        log_message receives error.message and 2
        log_integer receives error.actual_value
        log_integer receives error.minimum_allowed
        log_integer receives error.maximum_allowed
        apply_safe_default_value
    on success
        -- продолжаем
end call
```

---

## Финальный обработчик

Иногда нужно выполнить код независимо от того была ошибка или нет. Например освободить ресурс:

```
function process_audio_file
    receives
        text named file_path
    returns
        nothing
    on error[FileNotFound]
        reject with error[FileNotFound]
    on error[ProcessingFailed]
        reject with error[ProcessingFailed]
    body

        declare byte named file_data on heap is 0

        call open_audio_file
            with path as copy: file_path
            on error[FileNotFound]
                reject with error[FileNotFound]
            on success
                file_data is result as owner
        end call

        call process_raw_audio
            with data as access: file_data
            on error[ProcessingFailed]
                -- выполнится always перед reject
                reject with error[ProcessingFailed]
            on success
                -- продолжаем
        end call

    always
        -- выполняется всегда — и при ошибке и при успехе
        if file_data is not null
            release file_data
        end if
    end always

    end body
end function
```

Блок `always` — гарантированное выполнение. Память будет освобождена даже если функция завершилась ошибкой.

---

## Что компилятор проверяет в системе ошибок

```
✓ Каждая пользовательская ошибка имеет message, severity, recoverable
✓ Дочерние ошибки объявлены после родительских
✓ Каждый вызов функции обрабатывает все её возможные ошибки
✓ Ошибка с carries обрабатывается с доступом к её полям
✓ fatal ошибки не имеют recoverable true
✓ Блок always присутствует когда есть ресурсы требующие освобождения
✓ Распространение ошибок явное на каждом уровне
✓ Все пути через код завершаются либо успехом либо объявленной ошибкой
```

---

# C* Language Reference
## Раздел 3 — Управление потоком и логика
### 3.4 Модули и границы

---

## Главное правило модулей

> Модуль в C* — это самостоятельная единица с явно объявленными границами. Что входит, что выходит, от чего зависит — всё написано явно. Компилятор не допускает скрытых зависимостей.

---

## Структура модуля

```
module AudioEngine
    version[1.0]
    uses memory[Region]
    depends on module[LowLevelDriver]
    depends on module[StdMath]

    -- объявления типов и ошибок
    -- приватные функции
    -- публичные функции

end module
```

Четыре обязательных поля в заголовке:
```
module [имя]            — имя модуля
version[X.Y]            — версия
uses memory[модель]     — модель памяти
depends on module[...]  — зависимости
```

Нет зависимостей — пишется явно:
```
module StdMath
    version[1.0]
    uses memory[Manual]
    depends on nothing
```

---

## Три уровня видимости

### private — только внутри модуля

```
private function validate_audio_format
    receives
        pointer[to byte] named raw_data as access
        integer[unsigned, 32bit] named data_size
    returns
        boolean named format_is_valid
    body
        -- детали реализации скрыты от внешнего мира
    end body
end function
```

Попытка вызвать `private` функцию из другого модуля — отклонение компиляции:

```
COMPILATION REJECTED
Visibility violation.

Function [validate_audio_format] in module [AudioEngine]
is declared private.
Access attempted from module [UserInterface] at: line 34

Private members are only accessible within their module.
```

---

### internal — только внутри карты модулей

```
internal function sync_with_driver
    receives
        integer[unsigned, 32bit] named sync_token
    returns
        nothing
    on error[SyncFailed]
        reject with error[SyncFailed]
    body
        -- доступно модулям в одной карте
        -- недоступно внешним потребителям
    end body
end function
```

`internal` функция видна только модулям объявленным в одном `.cstar-map` файле. Это позволяет модулям одного проекта общаться между собой не открывая детали внешнему миру.

---

### public — доступно всем

```
public function write_audio_sample
    receives
        integer[signed, 16bit] named left_channel
        integer[signed, 16bit] named right_channel
    returns
        nothing
    on error[BufferFull]
        reject with error[BufferFull]
    on error[DeviceNotReady]
        reject with error[DeviceNotReady]
    body
        call validate_audio_format
            with raw_data as access: internal_buffer
            with data_size as copy: 4
            on error[InvalidValue]
                reject with error[DeviceNotReady]
            on success
                -- продолжаем
        end call

        call write_to_hardware_buffer
            with left as copy: left_channel
            with right as copy: right_channel
            on error[BufferFull]
                reject with error[BufferFull]
            on success
                -- продолжаем
        end call

    end body
end function
```

---

## Подключение модулей — три способа

### Способ 1 — По имени

```
program AudioSystem

    use module[AudioEngine]
    use module[StdMath]
    use module[StdMemory]

    body
        -- код
    end body

end program
```

Компилятор ищет модуль по имени в системном реестре C*. Подходит для стандартных и установленных модулей.

---

### Способ 2 — По пути к файлу

```
program AudioSystem

    use module at path["./audio/AudioEngine.cstar"]
    use module at path["./drivers/LowLevelDriver.cstar"]
    use module at path["/system/std/StdMath.cstar"]

    body
        -- код
    end body

end program
```

Подходит когда модуль не зарегистрирован глобально. Путь может быть относительным или абсолютным.

---

### Способ 3 — Карта модулей

Отдельный файл `.cstar-map` описывает всю структуру проекта. Самый мощный инструмент:

```
module map[ProjectAudioSystem]
    version[1.0]
    author["Project Team"]

    -- Регистрация модулей
    register module[AudioEngine]
        at path["./audio/AudioEngine.cstar"]
        version[1.0]
        required true
    end register

    register module[LowLevelDriver]
        at path["./drivers/LowLevelDriver.cstar"]
        version[1.4]
        required true
    end register

    register module[AudioEffects]
        at path["./effects/AudioEffects.cstar"]
        version[2.1]
        required false
    end register

    register module[StdMath]
        at path["/system/std/StdMath.cstar"]
        version[1.0]
        required true
    end register

    -- Описание связей
    connect module[AudioEngine]
        depends on module[LowLevelDriver]
            through gateway[DriverToEngine]
        depends on module[StdMath]
            direct
        depends on module[AudioEffects]
            optional
            through gateway[EffectsToEngine]
    end connect

    connect module[LowLevelDriver]
        depends on module[StdMath]
            direct
    end connect

    -- Описание шлюзов
    gateway[DriverToEngine]
        from module[LowLevelDriver] memory[Manual]
        to module[AudioEngine] memory[Region]
        transfers
            pointer[to byte] as access only
            integer[unsigned, 32bit] as copy only
        end transfers
        lifetime
            access bounded by region[AudioEngine.frame_region]
        end lifetime
    end gateway

    gateway[EffectsToEngine]
        from module[AudioEffects] memory[Region]
        to module[AudioEngine] memory[Region]
        transfers
            pointer[to AudioSample] as access only
        end transfers
        lifetime
            access bounded by shorter of two regions
        end lifetime
    end gateway

end module map
```

---

## Необязательные зависимости

Модуль может зависеть от другого модуля необязательно. Тогда он обязан проверить доступность:

```
module AudioEngine
    version[1.0]
    uses memory[Region]
    depends on module[LowLevelDriver]
    depends on module[AudioEffects] optional

    public function initialize
        receives
            nothing
        returns
            nothing
        on error[InitializationFailed]
            reject with error[InitializationFailed]
        body

            call setup_hardware_driver
                on error[InitializationFailed]
                    reject with error[InitializationFailed]
                on success
                    -- продолжаем
            end call

            if module[AudioEffects] is available
                call initialize_effects_pipeline
                    on error[InitializationFailed]
                        -- эффекты недоступны — продолжаем без них
                        log_message receives "Effects unavailable" and 1
                    on success
                        log_message receives "Effects initialized" and 1
                end call
            otherwise
                log_message receives "Running without effects" and 1
            end otherwise
            end if

        end body
    end function

end module
```

---

## Циклические зависимости

Модуль A зависит от модуля B который зависит от модуля A — запрещено:

```
COMPILATION REJECTED
Circular dependency detected.

module [AudioEngine] depends on module [AudioEffects]
module [AudioEffects] depends on module [AudioEngine]

Circular dependencies are forbidden.
Redesign the dependency graph so all connections flow one way.
```

Зависимости в C* всегда однонаправлены. Это гарантирует что порядок компиляции всегда определён.

---

## Версионирование

Если модуль требует конкретную версию зависимости:

```
module AudioEngine
    version[1.0]
    uses memory[Region]
    depends on module[LowLevelDriver] version[1.4]
    depends on module[StdMath] version[1.0] or higher
```

При несовпадении версий — отклонение компиляции:

```
COMPILATION REJECTED
Version mismatch.

module [AudioEngine] requires module [LowLevelDriver] version [1.4]
Found module [LowLevelDriver] version [1.2]

Update [LowLevelDriver] or change the version requirement.
```

---

## Инициализация и завершение модуля

Каждый модуль может объявить код который выполняется при загрузке и выгрузке:

```
module AudioEngine
    version[1.0]
    uses memory[Region]
    depends on module[LowLevelDriver]

    on module load
        log_message receives "AudioEngine initializing" and 1
        call setup_internal_buffers
            on error[OutOfMemory]
                reject with error[ModuleLoadFailed]
            on success
                -- продолжаем
        end call
    end on

    on module unload
        call release_all_buffers
            on error[ReleaseFailed]
                log_message receives "Buffer release failed" and 2
            on success
                log_message receives "AudioEngine shutdown complete" and 1
        end call
    end on

    -- функции модуля

end module
```

Блок `on module load` — выполняется когда модуль подключается.
Блок `on module unload` — выполняется когда модуль отключается или программа завершается.

Оба блока необязательны. Но если объявлен `on module load` с выделением ресурсов — компилятор требует `on module unload` с их освобождением.

---

## Что компилятор проверяет в модулях

```
✓ Каждый модуль имеет имя, версию, модель памяти, зависимости
✓ Каждая функция имеет явный уровень видимости
✓ private функции недоступны снаружи модуля
✓ internal функции доступны только в пределах карты модулей
✓ Циклические зависимости запрещены
✓ Версии зависимостей совпадают с требованиями
✓ Необязательные зависимости проверяются перед использованием
✓ on module load с ресурсами требует on module unload
✓ Передача данных между моделями памяти только через шлюз
✓ Шлюзы объявлены в карте модулей
```

---

*Готово. Переходим к 3.5 — Битовые операции?*

# C* Language Reference
## Раздел 3 — Управление потоком и логика
### 3.5 Битовые операции

---

## Главное правило битовых операций

> Битовые операции в C* явно отделены от логических и арифметических. Слово `bits` сигнализирует компилятору — здесь работа с отдельными битами, не с числами и не с условиями. Один контекст — одно обозначение.

---

## Почему это важно

В C один символ `&` означает три разные вещи:
```c
a & b       // побитовое И
&value      // адрес переменной
f(a) && g() // логическое И
```

В C* каждое из этих понятий имеет своё уникальное выражение. Путаница невозможна структурно.

---

## Базовые битовые операции

### Побитовое И

```
declare integer[unsigned, 8bit] named mask on stack is 0
declare integer[unsigned, 8bit] named flags on stack is 0
declare integer[unsigned, 8bit] named result on stack is 0

mask is 0b00001111
flags is 0b10101010

result is bits of flags and bits of mask
-- result равен 0b00001010
```

### Побитовое ИЛИ

```
declare integer[unsigned, 8bit] named base_flags on stack is 0b10100000
declare integer[unsigned, 8bit] named new_flag on stack is 0b00000001
declare integer[unsigned, 8bit] named combined on stack is 0

combined is bits of base_flags or bits of new_flag
-- combined равен 0b10100001
```

### Побитовое исключающее ИЛИ

```
declare integer[unsigned, 8bit] named value_a on stack is 0b11001100
declare integer[unsigned, 8bit] named value_b on stack is 0b10101010
declare integer[unsigned, 8bit] named toggled on stack is 0

toggled is bits of value_a xor bits of value_b
-- toggled равен 0b01100110
```

### Побитовое НЕ

```
declare integer[unsigned, 8bit] named original on stack is 0b10110100
declare integer[unsigned, 8bit] named inverted on stack is 0

inverted is bits not of original
-- inverted равен 0b01001011
```

---

## Запись числовых литералов

C* поддерживает три формы записи числовых литералов для удобства битовой работы:

```
-- Двоичная форма — префикс 0b
declare integer[unsigned, 8bit] named binary_val on stack is 0b10110101

-- Шестнадцатеричная форма — префикс 0x
declare integer[unsigned, 8bit] named hex_val on stack is 0xFF

-- Десятичная форма — без префикса
declare integer[unsigned, 8bit] named decimal_val on stack is 255
```

Все три формы описывают одно и то же значение. Выбор формы зависит от контекста — там где важна битовая структура числа используется двоичная или шестнадцатеричная форма.

---

## Сдвиги

### Сдвиг влево

```
declare integer[unsigned, 32bit] named value on stack is 1
declare integer[unsigned, 32bit] named shifted on stack is 0

shifted is bits of value shifted left by 4
-- shifted равен 16
-- эквивалентно умножению на 2 в степени 4
```

### Сдвиг вправо

```
declare integer[unsigned, 32bit] named value on stack is 256
declare integer[unsigned, 32bit] named shifted on stack is 0

shifted is bits of value shifted right by 4
-- shifted равен 16
-- эквивалентно делению на 2 в степени 4
```

### Сдвиг с проверкой

Сдвиг на величину большую чем размер типа — отклонение компиляции:

```
declare integer[unsigned, 8bit] named value on stack is 1

-- ОШИБКА — сдвиг на 8 для 8-битного типа бессмысленен
shifted is bits of value shifted left by 8
```

Сообщение компилятора:
```
COMPILATION REJECTED
Invalid shift amount.

Type [integer[unsigned, 8bit]] has 8 bits.
Shift amount [8] equals or exceeds type size.
Valid shift range for this type: 0 to 7.
```

---

## Работа с отдельными битами

### Проверка бита

```
declare integer[unsigned, 8bit] named status_flags on stack is 0b10110101

-- Проверить установлен ли бит номер 2
if bit 2 of status_flags is set
    log_message receives "Bit 2 is active" and 1
end if

-- Проверить сброшен ли бит номер 3
if bit 3 of status_flags is clear
    log_message receives "Bit 3 is inactive" and 1
end if
```

Биты нумеруются с нуля от младшего к старшему. Бит 0 — самый правый.

### Установка бита

```
declare integer[unsigned, 8bit] named control_register on stack is 0b00000000

-- Установить бит номер 5
set bit 5 of control_register
-- control_register теперь равен 0b00100000

-- Установить несколько битов
set bit 0 of control_register
set bit 1 of control_register
-- control_register теперь равен 0b00100011
```

### Сброс бита

```
declare integer[unsigned, 8bit] named control_register on stack is 0b11111111

-- Сбросить бит номер 5
clear bit 5 of control_register
-- control_register теперь равен 0b11011111
```

### Инверсия бита

```
declare integer[unsigned, 8bit] named toggle_register on stack is 0b10101010

-- Инвертировать бит номер 3
toggle bit 3 of toggle_register
-- toggle_register теперь равен 0b10100010
```

---

## Именованные биты

Когда биты имеют смысловое значение — им можно дать имена:

```
define type[DeviceControlRegister] as integer[unsigned, 8bit]
    bit 0 named power_enable
    bit 1 named clock_enable
    bit 2 named interrupt_enable
    bit 3 named dma_enable
    bit 4 named error_flag
    bit 5 named ready_flag
    bits 6 to 7 named operating_mode
end type

declare DeviceControlRegister named control on stack is 0b00000000
```

Использование именованных битов:

```
-- Установка по имени
set bit[power_enable] of control
set bit[clock_enable] of control

-- Проверка по имени
if bit[ready_flag] of control is set
    log_message receives "Device is ready" and 1
end if

-- Чтение группы битов
declare integer[unsigned, 8bit] named current_mode on stack is 0
current_mode is bits[operating_mode] of control
```

Читается как описание регистра в документации к железу. Никаких магических чисел.

---

## Битовые операции над байтовыми массивами

```
declare byte named data_buffer on heap is 0
declare integer[unsigned, 32bit] named buffer_size on stack is 64
declare byte named mask_buffer on heap is 0

-- Применить маску к каждому байту буфера
declare integer[unsigned, 32bit] named current_index on stack is 0

repeat while current_index is less than buffer_size

    declare integer[unsigned, 8bit] named current_byte on stack is 0
    declare integer[unsigned, 8bit] named mask_byte on stack is 0
    declare integer[unsigned, 8bit] named result_byte on stack is 0

    current_byte is value at data_buffer offset by current_index
    mask_byte is value at mask_buffer offset by current_index

    result_byte is bits of current_byte and bits of mask_byte

    value at data_buffer offset by current_index is result_byte

    current_index is current_index plus 1

end repeat
```

Слова `offset by` — безопасный способ обратиться к элементу массива. Компилятор проверяет что индекс не выходит за границы.

---

## Порядок байт

При работе с многобайтовыми значениями порядок байт обязан быть объявлен явно:

```
declare integer[unsigned, 32bit] named network_value
    on stack
    byte order big endian
    is 0

declare integer[unsigned, 32bit] named local_value
    on stack
    byte order little endian
    is 0
```

Преобразование порядка байт:

```
local_value is convert network_value
    from byte order big endian
    to byte order little endian
```

Смешивание значений с разным порядком байт без явного преобразования — отклонение компиляции:

```
COMPILATION REJECTED
Byte order mismatch.

Variable [network_value] declared with byte order: big endian
Variable [local_value] declared with byte order: little endian

Cannot mix values with different byte orders without explicit conversion.
```

---

## Что компилятор проверяет в битовых операциях

```
✓ Битовые операции помечены словом bits of
✓ Операнды битовых операций имеют одинаковый тип
✓ Сдвиг не превышает размер типа
✓ Номер бита не превышает размер типа
✓ Именованные биты объявлены в определении типа
✓ offset by не выходит за границы массива
✓ Значения с разным порядком байт не смешиваются без преобразования
✓ Битовые операции не смешиваются с логическими без явного разделения
```

---

## Раздел 3 завершён

```
3.1 Условия и ветвление      ✓
3.2 Циклы и повторение       ✓
3.3 Система ошибок           ✓
3.4 Модули и границы         ✓
3.5 Битовые операции         ✓
```

Мы описали полную систему управления потоком C*. Программа теперь умеет принимать решения, повторять действия, обрабатывать ошибки, делиться на модули и работать с железом на уровне битов.

---

# C* Language Reference
## Раздел 4 — Типы и структуры данных
### 4.1 Пользовательские типы углублённо

---

## Главное правило пользовательских типов

> Пользовательский тип в C* — это не просто группировка данных. Это контракт который описывает что данные собой представляют, где живут, как выровнены, и какие операции над ними допустимы. Компилятор знает всё это до запуска программы.

---

## Сегменты памяти

Прежде чем углубляться в типы — фундамент на котором они строятся.

Память программы на C* разделена на физически изолированные сегменты:

```
define program memory layout

    segment[Code]
        contains: program instructions
        writable: false
        executable: true
    end segment

    segment[Numbers]
        contains: integer, float, byte, boolean
        writable: true
        executable: false
    end segment

    segment[Text]
        contains: text values only
        writable: true
        executable: false
        encoding: UTF-8
    end segment

    segment[Structures]
        contains: user defined types
        writable: true
        executable: false
    end segment

    segment[Stack]
        contains: temporary variables of all types
        writable: true
        executable: false
        grows: downward
    end segment

    segment[Heap]
        contains: dynamically allocated data
        writable: true
        executable: false
    end segment

end program memory layout
```

Компилятор знает в каком сегменте живёт каждая переменная. Данные из разных сегментов не могут оказаться соседями. Переполнение одного типа данных не может затронуть другой тип физически.

---

## Простой псевдоним типа

```
define type[SensorReading] as integer[signed, 16bit]
    lives in segment[Numbers]
    valid range from minus 1000 to 1000
    on out of range
        reject with error[InvalidSensorReading]
end type
```

Псевдоним не просто переименовывает тип. Он добавляет:
- явный сегмент памяти
- допустимый диапазон значений
- реакцию на нарушение диапазона

Попытка присвоить `SensorReading` значение вне диапазона — отклонение на уровне:

```
declare SensorReading named temperature on stack is 0

temperature is 1500  -- ОШИБКА. Выходит за диапазон.
```

```
COMPILATION REJECTED
Value out of declared range.

Type [SensorReading] valid range: -1000 to 1000
Assigned value: 1500

Declared at: line 1
Violation at: line 3
```

---

## Структура — составной тип

```
define type[AudioSample]
    lives in segment[Structures]
    alignment 4 bytes
    contains
        integer[signed, 16bit] named left_channel
            alignment 2 bytes
            valid range from minus 32767 to 32767
        integer[signed, 16bit] named right_channel
            alignment 2 bytes
            valid range from minus 32767 to 32767
        integer[unsigned, 32bit] named timestamp
            alignment 4 bytes
            valid range from 0 to 4294967295
        boolean named is_silent
            alignment 1 byte
        byte named reserved
            alignment 1 byte
            note "padding for alignment — explicit not hidden"
    end contains
end type
```

Поле `reserved` объявлено явно с пометкой. В C* нет скрытых padding байт — если выравнивание требует дополнительного места, программист объявляет его явно и объясняет зачем.

---

## Инициализация структуры

Все поля обязаны быть инициализированы при объявлении:

```
declare AudioSample named current_sample on stack is
    left_channel: 0
    right_channel: 0
    timestamp: 0
    is_silent: true
    reserved: 0
end declare
```

Пропустить поле — отклонение компиляции:

```
COMPILATION REJECTED
Incomplete initialization.

Type [AudioSample] has 5 fields.
Initialization provides 4 fields.
Missing field: reserved

All fields must be initialized at declaration.
```

---

## Значения по умолчанию

Если структура всегда начинается с одних и тех же значений — объявляются значения по умолчанию:

```
define type[AudioSample]
    lives in segment[Structures]
    alignment 4 bytes
    contains
        integer[signed, 16bit] named left_channel
            default 0
        integer[signed, 16bit] named right_channel
            default 0
        integer[unsigned, 32bit] named timestamp
            default 0
        boolean named is_silent
            default true
        byte named reserved
            default 0
            note "padding for alignment"
    end contains
end type

-- Теперь можно объявить с умолчаниями:
declare AudioSample named empty_sample on stack is default

-- Или переопределить часть полей:
declare AudioSample named active_sample on stack is default
    override left_channel: 1024
    override right_channel: 1024
    override is_silent: false
end declare
```

---

## Методы типа

Тип может иметь операции которые принадлежат только ему:

```
define type[AudioSample]
    lives in segment[Structures]
    alignment 4 bytes
    contains
        integer[signed, 16bit] named left_channel
            default 0
        integer[signed, 16bit] named right_channel
            default 0
        integer[unsigned, 32bit] named timestamp
            default 0
        boolean named is_silent
            default true
        byte named reserved
            default 0
    end contains

    operations

        operation normalize
            receives
                float[32bit] named target_level
            returns
                nothing
            on error[InvalidValue]
                reject with error[InvalidValue]
            body
                if target_level is less or equal to 0.0
                    reject with error[InvalidValue]
                end if
                declare float[32bit] named scale on stack is 0.0
                scale is target_level divide by 32767.0
                left_channel is convert
                    left_channel multiply by scale
                    to integer[signed, 16bit]
                    on overflow
                        reject with error[InvalidValue]
                right_channel is convert
                    right_channel multiply by scale
                    to integer[signed, 16bit]
                    on overflow
                        reject with error[InvalidValue]
            end body
        end operation

        operation is_clipping
            receives
                nothing
            returns
                boolean named clipping_detected
            body
                clipping_detected is check
                    left_channel is equal to 32767
                    or left_channel is equal to minus 32767
                    or right_channel is equal to 32767
                    or right_channel is equal to minus 32767
                end check
            end body
        end operation

    end operations

end type
```

Вызов операции:

```
declare AudioSample named sample on stack is default
    override left_channel: 30000
    override right_channel: 30000
    override is_silent: false
end declare

if sample.is_clipping
    call sample.normalize
        with target_level as copy: 0.8
        on error[InvalidValue]
            reject with error[NormalizationFailed]
        on success
            log_message receives "Sample normalized" and 1
    end call
end if
```

---

## Неизменяемый тип

Тип может быть объявлен полностью неизменяемым после создания:

```
define type[DeviceIdentifier]
    lives in segment[Structures]
    immutable after creation
    alignment 4 bytes
    contains
        integer[unsigned, 32bit] named device_id
            default 0
        integer[unsigned, 16bit] named vendor_id
            default 0
        integer[unsigned, 16bit] named product_id
            default 0
    end contains
end type

declare DeviceIdentifier named audio_device on stack is
    device_id: 42
    vendor_id: 1234
    product_id: 5678
end declare

-- После создания изменить невозможно:
audio_device.device_id is 100  -- ОТКЛОНЕНИЕ КОМПИЛЯЦИИ
```

```
COMPILATION REJECTED
Immutable type violation.

Type [DeviceIdentifier] declared as immutable after creation.
Modification attempted at: line 9

Immutable types cannot be modified after declaration.
```

---

## Тип с инвариантами

Инварианты — это условия которые всегда истинны для данного типа. Компилятор проверяет их при каждом изменении:

```
define type[AudioBuffer]
    lives in segment[Structures]
    alignment 8 bytes
    contains
        pointer[to byte] named data
            default null
        integer[unsigned, 32bit] named capacity
            default 0
        integer[unsigned, 32bit] named used_size
            default 0
        boolean named is_initialized
            default false
    end contains

    invariants
        invariant capacity_not_negative
            capacity is greater or equal to 0
        end invariant

        invariant used_not_exceeds_capacity
            used_size is less or equal to capacity
        end invariant

        invariant data_valid_when_initialized
            if is_initialized is equal to true
                data is not null
            end if
        end invariant
    end invariants

end type
```

При каждом изменении любого поля компилятор проверяет все инварианты. Если изменение нарушает инвариант — отклонение компиляции:

```
COMPILATION REJECTED
Invariant violation.

Type [AudioBuffer] invariant [used_not_exceeds_capacity] violated.

Field [used_size] set to: 1024
Field [capacity] current value: 512

used_size cannot exceed capacity.
Modification rejected at: line 34
```

---

## Что компилятор проверяет в пользовательских типах

```
✓ Каждый тип объявлен с сегментом памяти
✓ Выравнивание объявлено явно для типа и каждого поля
✓ Padding байты объявлены явно с пояснением
✓ Все поля инициализированы при объявлении переменной
✓ Диапазоны значений соблюдаются при каждом присвоении
✓ Иммутабельные типы не изменяются после создания
✓ Инварианты проверяются при каждом изменении поля
✓ Операции типа имеют полный контракт как обычные функции
```

---

*Готово. Переходим к 4.2 — Массивы?*
# C* Language Reference
## Раздел 4 — Типы и структуры данных
### 4.2 Массивы

---

## Главное правило массивов

> Массив в C* никогда не теряет информацию о себе. Его размер, тип элементов и сегмент памяти известны компилятору в каждой точке программы. Массив не распадается в указатель. Никогда.

---

## Объявление массива фиксированного размера

```
declare array[integer[signed, 16bit], 64] named sample_buffer
    on stack
    all elements is 0
```

Структура объявления:
```
array[ТИП_ЭЛЕМЕНТА, РАЗМЕР]     — тип и количество элементов
named ИМЯ                        — имя массива
on stack или on heap             — где живёт
all elements is ЗНАЧЕНИЕ         — начальное значение всех элементов
```

Все четыре части обязательны. Пропустить любую — отклонение компиляции.

---

## Объявление массива динамического размера

Когда размер неизвестен до запуска:

```
declare integer[unsigned, 32bit] named buffer_size on stack is 0
buffer_size is read_configuration_value receives "audio_buffer_size"

declare array[byte, buffer_size] named audio_data
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]
```

Динамический массив обязан жить на куче. Попытка объявить динамический массив на стеке — отклонение компиляции:

```
COMPILATION REJECTED
Dynamic array on stack forbidden.

Array [audio_data] has dynamic size [buffer_size].
Dynamic size is unknown at compile time.
Stack arrays must have size known at compile time.

Declare dynamic arrays on heap only.
```

---

## Доступ к элементам

### Чтение элемента

```
declare array[integer[signed, 16bit], 64] named sample_buffer
    on stack
    all elements is 0

declare integer[signed, 16bit] named first_sample on stack is 0
declare integer[signed, 16bit] named last_sample on stack is 0

first_sample is sample_buffer at index 0
last_sample is sample_buffer at index 63
```

Слова `at index` — единственный способ обратиться к элементу массива. Никакого `buffer[i]`.

### Запись элемента

```
sample_buffer at index 0 is 1024
sample_buffer at index 1 is minus 512
```

### Доступ через переменную индекса

```
declare integer[unsigned, 32bit] named current_index on stack is 0
declare integer[signed, 16bit] named current_value on stack is 0

current_value is sample_buffer at index current_index
```

---

## Проверка границ

Каждое обращение к массиву по переменному индексу обязано иметь проверку границ:

```
declare integer[unsigned, 32bit] named current_index on stack is 0

-- Запрещено — нет проверки границ:
current_value is sample_buffer at index current_index

-- Правильно:
if current_index is less than 64
    current_value is sample_buffer at index current_index
otherwise
    reject with error[IndexOutOfBounds]
end otherwise
end if
```

Для константного индекса проверка не нужна — компилятор проверяет сам:

```
-- Компилятор знает что 63 < 64 — проверка не нужна
current_value is sample_buffer at index 63

-- Компилятор знает что 64 >= 64 — отклонение компиляции
current_value is sample_buffer at index 64
```

```
COMPILATION REJECTED
Index out of bounds.

Array [sample_buffer] has size: 64
Valid index range: 0 to 63
Accessed index: 64

Constant index is always out of bounds.
```

---

## Размер массива

```
declare array[integer[signed, 16bit], 64] named sample_buffer
    on stack
    all elements is 0

declare integer[unsigned, 32bit] named total_elements on stack is 0
declare integer[unsigned, 32bit] named total_bytes on stack is 0

total_elements is count of sample_buffer
total_bytes is size of sample_buffer
```

`count of` — количество элементов.
`size of` — размер в байтах.

Оба выражения работают и для статических и для динамических массивов.

---

## Передача массива в функцию

Массив в C* не распадается в указатель. Функция получает массив целиком — с типом, размером и правилами доступа:

```
function process_audio_buffer
    receives
        array[integer[signed, 16bit], any size] named input_buffer as access
        array[integer[signed, 16bit], any size] named output_buffer as access
    returns
        nothing
    on error[SizeMismatch]
        reject with error[SizeMismatch]
    body

        if count of input_buffer is not equal to count of output_buffer
            reject with error[SizeMismatch]
        end if

        declare integer[unsigned, 32bit] named current_index on stack is 0

        repeat while current_index is less than count of input_buffer

            declare integer[signed, 16bit] named sample on stack is 0
            sample is input_buffer at index current_index

            declare integer[signed, 16bit] named processed on stack is 0
            processed is convert
                sample multiply by 0.8
                to integer[signed, 16bit]
                on overflow
                    reject with error[ArithmeticOverflow]

            output_buffer at index current_index is processed
            current_index is current_index plus 1

        end repeat

    end body
end function
```

Слово `any size` означает что функция принимает массив любого размера. Внутри функции размер всегда доступен через `count of`.

---

## Срез массива

Работа с частью массива без копирования:

```
declare array[byte, 1024] named full_buffer
    on heap
    all elements is 0

-- Взять срез с 256 по 511 элемент
declare array slice named middle_section
    of full_buffer
    from index 256
    to index 511
    as access
```

Срез не копирует данные. Он даёт доступ к части оригинального массива. Правила доступа наследуются от оригинала — если оригинал передан `as access` то срез тоже только для чтения если явно не объявлено иначе.

Изменение среза меняет оригинал:

```
middle_section at index 0 is 42
-- full_buffer at index 256 теперь тоже равен 42
```

---

## Многомерные массивы

```
declare array[array[integer[signed, 16bit], 8], 8] named audio_matrix
    on stack
    all elements is 0
```

Это массив из восьми массивов по восемь элементов. Матрица 8 на 8.

Доступ к элементу:

```
declare integer[signed, 16bit] named element on stack is 0

element is audio_matrix at index 3 at index 5
audio_matrix at index 3 at index 5 is 1024
```

Каждое измерение — отдельный `at index`. Читается как "в строке 3, в столбце 5".

Для удобства — именованные измерения:

```
declare array[array[integer[signed, 16bit], 8], 8] named audio_matrix
    on stack
    all elements is 0
    dimension 0 named row
    dimension 1 named column
```

Теперь доступ через имена измерений:

```
element is audio_matrix at row 3 at column 5
audio_matrix at row 3 at column 5 is 1024
```

---

## Копирование массивов

```
declare array[integer[signed, 16bit], 64] named source_buffer
    on stack
    all elements is 0

declare array[integer[signed, 16bit], 64] named destination_buffer
    on stack
    all elements is 0

-- Полное копирование
copy all of source_buffer to destination_buffer
    on size mismatch
        reject with error[SizeMismatch]

-- Частичное копирование
copy source_buffer
    from index 0
    to destination_buffer
    from index 32
    count 16 elements
    on size mismatch
        reject with error[SizeMismatch]
```

Копирование с проверкой. Компилятор знает размеры обоих массивов и проверяет совместимость.

---

## Массив структур

```
define type[AudioSample]
    lives in segment[Structures]
    alignment 4 bytes
    contains
        integer[signed, 16bit] named left_channel
            default 0
        integer[signed, 16bit] named right_channel
            default 0
        integer[unsigned, 32bit] named timestamp
            default 0
        boolean named is_silent
            default true
        byte named reserved
            default 0
    end contains
end type

declare array[AudioSample, 32] named sample_array
    on heap
    all elements is default
    on allocation failure
        reject with error[OutOfMemory]

-- Доступ к полю элемента массива:
declare integer[signed, 16bit] named left on stack is 0
left is sample_array at index 5 field left_channel

sample_array at index 5 field is_silent is false
sample_array at index 5 field left_channel is 2048
```

Слова `at index N field ИМЯ` — единственный способ обратиться к полю элемента массива структур. Читается явно и однозначно.

---

## Освобождение массива на куче

```
declare array[byte, buffer_size] named audio_data
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]

-- работа с массивом

release audio_data
-- все элементы освобождены
-- audio_data больше не существует
```

---

## Что компилятор проверяет в массивах

```
✓ Тип элементов, размер и место объявлены при создании
✓ Все элементы инициализированы при объявлении
✓ Динамические массивы живут только на куче
✓ Константный индекс проверяется на этапе компиляции
✓ Переменный индекс всегда проверяется перед использованием
✓ Функция получает массив с метаданными — не указатель
✓ Срез не выходит за границы оригинала
✓ Копирование проверяет совместимость размеров
✓ Массив на куче имеет достижимый release
✓ После release массив не используется
```

---

*Готово. Переходим к 4.3 — Строки и текст?*
# C* Language Reference
## Раздел 4 — Типы и структуры данных
### 4.3 Строки и текст

---

## Главное правило текста

> Text в C* живёт в собственном сегменте памяти физически изолированном от чисел и структур. Text знает свою длину. Text не заканчивается нулевым байтом. Переполнение текстового буфера не может затронуть другие данные — им там негде быть.

---

## Как text устроен внутри

В C строка — это массив байт заканчивающийся нулём. Это источник половины уязвимостей в истории программирования.

В C* text — это структура из двух частей:

```
Внутреннее устройство text:

[ длина в байтах: 32bit ][ данные в UTF-8 ]
        4 байта              N байт
```

Длина хранится явно. Нулевого терминатора нет. Компилятор всегда знает где text заканчивается без сканирования байт.

Весь text живёт в сегменте `Text` — физически отдельном от чисел, указателей и структур.

---

## Объявление текстовой переменной

```
declare text named greeting
    in segment[Text]
    on heap
    is "Hello"
    on allocation failure
        reject with error[OutOfMemory]
```

Текстовая переменная всегда живёт на куче — потому что её размер может меняться. На стеке можно хранить только указатель на text:

```
-- Указатель на text — живёт на стеке
declare pointer[to text] named message_ptr on stack is null
```

---

## Текстовые литералы

Текстовые литералы в коде автоматически помещаются в сегмент `Text` на этапе компиляции:

```
declare text named error_message
    in segment[Text]
    on heap
    is "Device initialization failed"
    on allocation failure
        reject with error[OutOfMemory]

-- Литерал "Device initialization failed" живёт в Text сегменте
-- error_message содержит длину и указатель на данные
```

---

## Длина текста

```
declare text named message
    in segment[Text]
    on heap
    is "AudioEngine"
    on allocation failure
        reject with error[OutOfMemory]

declare integer[unsigned, 32bit] named char_count on stack is 0
declare integer[unsigned, 32bit] named byte_count on stack is 0

char_count is character count of message
byte_count is byte count of message
```

`character count of` — количество символов Unicode. Для латиницы равно числу байт. Для кириллицы и других языков может отличаться.

`byte count of` — точное количество байт в памяти. Всегда доступно и всегда точно.

---

## Сравнение текста

```
declare text named input
    in segment[Text]
    on heap
    is "connected"
    on allocation failure
        reject with error[OutOfMemory]

declare text named expected
    in segment[Text]
    on heap
    is "connected"
    on allocation failure
        reject with error[OutOfMemory]

-- Сравнение содержимого:
if input is equal to expected
    log_message receives "Status confirmed" and 1
end if

-- Сравнение без учёта регистра:
if input is equal to expected ignoring case
    log_message receives "Status confirmed case insensitive" and 1
end if
```

Оператор `is equal to` для text сравнивает содержимое — не адреса в памяти. Это единственное поведение. Скрытого сравнения адресов не существует.

---

## Соединение текста

```
declare text named first_part
    in segment[Text]
    on heap
    is "Audio"
    on allocation failure
        reject with error[OutOfMemory]

declare text named second_part
    in segment[Text]
    on heap
    is "Engine"
    on allocation failure
        reject with error[OutOfMemory]

declare text named combined
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call join text
    with first as access: first_part
    with second as access: second_part
    into result as owner: combined
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- combined теперь содержит "AudioEngine"
end call
```

Соединение создаёт новый text. Оригиналы остаются неизменными если переданы `as access`.

---

## Поиск в тексте

```
declare text named haystack
    in segment[Text]
    on heap
    is "AudioEngine initialized successfully"
    on allocation failure
        reject with error[OutOfMemory]

declare text named needle
    in segment[Text]
    on heap
    is "initialized"
    on allocation failure
        reject with error[OutOfMemory]

declare integer[unsigned, 32bit] named found_at on stack is 0
declare boolean named was_found on stack is false

call find text
    with search in as access: haystack
    with search for as access: needle
    on not found
        was_found is false
    on found at position
        was_found is true
        found_at is position
end call
```

---

## Извлечение части текста

```
declare text named full_message
    in segment[Text]
    on heap
    is "ERROR: device not found"
    on allocation failure
        reject with error[OutOfMemory]

declare text named error_code
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call extract text
    with source as access: full_message
    from character 0
    count 5 characters
    into result as owner: error_code
    on error[IndexOutOfBounds]
        reject with error[InvalidTextOperation]
    on success
        -- error_code содержит "ERROR"
end call
```

---

## Преобразование числа в текст и обратно

### Число в текст

```
declare integer[signed, 32bit] named error_code on stack is minus 404
declare text named error_text
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call integer to text
    with value as copy: error_code
    into result as owner: error_text
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- error_text содержит "-404"
end call
```

### Текст в число

```
declare text named input_text
    in segment[Text]
    on heap
    is "1024"
    on allocation failure
        reject with error[OutOfMemory]

declare integer[signed, 32bit] named parsed_value on stack is 0

call text to integer
    with source as access: input_text
    into result: parsed_value
    on error[InvalidTextFormat]
        reject with error[InvalidTextFormat]
    on error[ValueTooLarge]
        reject with error[ValueTooLarge]
    on success
        -- parsed_value содержит 1024
end call
```

---

## Текст и байты

Иногда нужен доступ к сырым байтам текста — например при работе с сетевыми протоколами:

```
declare text named message
    in segment[Text]
    on heap
    is "Hello"
    on allocation failure
        reject with error[OutOfMemory]

declare array[byte, 5] named raw_bytes
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]

call text to bytes
    with source as access: message
    into result as access: raw_bytes
    on error[SizeMismatch]
        reject with error[SizeMismatch]
    on success
        -- raw_bytes содержит байты UTF-8 строки "Hello"
end call
```

Обратное преобразование:

```
call bytes to text
    with source as access: raw_bytes
    with byte count as copy: 5
    into result as owner: message
    on error[InvalidEncoding]
        reject with error[InvalidEncoding]
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- message содержит "Hello"
end call
```

---

## Неизменяемый текст

Текстовые константы объявляются явно:

```
declare constant text named application_name
    in segment[Text]
    is "C* Audio Engine"

declare constant text named version_string
    in segment[Text]
    is "1.0.0"
```

Константный text живёт в сегменте `Text` но помечен как неизменяемый. Попытка изменить — отклонение компиляции. Не требует `on allocation failure` — размер известен на этапе компиляции.

---

## Освобождение текста

```
declare text named temporary_message
    in segment[Text]
    on heap
    is "Processing complete"
    on allocation failure
        reject with error[OutOfMemory]

log_message receives temporary_message as access and 1

release temporary_message
-- временный текст освобождён
-- temporary_message больше не существует
```

---

## Защита от переполнения

Переполнение текстового буфера в C* невозможно по трём причинам:

```
Причина 1 — Сегрегация
    Text живёт в сегменте Text
    Числа живут в сегменте Numbers
    Они физически не соседи
    Вылезти за буфер некуда — там нет чужих данных

Причина 2 — Явная длина
    Text всегда знает свою длину
    Нет сканирования до нулевого байта
    Нет возможности "потерять" конец строки

Причина 3 — Проверка при операциях
    Каждая операция с текстом проверяет размер
    join, extract, copy — все проверяют границы
    Нарушение — отклонение или ошибка выполнения
```

---

## Что компилятор проверяет в тексте

```
✓ Text объявлен с сегментом Text
✓ Text на куче имеет on allocation failure
✓ Константный text не изменяется
✓ Сравнение text всегда по содержимому
✓ Все операции с text имеют обработку ошибок
✓ Преобразование bytes to text проверяет кодировку
✓ Text на куче имеет достижимый release
✓ После release text не используется
✓ Text не смешивается с числовыми данными напрямую
```

---

## Раздел 4.3 завершён

Три гарантии которые C* даёт программисту при работе с текстом:

```
Гарантия 1: Переполнение буфера невозможно структурно
Гарантия 2: Длина всегда известна без сканирования
Гарантия 3: Text физически изолирован от других данных
```

---

*Готово. Переходим к 4.4 — Обобщённые типы?*
# C* Language Reference
## Раздел 4 — Типы и структуры данных
### 4.4 Обобщённые типы

---

## Главное правило обобщённых типов

> Обобщённый тип в C* — это шаблон с явно объявленными ограничениями. Компилятор проверяет безопасность типов в момент использования шаблона а не в момент его объявления. Обобщённый тип не может нарушить сегрегацию памяти — он работает только внутри одного сегмента.

---

## Зачем нужны обобщённые типы

Без обобщённых типов пришлось бы писать отдельный буфер для каждого типа данных:

```
-- Без обобщённых типов — дублирование:
define type[IntegerBuffer] ...
define type[ByteBuffer] ...
define type[AudioSampleBuffer] ...
```

С обобщёнными типами — один шаблон для всех:

```
-- С обобщёнными типами — один шаблон:
define type[Buffer] for any[ElementType] ...
```

---

## Объявление обобщённого типа

```
define type[Buffer] for any[ElementType]
    lives in segment[Structures]
    alignment 8 bytes

    where ElementType
        lives in segment[Numbers]
        or lives in segment[Structures]
        size is known at compile time
    end where

    contains
        array[ElementType, any size] named data
            default empty
        integer[unsigned, 32bit] named capacity
            default 0
        integer[unsigned, 32bit] named used_count
            default 0
        boolean named is_initialized
            default false
    end contains

    invariants
        invariant used_not_exceeds_capacity
            used_count is less or equal to capacity
        end invariant

        invariant data_valid_when_initialized
            if is_initialized is equal to true
                capacity is greater than 0
            end if
        end invariant
    end invariants

    operations

        operation push
            receives
                ElementType named new_element as copy
            returns
                nothing
            on error[BufferFull]
                reject with error[BufferFull]
            body
                if used_count is equal to capacity
                    reject with error[BufferFull]
                end if
                data at index used_count is new_element
                used_count is used_count plus 1
            end body
        end operation

        operation pop
            receives
                nothing
            returns
                ElementType named removed_element
            on error[BufferEmpty]
                reject with error[BufferEmpty]
            body
                if used_count is equal to 0
                    reject with error[BufferEmpty]
                end if
                used_count is used_count minus 1
                removed_element is data at index used_count
            end body
        end operation

        operation peek
            receives
                nothing
            returns
                ElementType named top_element as access
            on error[BufferEmpty]
                reject with error[BufferEmpty]
            body
                if used_count is equal to 0
                    reject with error[BufferEmpty]
                end if
                top_element is data at index used_count minus 1
            end body
        end operation

    end operations

end type
```

---

## Блок where — ограничения на тип

Блок `where` обязателен. Он описывает какие типы допустимы в качестве `ElementType`:

```
where ElementType
    lives in segment[Numbers]
    or lives in segment[Structures]
    size is known at compile time
end where
```

Три вида ограничений:

### Ограничение по сегменту

```
where ElementType
    lives in segment[Numbers]
end where
```

Только числовые типы. Text запрещён — он живёт в другом сегменте.

### Ограничение по размеру

```
where ElementType
    size is known at compile time
end where
```

Только типы с известным размером. Динамические типы запрещены.

### Ограничение по операциям

```
where ElementType
    supports operation[is equal to]
    supports operation[is greater than]
end where
```

Только типы которые поддерживают сравнение. Компилятор проверяет что тип умеет это делать.

### Комбинированные ограничения

```
where ElementType
    lives in segment[Numbers]
    or lives in segment[Structures]
    size is known at compile time
    supports operation[is equal to]
end where
```

Все ограничения применяются одновременно. Тип должен удовлетворять всем.

---

## Использование обобщённого типа

```
-- Буфер целых чисел
declare Buffer[integer[signed, 32bit]] named integer_queue
    on heap
    with capacity 128
    on allocation failure
        reject with error[OutOfMemory]

-- Буфер структур AudioSample
declare Buffer[AudioSample] named sample_queue
    on heap
    with capacity 64
    on allocation failure
        reject with error[OutOfMemory]
```

Компилятор проверяет что тип в скобках удовлетворяет блоку `where`:

```
-- ОШИБКА — text живёт в сегменте Text, не Numbers или Structures
declare Buffer[text] named text_queue
    on heap
    with capacity 32
    on allocation failure
        reject with error[OutOfMemory]
```

```
COMPILATION REJECTED
Type constraint violation.

Generic type [Buffer] requires ElementType to live in:
    segment[Numbers] or segment[Structures]

Provided type [text] lives in: segment[Text]

text cannot be used as ElementType in Buffer.
```

---

## Работа с обобщённым типом

```
declare Buffer[integer[signed, 32bit]] named number_queue
    on heap
    with capacity 8
    on allocation failure
        reject with error[OutOfMemory]

-- Добавление элементов
call number_queue.push
    with new_element as copy: 42
    on error[BufferFull]
        reject with error[QueueOverflow]
    on success
        -- продолжаем
end call

call number_queue.push
    with new_element as copy: 100
    on error[BufferFull]
        reject with error[QueueOverflow]
    on success
        -- продолжаем
end call

-- Просмотр верхнего элемента
declare integer[signed, 32bit] named top_value on stack is 0

call number_queue.peek
    on error[BufferEmpty]
        reject with error[QueueEmpty]
    on success
        top_value is top_element
end call

-- Извлечение элемента
declare integer[signed, 32bit] named popped_value on stack is 0

call number_queue.pop
    on error[BufferEmpty]
        reject with error[QueueEmpty]
    on success
        popped_value is removed_element
end call

release number_queue
```

---

## Обобщённая функция

Функции тоже могут быть обобщёнными:

```
function find first
    for any[ElementType]
    where ElementType
        supports operation[is equal to]
        size is known at compile time
    end where
    receives
        array[ElementType, any size] named search_in as access
        ElementType named search_for as copy
    returns
        integer[unsigned, 32bit] named found_at_index
        boolean named was_found
    body

        declare integer[unsigned, 32bit] named current_index on stack is 0
        was_found is false
        found_at_index is 0

        repeat while current_index is less than count of search_in

            if search_in at index current_index is equal to search_for
                was_found is true
                found_at_index is current_index
                stop
            end if

            current_index is current_index plus 1

        end repeat

    end body
end function
```

Вызов обобщённой функции — компилятор определяет тип автоматически из аргументов:

```
declare array[integer[signed, 32bit], 8] named numbers
    on stack
    all elements is 0

numbers at index 0 is 10
numbers at index 1 is 20
numbers at index 2 is 30

declare integer[unsigned, 32bit] named position on stack is 0
declare boolean named found on stack is false

call find first[integer[signed, 32bit]]
    with search_in as access: numbers
    with search_for as copy: 20
    on success
        position is found_at_index
        found is was_found
end call

if found is equal to true
    log_message receives "Found at index" and 1
    log_integer receives position
end if
```

---

## Обобщённый тип с несколькими параметрами

```
define type[Pair] for any[FirstType] and any[SecondType]
    lives in segment[Structures]
    alignment 8 bytes

    where FirstType
        size is known at compile time
    end where

    where SecondType
        size is known at compile time
    end where

    contains
        FirstType named first_value
        SecondType named second_value
    end contains

    operations

        operation swap
            receives
                nothing
            returns
                Pair[SecondType, FirstType] named swapped_pair
            body
                swapped_pair is
                    first_value: second_value
                    second_value: first_value
                end
            end body
        end operation

    end operations

end type
```

Использование:

```
declare Pair[integer[signed, 32bit], boolean] named status_pair
    on stack
    is
        first_value: minus 404
        second_value: false
    end
```

---

## Что компилятор проверяет в обобщённых типах

```
✓ Блок where присутствует в каждом обобщённом типе
✓ Используемый тип удовлетворяет всем ограничениям where
✓ Обобщённый тип не нарушает сегрегацию памяти
✓ Размер типа известен на этапе компиляции если требуется
✓ Операции над типом поддерживаются если объявлены в where
✓ Все параметры обобщённого типа указаны при использовании
✓ Обобщённая функция получает совместимые аргументы
```

---

*Готово. Переходим к 4.5 — Преобразование типов?*
# C* Language Reference
## Раздел 4 — Типы и структуры данных
### 4.5 Преобразование типов

---

## Главное правило преобразования типов

> В C* не существует неявных преобразований типов. Каждое преобразование написано явно, имеет направление, и обязано описать что происходит если преобразование невозможно. Компилятор никогда не решает за программиста как обращаться с потерей данных.

---

## Почему это важно

В C можно написать:
```c
int large = 1000;
char small = large;  -- молчаливая потеря данных
float f = large;     -- молчаливое преобразование
```

Компилятор C промолчит. Данные потеряются или исказятся без единого предупреждения.

В C* это невозможно синтаксически. Каждое преобразование явное и обработанное.

---

## Три вида преобразований

```
Вид 1 — Безопасное преобразование
    Данные гарантированно не теряются
    Компилятор проверяет это статически

Вид 2 — Контролируемое преобразование
    Данные могут потеряться
    Программист обязан описать что делать при потере

Вид 3 — Сырое преобразование
    Биты интерпретируются как другой тип
    Только для работы с железом
    Требует явного разрешения
```

---

## Вид 1 — Безопасное преобразование

Преобразование которое никогда не теряет данные. Компилятор проверяет это на этапе компиляции.

```
declare integer[signed, 8bit] named small_number on stack is 42
declare integer[signed, 32bit] named large_number on stack is 0

-- Безопасно — 8bit всегда помещается в 32bit
large_number is safe convert small_number to integer[signed, 32bit]
```

Если преобразование не является безопасным — отклонение компиляции:

```
declare integer[signed, 32bit] named large_number on stack is 42
declare integer[signed, 8bit] named small_number on stack is 0

-- ОШИБКА — 32bit не всегда помещается в 8bit
small_number is safe convert large_number to integer[signed, 8bit]
```

```
COMPILATION REJECTED
Unsafe conversion declared as safe.

Converting from: integer[signed, 32bit] — range: -2147483648 to 2147483647
Converting to:   integer[signed, 8bit]  — range: -128 to 127

Source type can hold values that do not fit in target type.
Use controlled convert with overflow handling instead.
```

### Таблица безопасных преобразований

```
От меньшего к большему — всегда безопасно:
integer[signed, 8bit]   → integer[signed, 16bit]  ✓
integer[signed, 8bit]   → integer[signed, 32bit]  ✓
integer[signed, 8bit]   → integer[signed, 64bit]  ✓
integer[signed, 16bit]  → integer[signed, 32bit]  ✓
integer[signed, 16bit]  → integer[signed, 64bit]  ✓
integer[signed, 32bit]  → integer[signed, 64bit]  ✓
integer[unsigned, 8bit] → integer[unsigned, 16bit] ✓
float[32bit]            → float[64bit]             ✓

От беззнакового к знаковому большего размера — безопасно:
integer[unsigned, 8bit]  → integer[signed, 16bit]  ✓
integer[unsigned, 16bit] → integer[signed, 32bit]  ✓
integer[unsigned, 32bit] → integer[signed, 64bit]  ✓

Всё остальное — контролируемое преобразование.
```

---

## Вид 2 — Контролируемое преобразование

Преобразование которое может потерять данные. Программист обязан описать все возможные исходы.

### Сужение целого числа

```
declare integer[signed, 32bit] named source on stack is 1000
declare integer[signed, 8bit] named target on stack is 0

controlled convert source to integer[signed, 8bit]
    into target
    on overflow
        reject with error[ValueTooLarge]
    on success
        -- target содержит корректное значение
end convert
```

### Преобразование знакового в беззнаковое

```
declare integer[signed, 32bit] named signed_value on stack is minus 50
declare integer[unsigned, 32bit] named unsigned_value on stack is 0

controlled convert signed_value to integer[unsigned, 32bit]
    into unsigned_value
    on negative value
        reject with error[InvalidConversion]
    on success
        -- unsigned_value содержит корректное значение
end convert
```

### Преобразование float в integer

```
declare float[64bit] named precise on stack is 3.99
declare integer[signed, 32bit] named rounded on stack is 0

controlled convert precise to integer[signed, 32bit]
    into rounded
    rounding toward zero
    on overflow
        reject with error[ValueTooLarge]
    on success
        -- rounded содержит 3
end convert
```

Четыре варианта округления — обязательно выбрать один:

```
rounding toward zero      -- отбросить дробную часть: 3.9 → 3
rounding toward nearest   -- к ближайшему целому: 3.5 → 4
rounding toward floor     -- вниз: 3.9 → 3, минус 3.1 → минус 4
rounding toward ceiling   -- вверх: 3.1 → 4, минус 3.9 → минус 3
```

Не указать округление — отклонение компиляции.

### Преобразование integer в float

```
declare integer[signed, 64bit] named large_integer on stack is 9007199254740993
declare float[64bit] named approximate on stack is 0.0

controlled convert large_integer to float[64bit]
    into approximate
    on precision loss
        log_message receives "Precision lost in conversion" and 2
    on success
        -- approximate содержит приближённое значение
end convert
```

Большие целые числа не всегда точно представимы в float. Блок `on precision loss` обязателен.

---

## Вид 3 — Сырое преобразование

Биты числа интерпретируются как другой тип без каких-либо изменений. Только для работы с железом и низкоуровневого кода.

Требует явного разрешения в заголовке модуля:

```
module HardwareDriver
    version[1.0]
    uses memory[Manual]
    depends on nothing
    allows raw conversion
```

Без `allows raw conversion` в заголовке модуля — отклонение компиляции при попытке использовать сырое преобразование.

```
declare integer[unsigned, 32bit] named raw_register on stack is 0xFF00FF00

declare float[32bit] named interpreted_as_float on stack is 0.0

raw convert raw_register to float[32bit]
    into interpreted_as_float
    acknowledging bit pattern reinterpretation
```

Слова `acknowledging bit pattern reinterpretation` обязательны. Программист явно подтверждает — он знает что делает. Биты не изменяются. Только интерпретация меняется.

---

## Преобразование пользовательских типов

Программист может объявить правила преобразования между своими типами:

```
define type[Celsius]
    lives in segment[Numbers]
    as float[32bit]
    valid range from minus 273.15 to 10000.0
    on out of range
        reject with error[InvalidTemperature]
end type

define type[Fahrenheit]
    lives in segment[Numbers]
    as float[32bit]
    valid range from minus 459.67 to 18032.0
    on out of range
        reject with error[InvalidTemperature]
end type

define conversion from[Celsius] to[Fahrenheit]
    body
        result is source multiply by 1.8
        result is result plus 32.0
    end body
    on error[InvalidTemperature]
        reject with error[InvalidTemperature]
end conversion

define conversion from[Fahrenheit] to[Celsius]
    body
        result is source minus 32.0
        result is result divide by 1.8
    end body
    on error[InvalidTemperature]
        reject with error[InvalidTemperature]
end conversion
```

Использование:

```
declare Celsius named room_temp on stack is 22.5
declare Fahrenheit named room_temp_f on stack is 0.0

controlled convert room_temp to Fahrenheit
    into room_temp_f
    on error[InvalidTemperature]
        reject with error[InvalidTemperature]
    on success
        -- room_temp_f содержит 72.5
end convert
```

---

## Преобразование между сегментами

Данные из разных сегментов не могут быть преобразованы напрямую — только через явный мост:

```
-- ЗАПРЕЩЕНО — text и integer в разных сегментах:
declare text named number_text
    in segment[Text]
    on heap
    is "42"
    on allocation failure
        reject with error[OutOfMemory]

declare integer[signed, 32bit] named number on stack is 0

-- Прямое преобразование невозможно:
controlled convert number_text to integer[signed, 32bit]
    into number  -- ОТКЛОНЕНИЕ КОМПИЛЯЦИИ
```

```
COMPILATION REJECTED
Cross segment conversion forbidden.

Variable [number_text] lives in segment[Text]
Variable [number] lives in segment[Numbers]

Direct conversion between segments is forbidden.
Use text to integer conversion function instead.
See section 4.3
```

Правильный путь — через функцию преобразования описанную в разделе 4.3:

```
call text to integer
    with source as access: number_text
    into result: number
    on error[InvalidTextFormat]
        reject with error[InvalidTextFormat]
    on success
        -- number содержит 42
end call
```

---

## Цепочки преобразований

Преобразование через промежуточный тип — каждый шаг явный:

```
declare integer[signed, 8bit] named tiny on stack is 100
declare float[64bit] named precise on stack is 0.0

-- Запрещено — прыжок через два типа сразу:
controlled convert tiny to float[64bit]
    into precise
```

```
COMPILATION REJECTED
Conversion chain not declared.

Cannot convert directly from integer[signed, 8bit] to float[64bit].
Intermediate type required.

Declare each conversion step explicitly.
```

Правильно — каждый шаг отдельно:

```
declare integer[signed, 8bit] named tiny on stack is 100
declare integer[signed, 32bit] named medium on stack is 0
declare float[64bit] named precise on stack is 0.0

-- Шаг 1 — безопасное расширение
medium is safe convert tiny to integer[signed, 32bit]

-- Шаг 2 — контролируемое преобразование в float
controlled convert medium to float[64bit]
    into precise
    on precision loss
        -- для 32bit integer потери точности нет
        -- но блок обязателен
        log_message receives "Unexpected precision loss" and 2
    on success
        -- precise содержит 100.0
end convert
```

---

## Что компилятор проверяет в преобразованиях

```
✓ Каждое преобразование явно объявлено как safe, controlled или raw
✓ safe convert отклоняется если возможна потеря данных
✓ controlled convert имеет обработку всех возможных исходов
✓ float to integer объявляет правило округления
✓ integer to float имеет блок on precision loss
✓ raw convert разрешён только в модулях с allows raw conversion
✓ raw convert имеет acknowledging bit pattern reinterpretation
✓ Преобразование между сегментами только через функции
✓ Цепочки преобразований объявлены пошагово
✓ Пользовательские преобразования объявлены явно для каждого направления
```

---

## Раздел 4 завершён

```
4.1 Пользовательские типы углублённо    ✓
4.2 Массивы                             ✓
4.3 Строки и текст                      ✓
4.4 Обобщённые типы                     ✓
4.5 Преобразование типов                ✓
```

Система типов C* полностью описана. Каждый тип знает где живёт, сколько занимает, какие операции допустимы, и как взаимодействует с другими типами. Никакой неявности. Никакой магии.

---
---

# C* Language Reference
## Раздел 5 — Система и железо
### 5.1 Прямой доступ к памяти

---

## Главное правило прямого доступа

> Прямой доступ к памяти в C* — это осознанный выход за пределы системы гарантий. Он требует явного объявления адреса, размера, режима доступа, ответственного за адрес, и обязательного пояснения зачем этот адрес нужен. Компилятор не может проверить корректность аппаратного адреса — но может потребовать что программист явно взял на себя ответственность.

---

## Объявление hardware pointer

```
declare hardware pointer[to byte] named video_buffer
    at address 0xB8000
    size 4000 bytes
    access write only
    managed by hardware
    note "VGA text mode buffer — mapped by BIOS"
```

Шесть обязательных полей:

```
at address     — конкретный адрес в памяти
size           — сколько байт доступно начиная с адреса
access         — режим доступа
managed by     — кто отвечает за этот адрес
note           — зачем этот адрес нужен
```

Пропустить любое поле — отклонение компиляции.

---

## Режимы доступа

```
access read only        — только чтение
access write only       — только запись
access read write       — чтение и запись
access execute only     — только выполнение кода
```

Попытка записи в `read only` или чтения из `write only` — отклонение компиляции:

```
COMPILATION REJECTED
Access mode violation.

Hardware pointer [video_buffer] declared as: write only
Read operation attempted at: line 34

Write-only hardware regions cannot be read.
```

---

## Ответственный за адрес

Два варианта:

```
-- Железо управляет адресом — C* не трогает
managed by hardware

-- Конкретный модуль управляет адресом
managed by module[VideoDriver]
```

Если указан модуль — только этот модуль может объявить данный hardware pointer. Попытка объявить тот же адрес в другом модуле — отклонение компиляции:

```
COMPILATION REJECTED
Hardware address conflict.

Address [0xB8000] already managed by module [VideoDriver]
Conflicting declaration attempted in module [AudioDriver]

Each hardware address can only be managed by one module.
```

---

## Чтение и запись через hardware pointer

```
declare hardware pointer[to byte] named video_buffer
    at address 0xB8000
    size 4000 bytes
    access read write
    managed by module[VideoDriver]
    note "VGA text mode buffer — mapped by BIOS"

-- Запись байта по смещению
hardware write to video_buffer
    at offset 0
    value 0x41
    note "Writing character A to position 0"

-- Чтение байта по смещению
declare byte named current_char on stack is 0
hardware read from video_buffer
    at offset 0
    into current_char

-- Проверка смещения
hardware write to video_buffer
    at offset 3999
    value 0x07
    note "Writing attribute byte to last position"
```

Слова `hardware write` и `hardware read` сигнализируют компилятору — здесь прямой доступ к железу. Смещение проверяется против объявленного `size` — выйти за границу невозможно:

```
COMPILATION REJECTED
Hardware access out of bounds.

Hardware pointer [video_buffer] size: 4000 bytes
Valid offset range: 0 to 3999
Attempted offset: 4000
```

---

## Hardware pointer не участвует в системе владения

```
-- Запрещено:
release video_buffer           -- hardware память не освобождается через release

-- Запрещено:
declare pointer[to byte] named alias is address of video_buffer as owner
                                        -- нельзя взять владение над hardware

-- Запрещено:
if video_buffer is null        -- hardware pointer не проверяется на null
    ...
end if
```

Сообщение компилятора:
```
COMPILATION REJECTED
Invalid operation on hardware pointer.

Hardware pointers are not managed by C* ownership system.
Operations forbidden on hardware pointers:
    release, null check, ownership transfer.

Hardware pointer [video_buffer] declared at: line 1
Invalid operation attempted at: line 8
```

---

## Барьеры памяти

При работе с железом порядок операций критичен. Процессор может переупорядочивать инструкции для оптимизации. Hardware барьер запрещает это:

```
hardware write to control_register
    at offset 0
    value 0x01
    note "Enable device"

hardware memory barrier
    note "Ensure enable command reaches device before sending data"

hardware write to data_register
    at offset 0
    value 0xFF
    note "Send data after device is enabled"
```

`hardware memory barrier` — гарантия что все операции до барьера завершились до начала операций после барьера. Обязателен везде где порядок операций с железом важен.

---

## Что компилятор проверяет в прямом доступе к памяти

```
✓ Все шесть обязательных полей присутствуют
✓ Режим доступа соблюдается при каждой операции
✓ Смещение не выходит за объявленный size
✓ Каждый адрес управляется только одним модулем
✓ release, null check и передача владения запрещены
✓ hardware read и hardware write используются явно
```

---

*Готово. Переходим к 5.2 — Регистры и порты?*

# C* Language Reference
## Раздел 5 — Система и железо
### 5.2 Регистры и порты

---

## Главное правило регистров и портов

> Регистры процессора и порты устройств — это два разных механизма взаимодействия с железом. Они требуют разных машинных инструкций и имеют разную семантику. C* делает это различие явным на уровне синтаксиса. Компилятор генерирует правильные инструкции для каждого случая автоматически.

---

## Разница между регистрами и портами

```
Регистр процессора или устройства:
    Доступ через адрес в пространстве памяти
    Читается и пишется как обычная память
    Но по этому адресу живёт железо а не RAM
    Машинная инструкция: MOV

Порт ввода-вывода:
    Доступ через отдельное пространство адресов портов
    Не пересекается с пространством памяти
    Специальные машинные инструкции: IN и OUT
    Типично для архитектуры x86
```

---

## Объявление регистра

```
declare hardware register[32bit] named apic_command
    at address 0xFEE00300
    access read write
    managed by module[InterruptController]
    volatile
    note "Local APIC interrupt command register — writing triggers IPI"
```

Поле `volatile` обязательно для регистров которые меняются независимо от программы. Оно запрещает компилятору кэшировать значение регистра — каждое чтение обращается к железу напрямую.

Семь обязательных полей для регистра:

```
at address      — адрес регистра в пространстве памяти
access          — режим доступа
managed by      — ответственный модуль или hardware
volatile        — запрет кэширования значения
note            — зачем этот регистр
```

---

## Объявление порта

```
declare hardware port[8bit] named keyboard_data_port
    at port 0x60
    access read only
    managed by module[KeyboardDriver]
    note "PS/2 keyboard data port — reading retrieves scan code"

declare hardware port[8bit] named keyboard_command_port
    at port 0x64
    access read write
    managed by module[KeyboardDriver]
    note "PS/2 keyboard command and status port"
```

Разница в синтаксисе: `at address` для регистров, `at port` для портов. Компилятор видит это различие и генерирует правильные инструкции.

---

## Чтение и запись регистра

```
declare hardware register[32bit] named apic_command
    at address 0xFEE00300
    access read write
    managed by module[InterruptController]
    volatile
    note "Local APIC interrupt command register"

-- Запись в регистр
hardware write register apic_command
    value 0x000C4500
    note "Send INIT IPI to all processors"

-- Чтение из регистра
declare integer[unsigned, 32bit] named apic_status on stack is 0

hardware read register apic_command
    into apic_status

-- Проверка конкретного бита после чтения
if bit 12 of apic_status is set
    log_message receives "IPI delivery pending" and 1
end if
```

---

## Чтение и запись порта

```
declare hardware port[8bit] named keyboard_data_port
    at port 0x60
    access read only
    managed by module[KeyboardDriver]
    note "PS/2 keyboard data port"

declare hardware port[8bit] named keyboard_status_port
    at port 0x64
    access read only
    managed by module[KeyboardDriver]
    note "PS/2 keyboard status port"

-- Проверка статуса перед чтением данных
declare byte named status_byte on stack is 0
declare byte named scan_code on stack is 0

hardware read port keyboard_status_port
    into status_byte

if bit 0 of status_byte is set
    hardware read port keyboard_data_port
        into scan_code
    process_scan_code receives scan_code as copy
end if
```

Слова `hardware read register` и `hardware read port` явно различаются. Компилятор генерирует инструкцию `MOV` для регистра и инструкцию `IN` для порта.

---

## Именованные биты регистра

Регистры железа часто имеют поля с конкретным смыслом. C* позволяет объявить их явно:

```
declare hardware register[32bit] named apic_spurious
    at address 0xFEE000F0
    access read write
    managed by module[InterruptController]
    volatile
    note "Local APIC spurious interrupt vector register"
    bits
        bits 0 to 7 named spurious_vector
            note "Interrupt vector for spurious interrupts"
        bit 8 named apic_enable
            note "Set to enable APIC, clear to disable"
        bit 9 named focus_processor_checking
            note "Focus processor checking enable"
        bits 10 to 31 named reserved_bits
            access read only
            note "Reserved — must not be modified"
    end bits
```

Использование именованных битов:

```
-- Установка вектора и включение APIC
hardware write register apic_spurious
    field spurious_vector: 0xFF
    field apic_enable: 1
    field focus_processor_checking: 0
    note "Initialize APIC with spurious vector 0xFF"

-- Чтение конкретного поля
declare byte named current_vector on stack is 0

hardware read register apic_spurious
    field spurious_vector
    into current_vector
```

Попытка записи в `reserved_bits` — отклонение компиляции:

```
COMPILATION REJECTED
Reserved field write attempt.

Register [apic_spurious] field [reserved_bits] declared as: read only
Write operation attempted at: line 23

Reserved register fields cannot be modified.
```

---

## Последовательность операций с портами

Некоторые устройства требуют строгой последовательности операций. C* позволяет объявить её явно:

```
declare hardware port[8bit] named cmos_address_port
    at port 0x70
    access write only
    managed by module[CMOSDriver]
    note "CMOS address port — write register index before reading data"

declare hardware port[8bit] named cmos_data_port
    at port 0x71
    access read write
    managed by module[CMOSDriver]
    note "CMOS data port — read or write after setting address"

define hardware sequence named read_cmos_register
    managed by module[CMOSDriver]
    note "CMOS requires address write before data read"

    step 1
        hardware write port cmos_address_port
            value register_index
            note "Select CMOS register to read"
    end step

    step 2
        hardware read port cmos_data_port
            into result_byte
            note "Read selected CMOS register value"
    end step

    on sequence violation
        reject with error[HardwareSequenceViolation]
    end on

end hardware sequence
```

Компилятор проверяет что операции с портами выполняются в объявленном порядке. Нарушение последовательности — отклонение компиляции.

---

## Задержки между операциями с железом

Некоторое железо требует задержки между командами:

```
hardware write port keyboard_command_port
    value 0xFF
    note "Send reset command to PS/2 controller"

hardware delay 10 microseconds
    note "PS/2 controller needs time to process reset command"

hardware read port keyboard_status_port
    into status_byte
    note "Read status after reset"
```

`hardware delay` — явная задержка. Компилятор не может оптимизировать или убрать её. Задержка гарантированно выполняется.

---

## Атомарные операции с регистрами

Некоторые операции с регистрами должны быть атомарными — неделимыми. Прерывание посередине недопустимо:

```
hardware atomic
    note "Read-modify-write must not be interrupted"

    hardware read register control_register
        into current_value

    set bit[interrupt_enable] of current_value

    hardware write register control_register
        value current_value
        note "Enable interrupts"

end hardware atomic
```

Внутри блока `hardware atomic` запрещены вызовы функций, выделение памяти и любые операции которые могут занять неопределённое время. Компилятор проверяет это.

---

## Что компилятор проверяет в регистрах и портах

```
✓ register использует at address — port использует at port
✓ Volatile регистры не кэшируются
✓ Режим доступа соблюдается при каждой операции
✓ Reserved поля не изменяются
✓ Аппаратные последовательности соблюдаются
✓ hardware delay присутствует где объявлен
✓ Внутри hardware atomic нет запрещённых операций
✓ Каждый регистр и порт управляется одним модулем
✓ hardware read register генерирует MOV
✓ hardware read port генерирует IN
✓ hardware write port генерирует OUT
```

---

*Готово. Переходим к 5.3 — Прерывания?*
# C* Language Reference
## Раздел 5 — Система и железо
### 5.3 Прерывания

---

## Главное правило прерываний

> Прерывание — это сигнал от железа который останавливает программу в произвольный момент и передаёт управление обработчику. Обработчик прерывания в C* — это особая функция с особыми ограничениями. Эти ограничения не придуманы языком — они продиктованы физической реальностью железа. C* делает их явными и проверяет их соблюдение.

---

## Почему обработчики прерываний особенные

Обычная функция в C* может:
```
Выделять память
Вызывать другие функции с блоками on error
Использовать переменные из внешних областей видимости
Работать сколько угодно долго
```

Обработчик прерывания не может делать ничего из этого:
```
Стек программы может быть в произвольном состоянии
Выделение памяти может нарушить текущую операцию
Долгая работа блокирует другие прерывания
Внешние переменные могут быть в несогласованном состоянии
```

C* делает эти ограничения частью синтаксиса — не документации.

---

## Объявление обработчика прерывания

```
declare interrupt handler named keyboard_interrupt_handler
    for interrupt vector 0x21
    saves registers[all]
    priority normal
    managed by module[KeyboardDriver]
    note "PS/2 keyboard interrupt — triggered on each keypress IRQ1"

    forbidden inside this handler
        memory allocation
        memory release
        function calls with on error blocks
        access to heap variables
        blocking operations
        floating point operations
    end forbidden

    uses only
        hardware port[8bit] named keyboard_data_port
            at port 0x60
            note "Read scan code from keyboard"
        hardware register[8bit] named pic_eoi_register
            at address 0x20
            note "Send End Of Interrupt to PIC"
    end uses only

    body
        declare byte named scan_code on stack is 0

        hardware read port keyboard_data_port
            into scan_code

        store scan_code
            in interrupt buffer[keyboard_scan_buffer]
            on buffer full
                -- буфер переполнен — просто теряем код
                -- в обработчике нельзя обрабатывать ошибки сложно
            end on

        hardware write register pic_eoi_register
            value 0x20
            note "Signal End Of Interrupt to PIC"

    end body

end interrupt handler
```

---

## Блок forbidden

Блок `forbidden` фиксированный для всех обработчиков прерываний. Программист не может его изменить или сократить. Но он **виден в коде** — в духе C* ограничения не скрываются.

```
forbidden inside this handler
    memory allocation           -- heap недоступен
    memory release              -- нельзя освобождать память
    function calls with on error blocks
                                -- сложная обработка ошибок запрещена
    access to heap variables    -- только стек и hardware
    blocking operations         -- нельзя ждать
    floating point operations   -- FPU может быть в чужом состоянии
end forbidden
```

Попытка нарушить любой запрет — отклонение компиляции:

```
COMPILATION REJECTED
Forbidden operation in interrupt handler.

Interrupt handler [keyboard_interrupt_handler]
forbids: memory allocation

Memory allocation attempted at: line 34

Interrupt handlers cannot allocate memory.
The heap may be in an inconsistent state during interrupt.
```

---

## Блок uses only

Обработчик прерывания видит только то что явно объявлено в `uses only`. Никакого доступа к переменным модуля или программы:

```
uses only
    hardware port[8bit] named keyboard_data_port
        at port 0x60
        note "Read scan code from keyboard"
    hardware register[8bit] named pic_eoi_register
        at address 0x20
        note "Send End Of Interrupt to PIC"
    interrupt buffer named keyboard_scan_buffer
        note "Ring buffer for storing scan codes"
end uses only
```

Попытка использовать что-то не объявленное в `uses only`:

```
COMPILATION REJECTED
Unauthorized access in interrupt handler.

Interrupt handler [keyboard_interrupt_handler]
only has access to resources declared in uses only block.

Variable [module_state] not declared in uses only.
Access attempted at: line 28

Add [module_state] to uses only block if access is required.
```

---

## Буферы прерываний

Единственный способ передать данные из обработчика прерывания в основную программу — через специальный буфер прерывания. Он спроектирован для безопасного доступа из двух контекстов одновременно:

```
declare interrupt buffer named keyboard_scan_buffer
    of type byte
    capacity 256
    managed by module[KeyboardDriver]
    note "Ring buffer between keyboard ISR and main keyboard processing"
    on overflow
        discard oldest
    end on
```

Запись в буфер — только из обработчика прерывания:

```
store scan_code
    in interrupt buffer[keyboard_scan_buffer]
    on buffer full
        discard oldest
    end on
```

Чтение из буфера — только из основной программы:

```
declare byte named next_scan_code on stack is 0
declare boolean named has_data on stack is false

read from interrupt buffer[keyboard_scan_buffer]
    into next_scan_code
    on buffer empty
        has_data is false
    on success
        has_data is true
end read
```

Компилятор гарантирует что запись и чтение никогда не происходят одновременно без синхронизации — это встроено в тип `interrupt buffer`.

---

## Сохранение регистров

Обработчик прерывания обязан сохранить и восстановить регистры процессора — иначе прерванная программа получит испорченное состояние:

```
saves registers[all]        -- сохранить все регистры
saves registers[none]       -- не сохранять ничего — только если точно знаешь что делаешь
saves registers[eax, ecx, edx]  -- сохранить конкретные регистры
```

`saves registers[all]` — рекомендуемый вариант для большинства обработчиков. Компилятор генерирует код сохранения и восстановления автоматически.

`saves registers[none]` требует дополнительного поля:

```
declare interrupt handler named fast_timer_handler
    for interrupt vector 0x20
    saves registers[none]
    acknowledging no register preservation
    note "Timer interrupt — only increments counter in dedicated register"
```

Без `acknowledging no register preservation` при `saves registers[none]` — отклонение компиляции.

---

## Приоритет прерываний

```
priority low        -- может быть прервано другими обработчиками
priority normal     -- стандартный приоритет
priority high       -- прерывает обработчики с низким приоритетом
priority critical   -- не может быть прервано ничем
```

Обработчик с `priority critical` имеет дополнительное ограничение — максимальное время выполнения:

```
declare interrupt handler named nmi_handler
    for interrupt vector 0x02
    saves registers[all]
    priority critical
    maximum execution time 100 nanoseconds
    managed by module[SystemCore]
    note "Non-maskable interrupt handler — hardware failure signal"
```

Если компилятор может доказать что тело обработчика займёт больше объявленного времени — отклонение компиляции. Если не может доказать — предупреждение.

---

## Маскирование прерываний

Иногда нужно временно запретить прерывания — например при атомарной операции:

```
disable interrupts
    note "Critical section — modifying shared hardware state"

    hardware write register control_register
        value new_control_value
        note "Update control register atomically"

    hardware memory barrier
        note "Ensure write completes before re-enabling interrupts"

enable interrupts
    note "Critical section complete"
```

`disable interrupts` и `enable interrupts` всегда идут парой. Компилятор проверяет что каждый `disable` имеет парный `enable` на каждом пути через код:

```
COMPILATION REJECTED
Interrupts disabled without re-enable.

disable interrupts at: line 12
Path through error handler at: line 18 exits without enable interrupts.

Every disable interrupts must have a matching enable interrupts
on every possible code path.
```

---

## Вектор прерываний и таблица

Все обработчики прерываний регистрируются в таблице прерываний. C* делает эту таблицу явной:

```
define interrupt table named system_idt
    managed by module[SystemCore]
    note "Interrupt Descriptor Table for x86 system"

    entry vector 0x00
        handler division_error_handler
        note "Division by zero — CPU exception"
    end entry

    entry vector 0x02
        handler nmi_handler
        note "Non-maskable interrupt"
    end entry

    entry vector 0x0E
        handler page_fault_handler
        note "Page fault — memory access violation"
    end entry

    entry vector 0x20
        handler timer_handler
        note "Programmable timer interrupt — IRQ0"
    end entry

    entry vector 0x21
        handler keyboard_interrupt_handler
        note "PS/2 keyboard interrupt — IRQ1"
    end entry

    entry vector 0x80
        handler system_call_handler
        note "System call interface"
    end entry

end interrupt table
```

Таблица прерываний — единственный документ где объявлены все обработчики. Попытка зарегистрировать обработчик на вектор который уже занят — отклонение компиляции:

```
COMPILATION REJECTED
Interrupt vector conflict.

Vector [0x21] already assigned to handler [keyboard_interrupt_handler]
in interrupt table [system_idt] at: line 23

Second handler [ps2_mouse_handler] attempts to use same vector at: line 47

Each interrupt vector can only have one handler.
```

---

## Что компилятор проверяет в прерываниях

```
✓ Блок forbidden присутствует и не изменён
✓ Блок uses only ограничивает доступные ресурсы
✓ Внутри обработчика нет запрещённых операций
✓ Все используемые ресурсы объявлены в uses only
✓ saves registers[none] требует acknowledging
✓ priority critical требует maximum execution time
✓ disable interrupts имеет парный enable на каждом пути
✓ Каждый вектор в таблице прерываний занят одним обработчиком
✓ interrupt buffer используется для передачи данных наружу
✓ Запись в interrupt buffer только из обработчика
✓ Чтение из interrupt buffer только из основной программы
```

---

*Готово. Переходим к 5.4 — Многопоточность?*
# C* Language Reference
## Раздел 5 — Система и железо
### 5.4 Многопоточность

---

## Главное правило многопоточности

> В C* каждый поток владеет своими данными единолично. Общей памяти между потоками не существует. Передача данных между потоками — это передача владения через канал. После передачи отправитель больше не видит данные. Получатель становится единственным владельцем. Это не ограничение — это расширение системы владения из Раздела 2 на параллельное выполнение.

---

## Модель потоков в C*

```
Традиционная модель (C, C++):
    Потоки разделяют память
    Синхронизация через мьютексы и блокировки
    Гонки данных возможны и трудноуловимы

Модель C*:
    Каждый поток владеет своими данными
    Передача только через каналы
    Передача = передача владения
    Гонки данных невозможны синтаксически
```

---

## Объявление потока

```
declare thread named audio_processing_thread
    priority normal
    stack size 65536 bytes
    managed by module[AudioEngine]
    note "Dedicated thread for real-time audio processing"

    receives through channel named audio_input_channel
        of type AudioSample
        capacity 256
        note "Incoming audio samples from capture thread"

    sends through channel named audio_output_channel
        of type AudioSample
        capacity 256
        note "Processed audio samples to playback thread"

    body
        run function process_audio_loop
    end body

end thread
```

Пять обязательных полей:

```
priority        — приоритет потока
stack size      — размер стека явно
managed by      — ответственный модуль
receives through — входящие каналы
sends through   — исходящие каналы
```

Поток без каналов — поток который ни с кем не общается. Это допустимо но требует явного объявления:

```
declare thread named background_logger
    priority low
    stack size 32768 bytes
    managed by module[Logger]
    receives through nothing
    sends through nothing
    note "Standalone logging thread — reads only from its own queue"
    body
        run function logging_loop
    end body
end thread
```

---

## Каналы

Канал — единственный способ передачи данных между потоками. Это типизированная очередь с явной пропускной способностью и моделью владения.

### Объявление канала

```
declare channel named audio_input_channel
    of type AudioSample
    capacity 256
    direction from thread[capture_thread] to thread[audio_processing_thread]
    on overflow
        block sender until space available
    on underflow
        block receiver until data available
    note "Audio sample pipeline between capture and processing"
```

Четыре варианта поведения при переполнении:

```
on overflow
    block sender until space available  -- отправитель ждёт
    discard oldest                       -- выбросить старые данные
    discard newest                       -- выбросить новые данные
    reject with error[ChannelFull]      -- ошибка
end on
```

Четыре варианта поведения при отсутствии данных:

```
on underflow
    block receiver until data available  -- получатель ждёт
    return nothing                        -- получатель получает пустой ответ
    reject with error[ChannelEmpty]      -- ошибка
end on
```

---

## Отправка данных через канал

Отправка — это передача владения. После отправки данные недоступны отправителю:

```
function capture_audio_loop
    receives
        nothing
    returns
        nothing
    body

        repeat forever
            stops when shutdown_requested is equal to true

            declare AudioSample named captured_sample on heap is default

            call read_from_hardware
                with output as owner: captured_sample
                on error[HardwareFailure]
                    reject with error[CaptureFailure]
                on success
                    -- captured_sample заполнен данными
            end call

            send captured_sample as owner
                through channel[audio_input_channel]
                on error[ChannelFull]
                    -- канал переполнен — теряем семпл
                    release captured_sample
                on success
                    -- captured_sample передан
                    -- он больше не наш
            end send

        end repeat

    end body
end function
```

После успешной отправки `as owner` — переменная не существует для отправителя. Компилятор это проверяет:

```
COMPILATION REJECTED
Variable used after channel transfer.

Variable [captured_sample] transferred as owner through channel at: line 24
Variable [captured_sample] no longer exists in this thread.
Access attempted at: line 27

After sending as owner through channel, variable belongs to receiver thread.
```

---

## Получение данных через канал

```
function process_audio_loop
    receives
        nothing
    returns
        nothing
    body

        repeat forever
            stops when shutdown_requested is equal to true

            declare AudioSample named incoming_sample on heap is default

            receive incoming_sample as owner
                from channel[audio_input_channel]
                on error[ChannelEmpty]
                    skip
                on error[ThreadShutdown]
                    stop
                on success
                    -- incoming_sample наш. Мы владельцы.
            end receive

            call apply_audio_effects
                with sample as owner: incoming_sample
                on error[ProcessingFailed]
                    log_message receives "Processing failed" and 2
                    skip
                on success
                    -- incoming_sample передан дальше
            end call

        end repeat

    end body
end function
```

---

## Запуск и остановка потоков

### Запуск

```
program AudioSystem

    body

        call start thread[capture_thread]
            on error[ThreadStartFailed]
                reject with error[SystemInitializationFailed]
            on success
                log_message receives "Capture thread started" and 1
        end call

        call start thread[audio_processing_thread]
            on error[ThreadStartFailed]
                call stop thread[capture_thread]
                    on error[ThreadStopFailed]
                        -- продолжаем несмотря на ошибку
                    on success
                        -- поток остановлен
                end call
                reject with error[SystemInitializationFailed]
            on success
                log_message receives "Processing thread started" and 1
        end call

    end body

end program
```

### Остановка

Поток нельзя убить принудительно — только попросить остановиться:

```
call request stop thread[audio_processing_thread]
    note "Signal thread to finish current work and exit"

call wait for thread[audio_processing_thread]
    timeout 5000 milliseconds
    on timeout
        reject with error[ThreadShutdownTimeout]
    on success
        log_message receives "Processing thread stopped" and 1
end call
```

`request stop` устанавливает флаг. Поток проверяет его через `shutdown_requested`. Принудительного убийства потока не существует в C* — это нарушило бы систему владения. Данные в потоке должны быть корректно освобождены.

---

## Синхронизация через барьеры

Иногда нужно чтобы несколько потоков достигли одной точки прежде чем продолжить:

```
declare thread barrier named initialization_barrier
    for threads
        thread[capture_thread]
        thread[audio_processing_thread]
        thread[playback_thread]
    end for
    note "All audio threads must complete initialization before processing begins"

-- Внутри каждого потока:
call wait at barrier[initialization_barrier]
    on error[BarrierTimeout]
        reject with error[InitializationFailed]
    on success
        -- все потоки готовы
        begin_processing
end call
```

Барьер не передаёт данные — только синхронизирует момент выполнения. Данные передаются только через каналы.

---

## Приоритеты потоков

```
priority idle           -- выполняется только когда все остальные ждут
priority low            -- фоновые задачи
priority normal         -- стандартный приоритет
priority high           -- важные задачи
priority realtime       -- реального времени — особые требования
```

Поток с `priority realtime` имеет дополнительные обязательные поля:

```
declare thread named audio_realtime_thread
    priority realtime
    stack size 65536 bytes
    maximum latency 1000 microseconds
    managed by module[AudioEngine]
    note "Real-time audio processing — strict timing requirements"
    receives through channel named rt_audio_channel
        of type AudioSample
        capacity 64
        note "Low-latency audio channel"
    sends through channel named rt_output_channel
        of type AudioSample
        capacity 64
        note "Processed real-time audio output"
    body
        run function realtime_audio_loop
    end body
end thread
```

`maximum latency` обязателен для `priority realtime`. Компилятор предупреждает если тело потока может превысить объявленную задержку.

---

## Что происходит при завершении потока

Когда поток завершается — все его данные освобождаются. Каналы закрываются. Получатели данных из закрытых каналов получают `error[ThreadShutdown]`:

```
receive incoming_sample as owner
    from channel[audio_input_channel]
    on error[ChannelEmpty]
        skip
    on error[ThreadShutdown]
        -- поток-отправитель завершился
        -- канал закрыт
        -- завершаем и этот поток
        stop
    on success
        -- обрабатываем данные
end receive
```

---

## Что компилятор проверяет в многопоточности

```
✓ Каждый поток имеет явные каналы или declares nothing
✓ Данные передаются между потоками только через каналы
✓ Отправка через канал — всегда as owner
✓ После отправки переменная недоступна отправителю
✓ Получение через канал даёт полное владение
✓ Принудительного убийства потока не существует
✓ request stop всегда имеет парный wait for
✓ priority realtime требует maximum latency
✓ Барьеры не передают данные — только синхронизируют
✓ Закрытый канал обрабатывается через error[ThreadShutdown]
```

---

*Готово. Переходим к 5.5 — Взаимодействие с C?*
# C* Language Reference
## Раздел 5 — Система и железо
### 5.5 Взаимодействие с C

---

## Главное правило взаимодействия с C

> Граница между C* и C — это граница гарантий. По одну сторону компилятор C* знает всё. По другую — ничего. Эту границу нельзя сделать безопасной. Можно только сделать её видимой. Каждый переход через границу явный, задокументированный, и подтверждённый программистом.

---

## Шлюз недоверия — foreign gateway

Любое взаимодействие с C проходит через `foreign gateway`. Это не просто синтаксис — это контракт между программистом и компилятором:

```
Программист говорит: я знаю что здесь гарантии кончаются
Компилятор говорит: хорошо. Я зафиксирую это и буду следить за границей.
```

---

## Объявление foreign gateway для C функции

```
foreign gateway to C function[malloc]
    found in library["libc"]
    found in header["stdlib.h"]

    receives
        integer[unsigned, 64bit] named size_in_bytes
            maps to C type "size_t"
    returns
        raw pointer named allocated_memory
            maps to C type "void*"
            can be null true

    trust level none
    note "Standard C memory allocation — no safety guarantees"

    on call
        acknowledge "Entering unverified C code"
        acknowledge "Memory safety not guaranteed beyond this point"
        acknowledge "Returned pointer not tracked by C* ownership system"
    end on call

    on return
        if allocated_memory is null
            reject with error[OutOfMemory]
        end if
        wrap allocated_memory as hardware pointer
            size equals requested size_in_bytes
            managed by caller
            note "malloc result wrapped as hardware pointer"
    end on return

end foreign gateway
```

---

## Три acknowledge — обязательные подтверждения

Каждый `foreign gateway` обязан содержать три `acknowledge`. Они фиксированы — программист не выбирает их содержимое:

```
on call
    acknowledge "Entering unverified C code"
    acknowledge "Memory safety not guaranteed beyond this point"
    acknowledge "Returned pointer not tracked by C* ownership system"
end on call
```

Убрать или изменить любой из них — отклонение компиляции:

```
COMPILATION REJECTED
Missing acknowledgment in foreign gateway.

foreign gateway [malloc] is missing required acknowledgment:
"Memory safety not guaranteed beyond this point"

All three acknowledgments are mandatory for foreign gateways.
They cannot be modified or removed.
```

---

## Отображение типов C на типы C*

Типы C и типы C* не совпадают напрямую. Каждый параметр gateway объявляет явное отображение:

```
Отображение типов:

C тип              C* тип
─────────────────────────────────────────────────
char               integer[signed, 8bit]
unsigned char      integer[unsigned, 8bit]
short              integer[signed, 16bit]
unsigned short     integer[unsigned, 16bit]
int                integer[signed, 32bit]
unsigned int       integer[unsigned, 32bit]
long               integer[signed, 64bit]
unsigned long      integer[unsigned, 64bit]
float              float[32bit]
double             float[64bit]
void*              raw pointer
char*              raw pointer — text conversion required
size_t             integer[unsigned, 64bit]
int*               pointer[to integer[signed, 32bit]]
```

Отображение объявляется явно для каждого параметра:

```
receives
    integer[signed, 32bit] named file_descriptor
        maps to C type "int"
    raw pointer named buffer_address
        maps to C type "void*"
    integer[unsigned, 64bit] named byte_count
        maps to C type "size_t"
```

---

## Вызов C функции через gateway

```
foreign gateway to C function[write]
    found in library["libc"]
    found in header["unistd.h"]

    receives
        integer[signed, 32bit] named file_descriptor
            maps to C type "int"
        raw pointer named buffer_address
            maps to C type "const void*"
        integer[unsigned, 64bit] named byte_count
            maps to C type "size_t"
    returns
        integer[signed, 64bit] named bytes_written
            maps to C type "ssize_t"
            on negative value
                reject with error[WriteFailure]

    trust level none
    note "POSIX write syscall wrapper"

    on call
        acknowledge "Entering unverified C code"
        acknowledge "Memory safety not guaranteed beyond this point"
        acknowledge "Returned pointer not tracked by C* ownership system"
    end on call

    on return
        if bytes_written is less than 0
            reject with error[WriteFailure]
        end if
    end on return

end foreign gateway
```

Использование gateway:

```
declare array[byte, 256] named output_buffer
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]

declare integer[signed, 64bit] named written on stack is 0

call foreign[write]
    with file_descriptor as copy: 1
    with buffer_address: raw address of output_buffer
    with byte_count as copy: count of output_buffer
    on error[WriteFailure]
        log_message receives "Write failed" and 3
        reject with error[IOFailure]
    on success
        written is bytes_written
end call
```

Слова `raw address of` — получить сырой адрес без системы владения C*. Доступно только при вызове через `foreign gateway`.

---

## Экспорт функций C* для вызова из C

C* может предоставить свои функции для вызова из C кода:

```
export to C function named cstar_process_audio
    as C name "cstar_process_audio"
    calling convention cdecl

    receives from C
        raw pointer named input_data
            maps to C type "const void*"
            minimum size 512 bytes
            note "Caller must ensure pointer validity"
        integer[unsigned, 32bit] named data_size
            maps to C type "unsigned int"
    returns to C
        integer[signed, 32bit] named result_code
            maps to C type "int"
            value 0 means success
            value minus 1 means failure

    trust level none
    note "Exported audio processing function for C consumers"

    on entry from C
        acknowledge "Data from C has no safety guarantees"
        acknowledge "Input pointer not validated by C* system"
        acknowledge "Caller responsible for pointer lifetime"

        validate input_data is not null
            on null
                return to C value minus 1
        end validate

        validate data_size is greater than 0
            on invalid
                return to C value minus 1
        end validate
    end on entry

    body
        declare array[byte, data_size] named safe_input
            on heap
            all elements is 0
            on allocation failure
                return to C value minus 1

        copy from raw pointer input_data
            size data_size bytes
            into safe_input
            on error[CopyFailed]
                release safe_input
                return to C value minus 1

        call process_audio_internal
            with data as owner: safe_input
            on error[ProcessingFailed]
                return to C value minus 1
            on success
                return to C value 0
        end call

    end body

end export
```

Блок `on entry from C` обязателен. Три `acknowledge` обязательны. Данные из C немедленно копируются в безопасные структуры C* — после этого на них распространяются все гарантии языка.

---

## Уровни доверия

```
trust level none        -- никаких гарантий. Максимальная осторожность.
trust level partial     -- некоторые гарантии задокументированы вызываемой стороной
trust level documented  -- полная документация есть, но проверить нельзя
```

`trust level none` — единственный уровень который компилятор не проверяет. Два других требуют дополнительной документации:

```
foreign gateway to C function[pthread_mutex_lock]
    found in library["libpthread"]
    found in header["pthread.h"]

    trust level documented
    documentation "POSIX standard guarantees atomic lock acquisition"
    documentation "Returns 0 on success, error code on failure"
    documentation "Does not modify any data — only synchronization primitive"

    receives
        raw pointer named mutex_pointer
            maps to C type "pthread_mutex_t*"
    returns
        integer[signed, 32bit] named error_code
            maps to C type "int"
            value 0 means success

    on call
        acknowledge "Entering unverified C code"
        acknowledge "Memory safety not guaranteed beyond this point"
        acknowledge "Returned pointer not tracked by C* ownership system"
    end on call

    on return
        if error_code is not equal to 0
            reject with error[MutexLockFailed]
        end if
    end on return

end foreign gateway
```

---

## Реестр внешних функций

Все foreign gateway проекта собираются в одном файле `.cstar-foreign`:

```
foreign registry named ProjectExternalDependencies

    library["libc"]
        includes gateway[malloc]
        includes gateway[free]
        includes gateway[write]
        includes gateway[read]
        includes gateway[open]
        includes gateway[close]
    end library

    library["libpthread"]
        includes gateway[pthread_mutex_lock]
        includes gateway[pthread_mutex_unlock]
    end library

    library["libm"]
        includes gateway[sin]
        includes gateway[cos]
        includes gateway[sqrt]
    end library

end foreign registry
```

Вызов C функции без зарегистрированного gateway — отклонение компиляции:

```
COMPILATION REJECTED
Unregistered foreign function call.

Function [printf] called at: line 34
No foreign gateway declared for [printf].

All C function calls must go through a declared foreign gateway.
Add a gateway declaration to your .cstar-foreign file.
```

---

## Что компилятор проверяет во взаимодействии с C

```
✓ Каждый вызов C функции имеет зарегистрированный gateway
✓ Три обязательных acknowledge присутствуют и не изменены
✓ Отображение типов объявлено для каждого параметра
✓ on return проверяет возвращаемое значение
✓ Экспортируемые функции имеют блок on entry from C
✓ Данные из C копируются в безопасные структуры немедленно
✓ raw address of используется только внутри foreign gateway
✓ Все gateway зарегистрированы в .cstar-foreign файле
✓ trust level partial и documented имеют documentation поля
```

---

## Раздел 5 завершён

```
5.1 Прямой доступ к памяти      ✓
5.2 Регистры и порты             ✓
5.3 Прерывания                   ✓
5.4 Многопоточность              ✓
5.5 Взаимодействие с C           ✓
```

C* теперь умеет работать с железом напрямую, управлять регистрами и портами, обрабатывать прерывания, запускать параллельные потоки и говорить с существующим C кодом. Всё явно. Всё задокументировано. Границы гарантий видны.

---

# C* Language Reference
## Раздел 6 — Компилятор и уровень
### 6.1 Стадии компиляции

---

## Главное правило компиляции

> Компилятор C* работает прозрачно. Каждая стадия видна программисту. Каждое решение объяснено. Компилятор не делает ничего скрытого — ни при анализе кода, ни при генерации машинных инструкций.

---

## Семь стадий компиляции

```
Stage 1 — Lexical Analysis       Разбор символов на слова
Stage 2 — Syntax Analysis        Проверка структуры кода
Stage 3 — Type Checking          Проверка типов и совместимости
Stage 4 — Level Traversal        Проход уровня — главная проверка C*
Stage 5 — Optimization           Допустимые оптимизации
Stage 6 — Code Generation        Генерация машинных инструкций
Stage 7 — Linking                Сборка модулей в единую программу
```

Стадии выполняются строго по порядку. Если стадия завершилась ошибкой — следующая не начинается.

---

## Как выглядит компиляция в обычном режиме

```
C* Compiler v1.0
Compiling project: AudioSystem
Target: x86-64 Linux
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Stage 1 — Lexical Analysis
    AudioEngine.cstar                             ✓
    LowLevelDriver.cstar                          ✓
    StdMath.cstar                                 ✓
    Lexical analysis complete — 3 files processed.

Stage 2 — Syntax Analysis
    AudioEngine.cstar                             ✓
    LowLevelDriver.cstar                          ✓
    StdMath.cstar                                 ✓
    Syntax analysis complete — no errors found.

Stage 3 — Type Checking
    Checking type declarations...                 ✓
    Checking type compatibility...                ✓
    Checking conversions...                       ✓
    Type checking complete — no errors found.

Stage 4 — Level Traversal
    Building ownership graph...                   ✓
    Checking lifetime rules...                    ✓
    Checking memory model rules...                ✓
    Checking user defined rules...                ✓
    Level traversal complete — all paths valid.

Stage 5 — Optimization
    Folding constants...                          ✓
    Removing unreachable code...                  ✓
    Optimization complete — 3 optimizations applied.

Stage 6 — Code Generation
    AudioEngine.cstar                             ✓
    LowLevelDriver.cstar                          ✓
    StdMath.cstar                                 ✓
    Code generation complete — 3 object files created.

Stage 7 — Linking
    Linking object files...                       ✓
    Resolving module dependencies...              ✓
    Linking complete — executable created.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Result:  SUCCESS
Output:  ./build/AudioSystem
Size:    47,832 bytes
Time:    1.24 seconds
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Как выглядит компиляция с ошибкой

```
C* Compiler v1.0
Compiling project: AudioSystem
Target: x86-64 Linux
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Stage 1 — Lexical Analysis
    AudioEngine.cstar                             ✓
    LowLevelDriver.cstar                          ✓
    Lexical analysis complete — 2 files processed.

Stage 2 — Syntax Analysis
    AudioEngine.cstar                             ✓
    LowLevelDriver.cstar

    ✗ SYNTAX ERROR at LowLevelDriver.cstar line 34

    Expected keyword: named
    Found: "="

    declare integer[signed, 32bit] = buffer_size is 0
                                   ^
    Correct form:
    declare integer[signed, 32bit] named buffer_size is 0

    Compilation stopped at Stage 2.
    Fix syntax error before compilation can continue.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Result:  REJECTED at Stage 2 — Syntax Analysis
Time:    0.12 seconds
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Stage 1 — Lexical Analysis

Компилятор читает файлы символ за символом и собирает их в слова — токены.

```
Что делает:
    Читает каждый символ файла
    Собирает символы в слова языка
    Проверяет что все символы принадлежат алфавиту C*
    Распознаёт ключевые слова, имена, числа, строки

Что находит:
    Недопустимые символы — ; ? @ $ % ^
    Неизвестные последовательности символов
    Незакрытые текстовые литералы

Что НЕ находит:
    Ошибки структуры — это Stage 2
    Ошибки типов — это Stage 3
```

В подробном режиме:

```
Stage 1 — Lexical Analysis [VERBOSE]
    AudioEngine.cstar
        Tokens found: 2847
        Keywords: 634
        Identifiers: 891
        Literals: 122
        Comments stripped: 47
        Time: 0.03 seconds                        ✓
```

---

## Stage 2 — Syntax Analysis

Компилятор проверяет что слова собраны в правильные конструкции.

```
Что делает:
    Проверяет структуру каждого блока
    Проверяет порядок элементов программы
    Проверяет что каждый открытый блок закрыт
    Проверяет отступы

Что находит:
    Пропущенные ключевые слова
    Неправильный порядок блоков
    Незакрытые блоки
    Нарушения отступов

Что НЕ находит:
    Несовместимые типы — это Stage 3
    Нарушения владения — это Stage 4
```

Синтаксическая ошибка останавливает компиляцию немедленно. Одна ошибка — одна остановка. Продолжать при сломанной структуре бессмысленно.

---

## Stage 3 — Type Checking

Компилятор проверяет что типы используются правильно.

```
Что делает:
    Проверяет совместимость типов при присвоении
    Проверяет что преобразования явные и обработанные
    Проверяет что операции допустимы для данных типов
    Проверяет что параметры функций совпадают с объявлением
    Проверяет ограничения обобщённых типов

Что находит:
    Несовместимые типы
    Неявные преобразования
    Недопустимые операции над типами
    Нарушения ограничений where в обобщённых типах
```

В отличие от Stage 2 — при ошибках типов компилятор показывает все найденные ошибки за один проход:

```
Stage 3 — Type Checking

    ✗ TYPE ERROR 1 of 2
    AudioEngine.cstar line 47

    Cannot assign integer[unsigned, 32bit] to integer[signed, 16bit]
    Implicit conversion forbidden.
    Use controlled convert with overflow handling.

    ✗ TYPE ERROR 2 of 2
    AudioEngine.cstar line 89

    Generic type [Buffer] requires ElementType in segment[Numbers]
    Provided type [text] lives in segment[Text]

    2 type errors found.
    Fix all type errors before compilation can continue.
```

---

## Stage 4 — Level Traversal

Главная стадия компилятора C*. Компилятор строит уровень и проходит его.

```
Что делает:
    Строит граф владения для каждой переменной
    Прослеживает время жизни каждой переменной
    Проверяет правила памяти на каждом пути через код
    Проверяет пользовательские модели памяти
    Проверяет правила модулей и шлюзов
    Проверяет правила потоков и каналов

Что находит:
    Нарушения владения
    Нарушения времени жизни
    Висячие указатели
    Конфликты правил пользовательских моделей
    Пути без release для heap переменных
    Утечки памяти
```

При ошибках уровня — показывает все нарушения за один проход:

```
Stage 4 — Level Traversal

    Building ownership graph...                   ✓
    Checking lifetime rules...

    ✗ LEVEL VIOLATION 1 of 3
    AudioEngine.cstar line 52

    Lifetime violation.
    Variable [local_buffer] on stack dies at end of if block line 61
    Pointer [result_ptr] returned from function — outlives its target.

    ✗ LEVEL VIOLATION 2 of 3
    AudioEngine.cstar line 78

    Double ownership.
    Variable [audio_data] transferred as owner at line 78
    Second transfer attempted at line 91

    ✗ LEVEL VIOLATION 3 of 3
    AudioEngine.cstar line 103

    Missing release.
    Variable [temp_buffer] on heap declared at line 103
    Path through error handler at line 112 exits without release.

    3 level violations found.
    Fix all violations before compilation can continue.
```

---

## Stage 5 — Optimization

Компилятор применяет допустимые оптимизации. Оптимизации никогда не меняют смысл программы — только устраняют избыточность.

```
Что оптимизирует:
    Константные выражения — вычисляет на этапе компиляции
    Мёртвый код — удаляет недостижимые ветки
    Инлайнинг — вставляет тело простых функций на место вызова
    Регистры — размещает часто используемые переменные в регистрах

Что НИКОГДА не оптимизирует:
    hardware операции — порядок всегда сохраняется
    volatile регистры — каждое обращение к железу
    hardware memory barrier — всегда выполняется
    hardware delay — всегда выполняется точно
    Явные шаги пользователя — одна инструкция C* один смысл
```

В обычном режиме показывает только количество оптимизаций. В подробном — каждую:

```
Stage 5 — Optimization [VERBOSE]
    Constant folding:
        AudioEngine.cstar line 23: max_size multiply by 2 → 2048       ✓
        AudioEngine.cstar line 67: buffer_count plus 0 → buffer_count   ✓
    Dead code elimination:
        AudioEngine.cstar line 145: unreachable branch removed          ✓
    Inline expansion:
        AudioEngine.cstar line 201: get_sample_count inlined            ✓
    3 optimizations applied.
```

---

## Stage 6 — Code Generation

Компилятор генерирует машинные инструкции. RISC принцип — каждая инструкция C* порождает минимальное количество машинных инструкций.

```
Что делает:
    Преобразует каждую операцию C* в машинные инструкции
    Размещает переменные в регистрах или на стеке
    Генерирует код для hardware операций
    Генерирует объектные файлы

Гарантии:
    plus → одна инструкция сложения
    multiply → одна инструкция умножения
    hardware write register → одна инструкция MOV
    hardware write port → одна инструкция OUT
    Никаких скрытых вызовов функций за простым синтаксисом
```

В подробном режиме показывает соответствие C* инструкций машинным:

```
Stage 6 — Code Generation [VERBOSE]
    AudioEngine.cstar line 34:
        result is first_number plus second_number
        → ADD rax, rbx                                                  ✓

    AudioEngine.cstar line 47:
        hardware write port keyboard_command_port value 0xFF
        → MOV al, 0xFF
        → OUT 0x64, al                                                  ✓
```

---

## Stage 7 — Linking

Компилятор собирает объектные файлы модулей в единую программу.

```
Что делает:
    Разрешает зависимости между модулями
    Проверяет совместимость версий
    Проверяет что все gateway объявлены
    Собирает финальный исполняемый файл

Что находит:
    Неразрешённые зависимости
    Конфликты версий модулей
    Незарегистрированные foreign gateway
    Циклические зависимости которые пропустила карта модулей
```

---

## Режимы вывода

Переключение в коде — первая строка первого файла:

```
compiler mode silent     -- только результат и ошибки
compiler mode normal     -- стадии и результат (по умолчанию)
compiler mode verbose    -- всё включая внутренние решения
```

Переключение в UI — кнопка рядом с кнопкой компиляции. Оба способа эквивалентны.

---

## Что компилятор гарантирует программисту

```
✓ Каждая стадия видна в обычном и подробном режиме
✓ Каждая ошибка содержит место, причину и правильную форму
✓ Синтаксическая ошибка — немедленная остановка
✓ Ошибки типов и уровня — все за один проход
✓ Оптимизации никогда не меняют смысл программы
✓ Одна инструкция C* — минимум машинных инструкций
✓ Время компиляции всегда показано
```

---

*Готово. Переходим к 6.2 — Система уровня?*

# C* Language Reference
## Раздел 6 — Компилятор и уровень
### 6.2 Система уровня

---

## Главное правило системы уровня

> Уровень — это путь от начала до конца компиляции. Каждое правило языка создаёт узкое место на этом пути. Компилятор проходит уровень и проверяет — есть ли выход из каждого узкого места. Если на каком-то шаге выхода нет — это смерть. Компилятор останавливается и сообщает где и почему.

---

## Геометрия уровня

```
Без правил — широкий открытый путь:

[Старт]━━━━━━━━━━━━━━━━━━━━━━━━━━[Компиляция]


С правилами — узкие места которые нужно пройти:

[Старт]━[узко]━[узко]━[узко]━[узко]━[Компиляция]
                         │
                    нет выхода
                       смерть
```

Каждое правило C* — это узкое место. Программист пишет код — код либо проходит через узкое место либо нет. Компилятор не угадывает — он проверяет геометрически.

---

## Как строится уровень

Уровень строится в четыре шага на Stage 4 компиляции:

### Шаг 1 — Сбор правил

Компилятор собирает все правила которые применяются к данному коду:

```
Правила языка C* — всегда активны:
    Правило владения: один владелец в каждый момент
    Правило времени жизни: указатель не переживает цель
    Правило null: указатель проверяется перед использованием
    Правило инициализации: переменная всегда имеет начальное значение

Правила модели памяти — из объявления модуля:
    Manual: каждый allocate имеет release
    Region: каждый регион закрыт на каждом пути
    Пользовательская модель: правила из define memory_model

Пользовательские правила — из объявлений типов:
    Инварианты типов
    Диапазоны значений
    Иммутабельность
```

### Шаг 2 — Построение графа путей

Компилятор строит граф всех возможных путей через код:

```
function example
    body

        declare integer[signed, 32bit] named value on heap is 0

        if condition_a                  ← ветка А
            call function_one           │
                on error[...]           │ путь А1
                on success              │ путь А2
            end call                    │
        otherwise                       ← ветка Б
            call function_two           │ путь Б1
                on error[...]           │
                on success              │ путь Б2
            end call
        end otherwise
        end if

        release value                   ← конец

    end body
end function
```

Граф путей:
```
Старт
  │
  ├── Путь А1: condition_a → function_one → error → ?
  ├── Путь А2: condition_a → function_one → success → release
  ├── Путь Б1: not condition_a → function_two → error → ?
  └── Путь Б2: not condition_a → function_two → success → release
```

### Шаг 3 — Наложение узких мест

Каждое правило накладывается на каждый путь как узкое место:

```
Правило: каждая heap переменная имеет release на каждом пути

Путь А2: ... → release value ✓ выход есть
Путь Б2: ... → release value ✓ выход есть
Путь А1: ... → error → ??? нет release → выхода нет → СМЕРТЬ
Путь Б1: ... → error → ??? нет release → выхода нет → СМЕРТЬ
```

### Шаг 4 — Проверка проходимости

Компилятор проверяет каждый путь через каждое узкое место. Если хотя бы один путь не имеет выхода — уровень не пройден.

---

## Узкие места языка

### Узкое место владения

```
Вопрос компилятора на этом узком месте:
"В этой точке кода — сколько владельцев у этих данных?"

Выход есть если: ровно один
Смерть если: ноль или больше одного
```

```
declare integer[signed, 32bit] named data on heap is 0

-- Путь через код:
send data as owner through channel[...]    ← владелец передан
                                           ← data не существует здесь
call process                               ← попытка использовать data
    with value as copy: data              ← СМЕРТЬ — владельца нет
```

---

### Узкое место времени жизни

```
Вопрос компилятора на этом узком месте:
"В этой точке кода — жива ли цель этого указателя?"

Выход есть если: цель жива
Смерть если: цель умерла или может умереть
```

```
declare pointer[to integer[signed, 32bit]] named ptr on stack is null

if condition
    declare integer[signed, 32bit] named target on stack is 42
    ptr is address of target as access
end if                                     ← target умер здесь

value at ptr is 100                        ← СМЕРТЬ — цель мертва
```

---

### Узкое место null проверки

```
Вопрос компилятора на этом узком месте:
"В этой точке кода — проверен ли этот указатель на null?"

Выход есть если: проверка была на всех входящих путях
Смерть если: хотя бы один входящий путь без проверки
```

```
declare pointer[to byte] named buffer_ptr on stack is null

-- Путь А: проверка есть
if some_condition
    if buffer_ptr is not null
        value at buffer_ptr is 42         ← выход есть
    end if
end if

-- Путь Б: проверки нет
if other_condition
    value at buffer_ptr is 42             ← СМЕРТЬ
end if
```

---

### Узкое место release

```
Вопрос компилятора на этом узком месте:
"На каждом пути через этот код — освобождена ли эта heap переменная?"

Выход есть если: release на каждом пути
Смерть если: хотя бы один путь без release
```

```
declare byte named buffer on heap is 0

call read_data
    with output as access: buffer
    on error[ReadFailed]
        reject with error[ReadFailed]      ← СМЕРТЬ — нет release перед reject
    on success
        -- продолжаем
end call

release buffer
```

Правильно:

```
call read_data
    with output as access: buffer
    on error[ReadFailed]
        release buffer                     ← выход есть
        reject with error[ReadFailed]
    on success
        -- продолжаем
end call

release buffer                             ← выход есть
```

---

## Стыковка уровней модулей

Когда модуль A передаёт данные модулю B — уровни двух модулей стыкуются в точке передачи.

```
Уровень модуля A:              Уровень модуля B:
[Старт]━[узко]━[узко]━[Выход]━━━[Вход]━[узко]━[узко]━[Компиляция]
                              ↑
                          точка стыка
                          шлюз здесь
```

Компилятор проверяет что узкие места в точке стыка совместимы:

```
Модуль A выходит с: pointer[to byte] as access
Модуль B ожидает: pointer[to byte] as access

Проверка:
    Тип совпадает?                  ✓
    Вид передачи совместим?         ✓
    Время жизни перекрывается?      ✓
    Шлюз объявлен?                  ✓

Стык проходим — уровни состыкованы.
```

Если стык не проходим:

```
LEVEL VIOLATION — Module boundary mismatch.

Module [AudioEngine] exits with:
    pointer[to AudioSample] as owner

Module [EffectsProcessor] expects:
    pointer[to AudioSample] as access

owner transfer consumed the data.
Receiver cannot access data that no longer exists in sender.

Declare matching transfer mode in gateway.
```

---

## Уровень пользовательской модели памяти

Пользовательская модель памяти добавляет свои узкие места к общему уровню:

```
define memory_model[RingBuffer]
    rules
        rule single_owner
            at every moment exactly one owner exists
        end rule
        rule overflow_behavior
            programmer must declare overflow handling
        end rule
    end rules
```

Эти правила становятся узкими местами:

```
[Старт]
  ↓
[Узкое место C* — владение]
  ↓
[Узкое место C* — время жизни]
  ↓
[Узкое место RingBuffer — single_owner]    ← пользовательское
  ↓
[Узкое место RingBuffer — overflow]        ← пользовательское
  ↓
[Компиляция]
```

Пользовательские узкие места проверяются после встроенных. Порядок фиксированный — сначала язык, потом модель памяти, потом пользовательские правила типов.

---

## Конфликт правил — смерть до уровня

Если правила противоречат друг другу — уровень невозможно построить. Это особый вид смерти — до начала прохода:

```
define memory_model[BadModel]
    rules
        rule single_owner
            at every moment exactly one owner exists
        end rule
        rule free_copying
            data can be copied to any number of receivers as owner
        end rule
    end rules
```

```
LEVEL BUILD FAILED — Rules conflict detected.

Cannot build level for memory_model [BadModel].

Rule [single_owner]: exactly one owner at all times
Rule [free_copying]: unlimited owner transfers as owner

Each copy as owner creates a new owner.
Multiple owners violate rule [single_owner].

Level cannot be traversed because entry point is already dead.
Fix conflicting rules before compilation can proceed.
```

---

## Визуализация уровня в подробном режиме

В режиме `compiler mode verbose` компилятор показывает граф уровня:

```
Stage 4 — Level Traversal [VERBOSE]

Building level for function [initialize_audio]:

Paths found: 4
    Path 1: success → success → release         [length 3]
    Path 2: success → error   → release → reject [length 4]
    Path 3: error   → release → reject           [length 3]
    Path 4: error   → reject                     [length 2]

Applying narrow points:

    Narrow point: null check for [buffer_ptr]
        Path 1: checked at line 12               ✓
        Path 2: checked at line 12               ✓
        Path 3: never reaches [buffer_ptr]       ✓
        Path 4: never reaches [buffer_ptr]       ✓

    Narrow point: release for [audio_buffer]
        Path 1: released at line 34              ✓
        Path 2: released at line 28              ✓
        Path 3: released at line 19              ✓
        Path 4: ✗ no release found               DEAD

Level died at Path 4, narrow point [release for audio_buffer].

All paths must pass all narrow points.
```

---

## Что система уровня гарантирует

```
✓ Каждый путь через код проверен
✓ Ни один путь не пропущен — даже редкие пути через ошибки
✓ Пользовательские правила проверяются наравне со встроенными
✓ Конфликтующие правила отклоняются до начала прохода
✓ Стыки модулей проверяются как часть уровня
✓ Подробный режим показывает весь граф путей
```

---

*Готово. Переходим к 6.3 — Сообщения компилятора?*
# C* Language Reference
## Раздел 6 — Компилятор и уровень
### 6.3 Сообщения компилятора

---

## Главное правило сообщений

> Сообщение компилятора C* — это не просто указание на ошибку. Это объяснение что пошло не так, почему это проблема, и как это исправить. Программист никогда не должен гадать что означает сообщение компилятора.

---

## Философия сообщений

Каждое сообщение отвечает на четыре вопроса:

```
Что случилось?      — тип проблемы
Где случилось?      — точное место в коде
Почему проблема?    — объяснение правила которое нарушено
Как исправить?      — конкретное предложение
```

Сообщение без ответа на любой из четырёх вопросов — неполное сообщение. Это так же недопустимо как неполный код.

---

## Структура сообщения

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[УРОВЕНЬ СЕРЬЁЗНОСТИ] [ТИП ПРОБЛЕМЫ]
File: [имя файла]
Line: [номер строки]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    [описание проблемы]

Код с проблемой:
    [строка кода]
    [указатель на проблемное место]

Почему это проблема:
    [объяснение правила]

Как исправить:
    [конкретное предложение]

Правило: [название правила из книги C*]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Четыре уровня серьёзности

### SYNTAX ERROR — синтаксическая ошибка

Компилятор не понимает что написано. Компиляция останавливается немедленно.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
SYNTAX ERROR — Unexpected token
File: AudioEngine.cstar
Line: 34
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Найден неожиданный символ "=" там где ожидалось
    ключевое слово "named".

Код с проблемой:
    declare integer[signed, 32bit] = buffer_size is 0
                                   ^
                              неожиданный "="

Почему это проблема:
    Объявление переменной требует ключевое слово "named"
    между типом и именем переменной.

Как исправить:
    declare integer[signed, 32bit] named buffer_size is 0

Правило: Раздел 1.4 — Объявление переменной
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

### TYPE ERROR — ошибка типов

Типы несовместимы или преобразование недопустимо. Компилятор показывает все ошибки типов за один проход.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
TYPE ERROR [1 of 2] — Implicit conversion forbidden
File: AudioEngine.cstar
Line: 47
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Попытка присвоить integer[unsigned, 32bit]
    переменной типа integer[signed, 16bit] без явного
    преобразования.

Код с проблемой:
    sample_level is buffer_capacity
    ~~~~~~~~~~~~    ~~~~~~~~~~~~~~~~
    signed 16bit    unsigned 32bit

Почему это проблема:
    Неявные преобразования запрещены в C*.
    integer[unsigned, 32bit] может содержать значения
    которые не помещаются в integer[signed, 16bit].
    Потеря данных должна быть явно обработана.

Как исправить:
    controlled convert buffer_capacity to integer[signed, 16bit]
        into sample_level
        on overflow
            reject with error[ValueTooLarge]

Правило: Раздел 4.5 — Контролируемое преобразование
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

### LEVEL VIOLATION — нарушение уровня

Правило владения, времени жизни или пользовательской модели нарушено. Компилятор показывает все нарушения за один проход.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL VIOLATION [1 of 2] — Missing release on error path
File: AudioEngine.cstar
Line: 78
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Переменная [audio_buffer] выделена на куче но не
    освобождена на пути через обработчик ошибки.

Код с проблемой:
    declare byte named audio_buffer on heap is 0    -- line 61
    ...
    call read_audio_data
        on error[ReadFailed]
            reject with error[ReadFailed]           -- line 78
            ↑
            audio_buffer не освобождён перед этим reject

Почему это проблема:
    Переменные на куче обязаны быть освобождены на
    каждом пути через код. Путь через error[ReadFailed]
    завершается без release audio_buffer.
    Это утечка памяти.

Как исправить:
    call read_audio_data
        on error[ReadFailed]
            release audio_buffer        ← добавить release
            reject with error[ReadFailed]

Правило: Раздел 2.1 — Правила кучи
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

### WARNING — предупреждение

Код корректен но есть потенциальная проблема. Компиляция продолжается. Предупреждения не блокируют компиляцию но отображаются всегда.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
WARNING — Realtime thread may exceed latency
File: AudioEngine.cstar
Line: 134
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Поток [audio_realtime_thread] объявлен с
    maximum latency 500 microseconds.
    Компилятор не может доказать что тело потока
    укладывается в это время.

Код с проблемой:
    declare thread named audio_realtime_thread
        priority realtime
        maximum latency 500 microseconds    -- line 134
        ...

Почему это проблема:
    Функция [apply_reverb_effect] вызывается внутри
    потока и содержит цикл с неизвестным числом итераций.
    Худший случай может превысить 500 microseconds.

Как исправить:
    Вариант 1: Увеличить maximum latency
    Вариант 2: Ограничить число итераций в apply_reverb_effect
    Вариант 3: Вынести apply_reverb_effect в поток без realtime

Правило: Раздел 5.4 — Приоритеты потоков
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Сообщения с контекстом из нескольких файлов

Когда проблема затрагивает несколько файлов — сообщение показывает оба места:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL VIOLATION — Module boundary mismatch
File: AudioEngine.cstar + LowLevelDriver.cstar
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Модуль [AudioEngine] передаёт данные модулю
    [LowLevelDriver] с несовместимым видом передачи.

Код в AudioEngine.cstar line 89:
    send audio_buffer as owner
        through gateway[EngineToDriver]
        ↑
        передаёт as owner

Код в LowLevelDriver.cstar line 12:
    gateway[EngineToDriver]
        transfers pointer[to byte] as access only
                                    ↑
                                    ожидает as access

Почему это проблема:
    Gateway объявляет передачу as access only.
    AudioEngine пытается передать as owner.
    После передачи as owner данные не существуют
    в отправителе — получатель не может обратиться
    к уже несуществующим данным через access.

Как исправить:
    Вариант 1: Изменить send на as access в AudioEngine
    Вариант 2: Изменить gateway на as owner если передача
               владения была целью

Правило: Раздел 2.3 — Шлюзы между моделями памяти
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Сообщение о конфликте правил модели памяти

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL BUILD FAILED — Memory model rules conflict
File: AudioEngine.cstar
Line: 12
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Пользовательская модель памяти [RingBuffer]
    содержит правила которые противоречат друг другу.
    Уровень невозможно построить.

Конфликтующие правила:

    rule [single_owner] объявлен в line 15:
        at every moment exactly one owner exists

    rule [free_copying] объявлен в line 21:
        data can be copied to any number of receivers as owner

Почему это проблема:
    Каждая копия as owner создаёт нового владельца.
    При нескольких копиях существует несколько владельцев.
    Это прямо нарушает правило single_owner.
    Уровень мёртв в точке входа — ни один путь не проходим.

Как исправить:
    Вариант 1: Удалить rule [free_copying]
               Используйте as copy вместо as owner для копий

    Вариант 2: Изменить rule [single_owner]
               Разрешите несколько владельцев если это цель

    Вариант 3: Добавить правило передачи владения
               при котором предыдущий владелец теряет доступ

Правило: Раздел 2.4 — Пользовательские модели памяти
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Итоговая сводка после компиляции

После завершения всех стадий компилятор показывает сводку:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
COMPILATION SUMMARY
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Files processed:    3
Lines of code:      1247

Syntax errors:      0
Type errors:        0
Level violations:   0
Warnings:           1

    WARNING at AudioEngine.cstar line 134
    Realtime thread may exceed latency

Optimizations:      3
    Constant folding:       2
    Dead code removed:      1

Result:  SUCCESS with 1 warning
Output:  ./build/AudioSystem
Size:    47,832 bytes
Time:    1.24 seconds
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Успешная компиляция с предупреждениями не блокируется. Но предупреждения всегда видны — их нельзя скрыть.

---

## Что компилятор гарантирует в сообщениях

```
✓ Каждое сообщение отвечает на четыре вопроса
✓ Каждое сообщение содержит ссылку на правило книги C*
✓ Код с проблемой показан с указателем на место
✓ Предложение по исправлению конкретное — не общее
✓ Многофайловые проблемы показывают оба места
✓ Предупреждения не скрываются никогда
✓ Итоговая сводка всегда показана после компиляции
```

---

*Готово. Переходим к 6.4 — Пользовательские правила компилятора?*

# C* Language Reference
## Раздел 6 — Компилятор и уровень
### 6.4 Пользовательские правила компилятора

---

## Главное правило пользовательских правил

> Программист может добавить собственные правила к уровню. Компилятор будет проверять их так же строго как встроенные правила языка. Пользовательское правило — это не комментарий и не документация. Это узкое место на уровне которое код обязан пройти.

---

## Зачем нужны пользовательские правила

Встроенные правила C* покрывают безопасность памяти и типов. Но у каждого проекта есть свои инварианты которые компилятор не знает:

```
-- Проектные правила которые компилятор не знает сам:
"Функции работающие с аудио никогда не выделяют память"
"Все публичные функции модуля драйвера логируют вызов"
"Размер буфера всегда кратен 512"
"Функции реального времени не вызывают функции с on error блоками"
```

Без пользовательских правил эти инварианты существуют только в документации. С пользовательскими правилами — компилятор их проверяет.

---

## Объявление пользовательского правила

```
define compiler rule named NoHeapInAudioFunctions
    description "Audio processing functions must never allocate heap memory"
    severity error
    applies to functions
        tagged with[audio_processing]
    end applies to

    forbids inside tagged functions
        memory allocation on heap
        memory release
        declare ... on heap
    end forbids

    on violation
        message "Audio function allocates heap memory"
        hint "Use stack allocation or pre-allocated buffers instead"
        hint "Audio functions must be deterministic in execution time"
    end on violation

end compiler rule
```

Четыре обязательных блока:

```
description     — что проверяет правило
severity        — error или warning
applies to      — к чему применяется
on violation    — что показать при нарушении
```

---

## Теги — способ пометить код для правил

Правила применяются к помеченному коду через теги:

```
-- Пометка функции тегом:
function process_audio_frame
    tagged with[audio_processing]
    tagged with[realtime]
    receives
        pointer[to AudioSample] named input as access
    returns
        nothing
    body
        -- компилятор применяет все правила для этих тегов
    end body
end function
```

Тег можно поставить на:

```
function        -- конкретная функция
module          -- все функции модуля
type            -- все операции типа
thread          -- код потока
```

---

## Виды пользовательских правил

### Правило запрета

Запрещает определённые операции в помеченном коде:

```
define compiler rule named NoBlockingInRealtime
    description "Realtime functions must never block execution"
    severity error
    applies to functions
        tagged with[realtime]
    end applies to

    forbids inside tagged functions
        blocking operations
        repeat forever without maximum iterations
        call via pointer[to function]
            note "Indirect calls have unpredictable timing"
        hardware delay
    end forbids

    on violation
        message "Blocking operation in realtime function"
        hint "Realtime functions must complete in bounded time"
        hint "Use non-blocking alternatives"
    end on violation

end compiler rule
```

---

### Правило требования

Требует определённых операций в помеченном коде:

```
define compiler rule named AllPublicFunctionsLog
    description "All public functions must log their entry"
    severity warning
    applies to functions
        visibility public
        in module tagged with[production]
    end applies to

    requires at function entry
        call log_function_entry
            note "First call in function body must be log_function_entry"
    end requires

    on violation
        message "Public function missing entry log"
        hint "Add as first line of function body:"
        hint "log_function_entry receives function_name and severity_level"
    end on violation

end compiler rule
```

---

### Правило значений

Проверяет допустимые значения переменных и параметров:

```
define compiler rule named BufferSizeMultipleOf512
    description "All buffer sizes must be multiples of 512 bytes"
    severity error
    applies to declarations
        named with suffix "_buffer_size"
        of type integer[unsigned, 32bit]
    end applies to

    requires value
        is multiple of 512
    end requires

    on violation
        message "Buffer size is not a multiple of 512"
        hint "Valid buffer sizes: 512, 1024, 1536, 2048..."
        hint "Round up to nearest multiple of 512"
    end on violation

end compiler rule
```

---

### Правило последовательности

Проверяет порядок вызовов функций:

```
define compiler rule named InitializeBeforeUse
    description "Device must be initialized before any operation"
    severity error
    applies to functions
        in module[HardwareDriver]
        visibility public
        except function[initialize_device]
    end applies to

    requires before first use
        call initialize_device has been called
            in same module
    end requires

    on violation
        message "Hardware operation called before initialization"
        hint "Call initialize_device before any other hardware function"
        hint "initialization_device must succeed before proceeding"
    end on violation

end compiler rule
```

---

## Реестр пользовательских правил

Все пользовательские правила проекта собираются в одном файле `.cstar-rules`:

```
compiler rules named ProjectRules
    version[1.0]
    description "Custom compiler rules for AudioSystem project"

    include rule[NoHeapInAudioFunctions]
        at path["./rules/audio_rules.cstar"]
    end include

    include rule[NoBlockingInRealtime]
        at path["./rules/realtime_rules.cstar"]
    end include

    include rule[AllPublicFunctionsLog]
        at path["./rules/logging_rules.cstar"]
    end include

    include rule[BufferSizeMultipleOf512]
        at path["./rules/buffer_rules.cstar"]
    end include

    include rule[InitializeBeforeUse]
        at path["./rules/hardware_rules.cstar"]
    end include

    execution order
        first built in rules
        then memory model rules
        then project rules in declaration order
    end execution order

end compiler rules
```

Порядок выполнения фиксирован:
```
1. Встроенные правила C*
2. Правила модели памяти
3. Пользовательские правила в порядке объявления
```

---

## Как пользовательские правила становятся узкими местами

Каждое пользовательское правило добавляет узкое место к уровню:

```
Уровень без пользовательских правил:

[Старт]━[владение]━[время жизни]━[null]━[release]━[Компиляция]


Уровень с пользовательскими правилами:

[Старт]━[владение]━[время жизни]━[null]━[release]
         ━[NoHeapInAudio]━[NoBlockingInRealtime]━[Компиляция]
```

Компилятор проверяет пользовательские узкие места на каждом пути через помеченный код.

---

## Сообщение при нарушении пользовательского правила

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL VIOLATION — Custom rule violation
File: AudioEngine.cstar
Line: 67
Rule: NoHeapInAudioFunctions
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Функция [apply_equalizer] помечена тегом
    [audio_processing] но выделяет память на куче.

Код с проблемой:
    function apply_equalizer
        tagged with[audio_processing]       -- line 61
        ...
        body
            declare byte named temp on heap is 0  -- line 67
                                       ^^^^
                              heap allocation forbidden

Почему это проблема:
    Правило [NoHeapInAudioFunctions]:
    "Audio processing functions must never allocate heap memory"

    Выделение памяти на куче недетерминировано по времени.
    Аудио функции обязаны выполняться за предсказуемое время.

Как исправить:
    Используйте стековое размещение:
    declare byte named temp on stack is 0

    Или используйте предварительно выделенный буфер:
    declare byte named temp as access: pre_allocated_buffer

Правило объявлено: ./rules/audio_rules.cstar line 1
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Конфликт пользовательских правил

Пользовательские правила могут конфликтовать друг с другом — компилятор обнаруживает это до прохода уровня:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
LEVEL BUILD FAILED — Custom rules conflict
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Что случилось:
    Два пользовательских правила предъявляют
    взаимоисключающие требования к одному коду.

Конфликт:

    Правило [AllPublicFunctionsLog]
        requires at function entry:
            call log_function_entry
        Объявлено: ./rules/logging_rules.cstar line 1

    Правило [NoBlockingInRealtime]
        forbids inside tagged functions:
            blocking operations
        Объявлено: ./rules/realtime_rules.cstar line 1

    Функция [process_realtime_audio]
        tagged with[public]
        tagged with[realtime]

    log_function_entry содержит блокирующую операцию
    записи в лог файл.

Почему это проблема:
    Правило 1 требует вызов log_function_entry.
    Правило 2 запрещает блокирующие операции.
    log_function_entry является блокирующей операцией.
    Оба правила применяются к одной функции.
    Уровень не может быть пройден.

Как исправить:
    Вариант 1: Создать неблокирующую версию log_function_entry
               для realtime функций

    Вариант 2: Исключить realtime функции из правила
               AllPublicFunctionsLog:
               except functions tagged with[realtime]

    Вариант 3: Разделить теги — использовать отдельный
               тег для публичных realtime функций

Правило: Раздел 6.4 — Конфликты пользовательских правил
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Что компилятор проверяет в пользовательских правилах

```
✓ Каждое правило имеет description, severity, applies to, on violation
✓ Теги объявлены до использования
✓ Правила зарегистрированы в .cstar-rules файле
✓ Пользовательские правила не конфликтуют между собой
✓ Пользовательские правила не конфликтуют со встроенными
✓ Порядок выполнения правил фиксирован
✓ Сообщение нарушения содержит ссылку на файл правила
```

---


# C* Language Reference
## Раздел 6 — Компилятор и уровень
### 6.5 Оптимизации

---

## Главное правило оптимизаций

> Компилятор C* может оптимизировать результат но никогда не меняет смысл. Если программист написал одну операцию — в машинном коде будет одна операция или эквивалентная ей. Никогда три скрытых операции которых программист не писал. Оптимизация убирает избыточность — не добавляет скрытую сложность.

---

## Граница допустимой оптимизации

```
Допустимо:
    Убрать то что не меняет результат
    Заменить медленное эквивалентным быстрым
    Вычислить заранее то что известно заранее

Недопустимо:
    Добавить операции которых программист не писал
    Изменить порядок hardware операций
    Убрать явные задержки и барьеры
    Скрыть сложность за простым синтаксисом
    Изменить поведение при переполнении
```

---

## Оптимизация 1 — Свёртка констант

Выражения из констант вычисляются на этапе компиляции:

```
-- Написано:
declare constant integer[unsigned, 32bit] named sample_rate is 44100
declare constant integer[unsigned, 32bit] named channels is 2
declare constant integer[unsigned, 32bit] named bytes_per_sample is 3

declare integer[unsigned, 32bit] named frame_size on stack is
    sample_rate multiply by channels multiply by bytes_per_sample

-- Компилятор вычисляет: 44100 × 2 × 3 = 264600
-- Генерируется:
declare integer[unsigned, 32bit] named frame_size on stack is 264600
```

В подробном режиме:

```
Stage 5 — Optimization [VERBOSE]
    Constant folding:
        AudioEngine.cstar line 8:
            44100 multiply by 2 multiply by 3 → 264600      ✓
```

---

## Оптимизация 2 — Удаление мёртвого кода

Код который никогда не выполняется удаляется:

```
-- Написано:
declare constant boolean named debug_mode is false

if debug_mode is equal to true
    log_verbose_output       -- этот код никогда не выполнится
    dump_memory_state
end if

process_audio_frame
```

Компилятор знает что `debug_mode` — константа равная `false`. Блок `if` никогда не выполнится. Он удаляется полностью.

```
-- Генерируется эквивалентно:
process_audio_frame
```

Ограничение: удаляется только код который **доказуемо** недостижим. Если компилятор не уверен — код остаётся.

---

## Оптимизация 3 — Инлайнинг функций

Тело простой функции вставляется на место вызова:

```
-- Написано:
function clamp_sample
    receives
        integer[signed, 32bit] named value
        integer[signed, 32bit] named minimum
        integer[signed, 32bit] named maximum
    returns
        integer[signed, 32bit] named clamped
    body
        if value is less than minimum
            clamped is minimum
        otherwise if value is greater than maximum
            clamped is maximum
        otherwise
            clamped is value
        end otherwise
        end otherwise if
        end if
    end body
end function

-- Вызов:
result is clamp_sample receives raw_value and minus 32767 and 32767
```

Компилятор вставляет тело функции напрямую — убирает накладные расходы вызова. Результат идентичен. Функция по-прежнему существует в коде — только вызов становится прямым кодом.

Инлайнинг применяется когда:
```
Функция маленькая — тело короче накладных расходов вызова
Функция вызывается в горячем пути — часто используемый код
Функция не рекурсивная
```

---

## Оптимизация 4 — Размещение в регистрах

Часто используемые переменные размещаются в регистрах процессора вместо стека:

```
-- Написано:
declare integer[unsigned, 32bit] named current_index on stack is 0

repeat while current_index is less than buffer_size
    process_byte receives buffer at index current_index
    current_index is current_index plus 1
end repeat
```

`current_index` используется на каждой итерации. Компилятор размещает его в регистре процессора — обращение к регистру быстрее обращения к стеку.

Программист не видит разницы в поведении — только в скорости.

---

## Оптимизация 5 — Устранение хвостовых вызовов

Рекурсивный вызов в конце функции преобразуется в цикл:

```
-- Написано:
function sum_recursive
    receives
        integer[unsigned, 32bit] named remaining_count
        integer[unsigned, 64bit] named accumulated_sum
    returns
        integer[unsigned, 64bit] named total_sum
    stops when remaining_count is equal to 0
    body
        if remaining_count is equal to 0
            total_sum is accumulated_sum
        otherwise
            declare integer[unsigned, 64bit] named new_sum on stack is 0
            new_sum is accumulated_sum plus remaining_count

            call sum_recursive
                with remaining_count as copy: remaining_count minus 1
                with accumulated_sum as copy: new_sum
                on success
                    total_sum is result
            end call
        end otherwise
        end if
    end body
end function
```

Рекурсивный вызов в конце функции — хвостовой вызов. Компилятор превращает его в цикл. Стек не растёт. Миллион итераций не переполнит стек.

---

## Что никогда не оптимизируется

### Hardware операции

```
-- Написано:
hardware write register control_register
    value 0x01
    note "Enable device"

hardware memory barrier
    note "Ensure write reaches device"

hardware write register data_register
    value 0xFF
    note "Send data"

-- Генерируется именно это — без изменений:
MOV [control_register], 0x01
MFENCE
MOV [data_register], 0xFF
```

Порядок hardware операций священен. Компилятор не переставляет их никогда.

### Volatile регистры

```
-- Написано три раза подряд — читается три раза:
hardware read register volatile_status_register
    into reading_one

hardware read register volatile_status_register
    into reading_two

hardware read register volatile_status_register
    into reading_three
```

Компилятор не кэширует значение volatile регистра. Каждое чтение — обращение к железу.

### Явные задержки

```
hardware delay 10 microseconds
    note "Device needs time to stabilize"
```

Задержка выполняется точно. Не приблизительно. Не убирается как "ненужная пауза".

### Поведение при переполнении

```
controlled convert large_value to integer[signed, 8bit]
    into small_value
    on overflow
        reject with error[ValueTooLarge]
```

Проверка переполнения остаётся всегда. Компилятор не убирает её даже если считает что переполнение маловероятно.

### Явные шаги пользователя

```
-- Написано три отдельных шага:
declare integer[signed, 32bit] named step_one on stack is 0
declare integer[signed, 32bit] named step_two on stack is 0
declare integer[signed, 32bit] named result on stack is 0

step_one is a multiply by b
step_two is c divide by d
result is step_one plus step_two
```

Компилятор не сворачивает это в одно выражение. Программист написал три шага — будет три шага. RISC принцип сохранён.

---

## Управление оптимизациями

Программист может отключить конкретные оптимизации:

```
compiler optimizations
    constant folding: enabled
    dead code elimination: enabled
    inline expansion: enabled
    register allocation: enabled
    tail call elimination: enabled
end compiler optimizations
```

Или отключить все оптимизации для отладки:

```
compiler optimizations none
    note "Debug build — no optimizations applied"
```

Директива пишется в первом файле компиляции рядом с режимом вывода:

```
compiler mode verbose
compiler optimizations none
```

---

## Как оптимизации отображаются пользователю

В тихом режиме — не отображаются совсем.

В обычном режиме — только количество:

```
Stage 5 — Optimization
    5 optimizations applied.                      ✓
```

В подробном режиме — каждая оптимизация с объяснением:

```
Stage 5 — Optimization [VERBOSE]

    Constant folding [3]:
        line 8:  44100 × 2 × 3 → 264600          ✓
        line 15: 512 × 8 → 4096                   ✓
        line 23: max_size + 0 → max_size           ✓

    Dead code elimination [1]:
        line 145: debug_mode branch removed
                  reason: debug_mode is constant false  ✓

    Inline expansion [1]:
        line 201: clamp_sample inlined
                  original size: 8 instructions
                  call overhead saved: 4 instructions   ✓

    NOT optimized [hardware]:
        line 89:  hardware write — order preserved      ✓
        line 91:  hardware barrier — always executed    ✓
        line 93:  hardware write — order preserved      ✓

    Total: 5 optimizations applied.
    Hardware operations: 3 preserved unchanged.
```

---

## Что компилятор гарантирует в оптимизациях

```
✓ Оптимизации никогда не меняют результат программы
✓ Hardware операции никогда не переставляются
✓ Volatile регистры всегда читаются из железа
✓ Явные задержки всегда выполняются точно
✓ Проверки переполнения никогда не убираются
✓ Явные шаги программиста сохраняются как шаги
✓ Подробный режим показывает каждую оптимизацию
✓ Подробный режим показывает что НЕ оптимизировано
✓ Программист может отключить любую оптимизацию
```

---

## Раздел 6 завершён

```
6.1 Стадии компиляции                  ✓
6.2 Система уровня                     ✓
6.3 Сообщения компилятора              ✓
6.4 Пользовательские правила           ✓
6.5 Оптимизации                        ✓
```

Компилятор C* полностью описан. Прозрачный — программист видит каждую стадию. Строгий — уровень не прощает нарушений. Точный — каждое сообщение объясняет проблему и предлагает решение.

---
# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.1 Организация стандартной библиотеки

---

## Главное правило стандартной библиотеки

> Стандартная библиотека C* следует тем же правилам что и пользовательский код. Никаких исключений для удобства. Никакой скрытой магии. Код библиотеки читается так же как код программиста — потому что написан по тем же правилам.

---

## Философия — из коробки всё необходимое

```
Входит в коробку — необходимость:
    StdMath        вся базовая математика
    StdMemory      управление памятью
    StdText        полная работа с текстом
    StdIO          ввод-вывод на любой платформе
    StdTime        время и таймеры
    StdCollections коллекции данных

Докупается отдельно — украшения и доп функции:
    Сетевые библиотеки
    Криптография
    Графика
    Специализированные форматы данных
    Пользовательские коллекции
```

---

## Структура стандартной библиотеки

Каждый модуль стандартной библиотеки — это обычный модуль C*. Никакого специального статуса. Никаких привилегий. Они написаны по тем же правилам что и любой другой модуль.

```
StdLibrary/
    StdMath/
        StdMath.cstar
        StdMath.cstar-rules
    StdMemory/
        StdMemory.cstar
        StdMemory.cstar-rules
    StdText/
        StdText.cstar
        StdText.cstar-rules
    StdIO/
        StdIO.cstar
        StdIO.cstar-rules
        platforms/
            StdIO.linux.cstar
            StdIO.windows.cstar
            StdIO.bare_metal.cstar
    StdTime/
        StdTime.cstar
        StdTime.cstar-rules
    StdCollections/
        StdCollections.cstar
        StdList.cstar
        StdQueue.cstar
        StdStack.cstar
        StdDictionary.cstar
        StdSet.cstar
        StdRingBuffer.cstar
        StdCollections.cstar-rules
```

---

## Подключение стандартной библиотеки

По имени — компилятор знает где искать:

```
program AudioSystem

    use module[StdMath]
    use module[StdMemory]
    use module[StdText]
    use module[StdIO]
    use module[StdTime]
    use module[StdCollections]

    body
        -- код
    end body

end program
```

Или подключить только нужные коллекции:

```
use module[StdCollections.StdList]
use module[StdCollections.StdDictionary]
```

---

## Версионирование стандартной библиотеки

Стандартная библиотека версионируется вместе с компилятором:

```
C* Compiler v1.0  →  StdLibrary v1.0
C* Compiler v1.1  →  StdLibrary v1.1
C* Compiler v2.0  →  StdLibrary v2.0
```

Версия библиотеки всегда совпадает с версией компилятора. Несовместимость версий невозможна.

---

## Независимость от C

Вся стандартная библиотека написана на C* без единой зависимости от C. Никаких foreign gateway внутри стандартных модулей. Это означает:

```
✓ Библиотека работает на любой платформе где есть компилятор C*
✓ Библиотека работает без операционной системы
✓ Библиотека не тянет за собой libc или любую другую C библиотеку
✓ Поведение библиотеки одинаково на всех платформах
```

---

## Платформенные реализации

StdIO и StdTime имеют платформенные реализации. Остальные модули платформонезависимы полностью.

Выбор платформы — при компиляции:

```
compiler target linux x86-64
compiler target windows x86-64
compiler target bare-metal arm-cortex-m4
```

Компилятор подключает правильную реализацию автоматически. Код программы не меняется.

Для голого железа без поддерживаемой платформы — программист реализует интерфейс сам:

```
implement platform interface[StdIO]
    for target[custom-hardware]

    function write_bytes
        receives
            array[byte, any size] named data as access
        returns
            integer[unsigned, 32bit] named bytes_written
        on error[WriteFailure]
            reject with error[WriteFailure]
        body
            -- реализация через hardware операции из Раздела 5
        end body
    end function

    function read_bytes
        receives
            integer[unsigned, 32bit] named max_count
        returns
            array[byte, any size] named received_data as owner
        on error[ReadFailure]
            reject with error[ReadFailure]
        body
            -- реализация через hardware операции
        end body
    end function

end implement
```

---

## Общие ошибки стандартной библиотеки

Все модули используют единый набор ошибок:

```
-- Ошибки StdMemory:
error[OutOfMemory]
error[InvalidAllocation]
error[DoubleFree]

-- Ошибки StdIO:
error[ReadFailure]
error[WriteFailure]
error[EndOfInput]
error[DeviceNotReady]

-- Ошибки StdCollections:
error[CollectionFull]
error[CollectionEmpty]
error[KeyNotFound]
error[DuplicateKey]
error[IndexOutOfBounds]

-- Ошибки StdMath:
error[DivisionByZero]
error[ArithmeticOverflow]
error[InvalidInput]
error[PrecisionLoss]

-- Ошибки StdText:
error[InvalidEncoding]
error[TextTooLarge]
error[PatternNotFound]

-- Ошибки StdTime:
error[TimerNotAvailable]
error[InvalidDuration]
error[TimeoutExpired]
```

---

## Что гарантирует стандартная библиотека

```
✓ Все модули следуют правилам языка C* без исключений
✓ Все функции имеют полные контракты с блоками on error
✓ Все модули независимы от C
✓ Поведение одинаково на всех платформах
✓ Версия библиотеки всегда совпадает с версией компилятора
✓ Платформенные различия скрыты за единым интерфейсом
✓ Код библиотеки открыт и читается как обычный C* код
```

---

*Готово. Переходим к 7.2 — StdMath?*

# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.2 StdMath — Математика

---

## Главное правило StdMath

> StdMath предоставляет математические операции которые выходят за рамки встроенных арифметических операций языка. Каждая функция явно объявляет что может пойти не так. Никакой тихой потери точности. Никаких молчаливых переполнений.

---

## Подключение

```
use module[StdMath]
```

---

## Целочисленная математика

### Абсолютное значение

```
call StdMath.absolute value
    with value as copy: minus 42
    on success
        result is absolute_result
        -- result равен 42
end call
```

### Минимум и максимум

```
call StdMath.minimum of
    with first as copy: 17
    with second as copy: 42
    on success
        result is minimum_result
        -- result равен 17
end call

call StdMath.maximum of
    with first as copy: 17
    with second as copy: 42
    on success
        result is maximum_result
        -- result равен 42
end call
```

### Возведение в степень

```
declare integer[signed, 64bit] named power_result on stack is 0

call StdMath.integer power
    with base as copy: 2
    with exponent as copy: 10
    on error[ArithmeticOverflow]
        reject with error[CalculationFailed]
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        power_result is result
        -- result равен 1024
end call
```

### Целочисленный квадратный корень

```
declare integer[unsigned, 32bit] named sqrt_result on stack is 0

call StdMath.integer square root
    with value as copy: 144
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        sqrt_result is result
        -- result равен 12
end call
```

### Наибольший общий делитель

```
declare integer[unsigned, 32bit] named gcd_result on stack is 0

call StdMath.greatest common divisor
    with first as copy: 48
    with second as copy: 18
    on success
        gcd_result is result
        -- result равен 6
end call
```

### Наименьшее общее кратное

```
declare integer[unsigned, 32bit] named lcm_result on stack is 0

call StdMath.least common multiple
    with first as copy: 12
    with second as copy: 18
    on error[ArithmeticOverflow]
        reject with error[CalculationFailed]
    on success
        lcm_result is result
        -- result равен 36
end call
```

---

## Математика с плавающей точкой

### Константы

```
declare constant float[64bit] named pi
    is StdMath.PI
    note "3.14159265358979323846..."

declare constant float[64bit] named euler
    is StdMath.E
    note "2.71828182845904523536..."

declare constant float[64bit] named square_root_of_two
    is StdMath.SQRT2
    note "1.41421356237309504880..."

declare constant float[64bit] named positive_infinity
    is StdMath.INFINITY

declare constant float[64bit] named not_a_number
    is StdMath.NAN
```

### Квадратный корень

```
declare float[64bit] named sqrt_result on stack is 0.0

call StdMath.square root
    with value as copy: 2.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        sqrt_result is result
        -- result равен 1.41421356...
end call
```

### Степень

```
declare float[64bit] named power_result on stack is 0.0

call StdMath.power
    with base as copy: 2.718281828
    with exponent as copy: 3.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on error[ArithmeticOverflow]
        reject with error[CalculationFailed]
    on success
        power_result is result
end call
```

### Логарифмы

```
declare float[64bit] named log_result on stack is 0.0

-- Натуральный логарифм
call StdMath.natural logarithm
    with value as copy: 2.718281828
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        log_result is result
        -- result равен примерно 1.0
end call

-- Логарифм по основанию 10
call StdMath.logarithm base 10
    with value as copy: 1000.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        log_result is result
        -- result равен 3.0
end call

-- Логарифм по произвольному основанию
call StdMath.logarithm base
    with value as copy: 8.0
    with base as copy: 2.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        log_result is result
        -- result равен 3.0
end call
```

---

## Тригонометрия

Углы в StdMath всегда в радианах. Функции преобразования предоставлены явно.

### Преобразование углов

```
declare float[64bit] named angle_radians on stack is 0.0
declare float[64bit] named angle_degrees on stack is 90.0

call StdMath.degrees to radians
    with degrees as copy: angle_degrees
    on success
        angle_radians is result
        -- result равен 1.5707963...
end call

call StdMath.radians to degrees
    with radians as copy: angle_radians
    on success
        angle_degrees is result
        -- result равен 90.0
end call
```

### Основные функции

```
declare float[64bit] named trig_result on stack is 0.0

call StdMath.sine
    with angle radians as copy: angle_radians
    on success
        trig_result is result
end call

call StdMath.cosine
    with angle radians as copy: angle_radians
    on success
        trig_result is result
end call

call StdMath.tangent
    with angle radians as copy: angle_radians
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        trig_result is result
end call
```

### Обратные функции

```
call StdMath.arc sine
    with value as copy: 1.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        angle_radians is result
        -- result равен 1.5707963...
end call

call StdMath.arc cosine
    with value as copy: 0.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        angle_radians is result
end call

call StdMath.arc tangent
    with value as copy: 1.0
    on success
        angle_radians is result
        -- result равен 0.7853981...
end call

-- Четырёхквадрантный арктангенс
call StdMath.arc tangent two
    with y as copy: 1.0
    with x as copy: 1.0
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        angle_radians is result
end call
```

---

## Округление

```
declare float[64bit] named value on stack is 3.7
declare float[64bit] named rounded on stack is 0.0

-- Вниз — к меньшему целому
call StdMath.floor
    with value as copy: value
    on success
        rounded is result
        -- result равен 3.0
end call

-- Вверх — к большему целому
call StdMath.ceiling
    with value as copy: value
    on success
        rounded is result
        -- result равен 4.0
end call

-- К ближайшему целому
call StdMath.round
    with value as copy: value
    on success
        rounded is result
        -- result равен 4.0
end call

-- К нулю — отбросить дробную часть
call StdMath.truncate
    with value as copy: value
    on success
        rounded is result
        -- result равен 3.0
end call
```

---

## Проверка специальных значений

```
declare float[64bit] named suspicious_value on stack is 0.0
declare boolean named check_result on stack is false

call StdMath.is not a number
    with value as copy: suspicious_value
    on success
        check_result is result
end call

call StdMath.is infinite
    with value as copy: suspicious_value
    on success
        check_result is result
end call

call StdMath.is finite
    with value as copy: suspicious_value
    on success
        check_result is result
end call
```

---

## Случайные числа

```
-- Инициализация генератора
call StdMath.seed random
    with seed as copy: 42
    on success
        -- генератор инициализирован
end call

-- Случайное целое число в диапазоне
declare integer[signed, 32bit] named random_int on stack is 0

call StdMath.random integer
    with minimum as copy: 0
    with maximum as copy: 100
    on error[InvalidInput]
        reject with error[CalculationFailed]
    on success
        random_int is result
        -- result от 0 до 100 включительно
end call

-- Случайное число с плавающей точкой от 0.0 до 1.0
declare float[64bit] named random_float on stack is 0.0

call StdMath.random float
    on success
        random_float is result
end call
```

---

## Что гарантирует StdMath

```
✓ Все функции явно объявляют возможные ошибки
✓ Углы всегда в радианах — преобразование явное
✓ Переполнение никогда не молчит
✓ Потеря точности объявлена через on error[PrecisionLoss]
✓ Специальные значения NAN и INFINITY проверяемы явно
✓ Случайные числа требуют явной инициализации
✓ Все константы именованы и задокументированы
✓ Независимость от libm или любой C библиотеки
```

---

*Готово. Переходим к 7.3 — StdMemory?*
# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.3 StdMemory — Управление памятью

---

## Главное правило StdMemory

> StdMemory предоставляет инструменты для работы с памятью которые выходят за рамки встроенных операций языка. Каждая операция явна. Каждая ошибка обработана. StdMemory не делает ничего за спиной программиста.

---

## Подключение

```
use module[StdMemory]
```

---

## Выделение и освобождение памяти

### Явное выделение блока

```
declare pointer[to byte] named raw_block on stack is null
declare integer[unsigned, 32bit] named block_size on stack is 4096

call StdMemory.allocate block
    with size as copy: block_size
    with alignment as copy: 8
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on error[InvalidAllocation]
        reject with error[InvalidAllocation]
    on success
        raw_block is result as owner
end call
```

Параметр `alignment` обязателен — в духе C* выравнивание всегда явное.

### Освобождение блока

```
call StdMemory.release block
    with block as owner: raw_block
    on error[InvalidAllocation]
        reject with error[InvalidAllocation]
    on success
        -- raw_block освобождён
        -- raw_block больше не существует
end call
```

### Изменение размера блока

```
call StdMemory.resize block
    with block as owner: raw_block
    with new size as copy: 8192
    with alignment as copy: 8
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on error[InvalidAllocation]
        reject with error[InvalidAllocation]
    on success
        raw_block is result as owner
        -- raw_block теперь указывает на блок размером 8192
end call
```

---

## Копирование памяти

### Копирование блоков

```
declare pointer[to byte] named source_block on stack is null
declare pointer[to byte] named destination_block on stack is null
declare integer[unsigned, 32bit] named copy_size on stack is 1024

call StdMemory.copy block
    with source as access: source_block
    with destination as access: destination_block
    with size as copy: copy_size
    on error[InvalidAllocation]
        reject with error[CopyFailed]
    on error[OverlapDetected]
        reject with error[CopyFailed]
    on success
        -- destination содержит копию source
end call
```

Блок `on error[OverlapDetected]` обязателен — StdMemory обнаруживает перекрывающиеся блоки и сообщает об этом. В C функция `memcpy` при перекрытии блоков приводит к неопределённому поведению. В C* это ошибка.

### Копирование перекрывающихся блоков

Когда перекрытие допустимо — явная функция:

```
call StdMemory.move block
    with source as access: source_block
    with destination as access: destination_block
    with size as copy: copy_size
    on error[InvalidAllocation]
        reject with error[MoveFailed]
    on success
        -- корректное перемещение даже при перекрытии
end call
```

`move block` корректно обрабатывает перекрывающиеся блоки. `copy block` запрещает их. Два разных имени — два разных смысла.

---

## Заполнение памяти

```
declare pointer[to byte] named buffer on stack is null
declare integer[unsigned, 32bit] named fill_size on stack is 512

-- Заполнить нулями
call StdMemory.fill block with zeros
    with block as access: buffer
    with size as copy: fill_size
    on error[InvalidAllocation]
        reject with error[FillFailed]
    on success
        -- все байты равны 0
end call

-- Заполнить конкретным байтом
call StdMemory.fill block with byte
    with block as access: buffer
    with size as copy: fill_size
    with value as copy: 0xFF
    on error[InvalidAllocation]
        reject with error[FillFailed]
    on success
        -- все байты равны 0xFF
end call
```

---

## Сравнение блоков памяти

```
declare pointer[to byte] named block_one on stack is null
declare pointer[to byte] named block_two on stack is null
declare integer[unsigned, 32bit] named compare_size on stack is 256
declare boolean named blocks_are_equal on stack is false

call StdMemory.compare blocks
    with first as access: block_one
    with second as access: block_two
    with size as copy: compare_size
    on error[InvalidAllocation]
        reject with error[CompareFailed]
    on success
        blocks_are_equal is result
end call
```

---

## Статистика памяти

```
declare integer[unsigned, 64bit] named total_heap on stack is 0
declare integer[unsigned, 64bit] named used_heap on stack is 0
declare integer[unsigned, 64bit] named free_heap on stack is 0

call StdMemory.query heap statistics
    on error[StatisticsUnavailable]
        log_message receives "Memory statistics unavailable" and 2
    on success
        total_heap is result.total_bytes
        used_heap is result.used_bytes
        free_heap is result.free_bytes
end call
```

---

## Пулы памяти

Пул — заранее выделенный блок из которого выдаются меньшие куски. Быстрее чем выделение через систему. Предсказуемо по времени.

### Создание пула

```
declare StdMemory.Pool named audio_pool
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdMemory.create pool
    with pool as access: audio_pool
    with total size as copy: 65536
    with block size as copy: 512
    with alignment as copy: 8
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on error[InvalidAllocation]
        reject with error[InvalidAllocation]
    on success
        -- пул готов к использованию
        -- 128 блоков по 512 байт
end call
```

### Выделение из пула

```
declare pointer[to byte] named pool_block on stack is null

call StdMemory.allocate from pool
    with pool as access: audio_pool
    on error[CollectionFull]
        reject with error[OutOfMemory]
    on success
        pool_block is result as owner
end call
```

### Освобождение в пул

```
call StdMemory.release to pool
    with pool as access: audio_pool
    with block as owner: pool_block
    on error[InvalidAllocation]
        reject with error[ReleaseFailed]
    on success
        -- блок возвращён в пул
        -- pool_block больше не существует
end call
```

### Уничтожение пула

```
call StdMemory.destroy pool
    with pool as owner: audio_pool
    on error[ReleaseFailed]
        reject with error[ReleaseFailed]
    on success
        -- весь пул освобождён
        -- audio_pool больше не существует
end call
```

---

## Стековый аллокатор

Выделяет память последовательно. Освобождение только всего стека сразу. Максимально быстрый — указатель просто двигается вперёд.

```
declare StdMemory.StackAllocator named frame_allocator
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdMemory.create stack allocator
    with allocator as access: frame_allocator
    with total size as copy: 16384
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- аллокатор готов
end call

-- Выделить из стекового аллокатора
declare pointer[to byte] named frame_data on stack is null

call StdMemory.allocate from stack
    with allocator as access: frame_allocator
    with size as copy: 256
    with alignment as copy: 4
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        frame_data is result as access
        -- access — стековый аллокатор остаётся владельцем
end call

-- Сбросить весь стековый аллокатор
call StdMemory.reset stack allocator
    with allocator as access: frame_allocator
    on success
        -- вся выделенная память возвращена
        -- все указатели из этого аллокатора недействительны
end call

-- Уничтожить аллокатор
call StdMemory.destroy stack allocator
    with allocator as owner: frame_allocator
    on success
        -- аллокатор освобождён
end call
```

---

## Защита памяти

### Защита блока от записи

```
call StdMemory.protect block read only
    with block as access: code_block
    with size as copy: code_size
    on error[ProtectionFailed]
        reject with error[ProtectionFailed]
    on success
        -- блок защищён от записи
end call
```

### Снятие защиты

```
call StdMemory.protect block read write
    with block as access: code_block
    with size as copy: code_size
    on error[ProtectionFailed]
        reject with error[ProtectionFailed]
    on success
        -- защита снята
end call
```

---

## Что гарантирует StdMemory

```
✓ Выравнивание всегда явное — никогда не угадывается
✓ copy block обнаруживает перекрытие — move block обрабатывает
✓ Пул памяти предсказуем по времени выполнения
✓ Стековый аллокатор — максимально быстрый
✓ Статистика памяти доступна всегда
✓ Защита блоков памяти явная и обратимая
✓ Независимость от malloc или любой C функции
```

---

*Готово. Переходим к 7.4 — StdText?*
# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.4 StdText — Работа с текстом

---

## Главное правило StdText

> StdText расширяет встроенные возможности типа text из Раздела 4.3. Все операции явные. Кодировка всегда UTF-8. Длина всегда известна. Переполнение невозможно структурно.

---

## Подключение

```
use module[StdText]
```

---

## Создание и копирование

### Создание пустого текста

```
declare text named empty_message
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]
```

### Копирование текста

```
declare text named original
    in segment[Text]
    on heap
    is "AudioEngine"
    on allocation failure
        reject with error[OutOfMemory]

declare text named copy_of_original
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdText.copy
    with source as access: original
    into result as owner: copy_of_original
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- copy_of_original содержит "AudioEngine"
end call
```

---

## Анализ текста

### Длина

```
declare text named message
    in segment[Text]
    on heap
    is "Привет мир"
    on allocation failure
        reject with error[OutOfMemory]

declare integer[unsigned, 32bit] named char_count on stack is 0
declare integer[unsigned, 32bit] named byte_count on stack is 0

call StdText.character count
    with source as access: message
    on success
        char_count is result
        -- result равен 10 — символов Unicode
end call

call StdText.byte count
    with source as access: message
    on success
        byte_count is result
        -- result равен 19 — байт UTF-8
        -- кириллица занимает 2 байта на символ
end call
```

### Проверка содержимого

```
declare boolean named check_result on stack is false

-- Пустой ли текст
call StdText.is empty
    with source as access: message
    on success
        check_result is result
end call

-- Начинается ли с подстроки
call StdText.starts with
    with source as access: message
    with prefix as access: search_prefix
    on success
        check_result is result
end call

-- Заканчивается ли подстрокой
call StdText.ends with
    with source as access: message
    with suffix as access: search_suffix
    on success
        check_result is result
end call

-- Содержит ли подстроку
call StdText.contains
    with source as access: message
    with search for as access: needle
    on success
        check_result is result
end call
```

---

## Поиск

### Поиск первого вхождения

```
declare text named haystack
    in segment[Text]
    on heap
    is "AudioEngine initialized successfully"
    on allocation failure
        reject with error[OutOfMemory]

declare text named needle
    in segment[Text]
    on heap
    is "initialized"
    on allocation failure
        reject with error[OutOfMemory]

declare integer[unsigned, 32bit] named found_position on stack is 0
declare boolean named was_found on stack is false

call StdText.find first
    with source as access: haystack
    with search for as access: needle
    on not found
        was_found is false
    on found
        was_found is true
        found_position is result.character_position
end call
```

### Поиск последнего вхождения

```
call StdText.find last
    with source as access: haystack
    with search for as access: needle
    on not found
        was_found is false
    on found
        was_found is true
        found_position is result.character_position
end call
```

### Поиск всех вхождений

```
declare StdCollections.List[integer[unsigned, 32bit]] named all_positions
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdText.find all
    with source as access: haystack
    with search for as access: needle
    into positions as owner: all_positions
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on not found
        -- all_positions пуст
    on found
        -- all_positions содержит все позиции
end call
```

---

## Извлечение

### Получение символа по индексу

```
declare integer[unsigned, 32bit] named char_code on stack is 0

call StdText.character at
    with source as access: message
    with position as copy: 0
    on error[IndexOutOfBounds]
        reject with error[InvalidTextOperation]
    on success
        char_code is result
        -- result — код символа Unicode
end call
```

### Извлечение подстроки

```
declare text named substring
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdText.substring
    with source as access: haystack
    with from character as copy: 13
    with count characters as copy: 11
    into result as owner: substring
    on error[IndexOutOfBounds]
        reject with error[InvalidTextOperation]
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- substring содержит "initialized"
end call
```

### Первые N символов

```
call StdText.take first
    with source as access: message
    with count as copy: 5
    into result as owner: first_part
    on error[IndexOutOfBounds]
        reject with error[InvalidTextOperation]
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- first_part содержит первые 5 символов
end call
```

### Последние N символов

```
call StdText.take last
    with source as access: message
    with count as copy: 5
    into result as owner: last_part
    on error[IndexOutOfBounds]
        reject with error[InvalidTextOperation]
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- last_part содержит последние 5 символов
end call
```

---

## Изменение текста

### Соединение

```
declare text named first_part
    in segment[Text]
    on heap
    is "Audio"
    on allocation failure
        reject with error[OutOfMemory]

declare text named second_part
    in segment[Text]
    on heap
    is "Engine"
    on allocation failure
        reject with error[OutOfMemory]

declare text named combined
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdText.join
    with first as access: first_part
    with second as access: second_part
    into result as owner: combined
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- combined содержит "AudioEngine"
end call
```

### Соединение списка текстов

```
declare StdCollections.List[text] named parts
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

declare text named separator
    in segment[Text]
    on heap
    is ", "
    on allocation failure
        reject with error[OutOfMemory]

declare text named joined_result
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdText.join list
    with parts as access: parts
    with separator as access: separator
    into result as owner: joined_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- joined_result содержит все части через разделитель
end call
```

### Замена

```
declare text named source_text
    in segment[Text]
    on heap
    is "Hello World Hello"
    on allocation failure
        reject with error[OutOfMemory]

declare text named search_text
    in segment[Text]
    on heap
    is "Hello"
    on allocation failure
        reject with error[OutOfMemory]

declare text named replace_text
    in segment[Text]
    on heap
    is "Goodbye"
    on allocation failure
        reject with error[OutOfMemory]

declare text named replaced_result
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

-- Заменить все вхождения
call StdText.replace all
    with source as access: source_text
    with search for as access: search_text
    with replace with as access: replace_text
    into result as owner: replaced_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- replaced_result содержит "Goodbye World Goodbye"
end call

-- Заменить только первое вхождение
call StdText.replace first
    with source as access: source_text
    with search for as access: search_text
    with replace with as access: replace_text
    into result as owner: replaced_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on not found
        -- поиск не нашёл вхождений
    on success
        -- replaced_result содержит "Goodbye World Hello"
end call
```

### Обрезка пробелов

```
declare text named padded_text
    in segment[Text]
    on heap
    is "   AudioEngine   "
    on allocation failure
        reject with error[OutOfMemory]

declare text named trimmed_result
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

-- Убрать пробелы с обеих сторон
call StdText.trim
    with source as access: padded_text
    into result as owner: trimmed_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- trimmed_result содержит "AudioEngine"
end call

-- Убрать пробелы только слева
call StdText.trim left
    with source as access: padded_text
    into result as owner: trimmed_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- trimmed_result содержит "AudioEngine   "
end call

-- Убрать пробелы только справа
call StdText.trim right
    with source as access: padded_text
    into result as owner: trimmed_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- trimmed_result содержит "   AudioEngine"
end call
```

### Изменение регистра

```
declare text named mixed_case
    in segment[Text]
    on heap
    is "AudioEngine"
    on allocation failure
        reject with error[OutOfMemory]

declare text named case_result
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdText.to uppercase
    with source as access: mixed_case
    into result as owner: case_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- case_result содержит "AUDIOENGINE"
end call

call StdText.to lowercase
    with source as access: mixed_case
    into result as owner: case_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- case_result содержит "audioengine"
end call
```

---

## Разбиение и сборка

### Разбиение по разделителю

```
declare text named csv_line
    in segment[Text]
    on heap
    is "44100,2,16,stereo"
    on allocation failure
        reject with error[OutOfMemory]

declare text named comma_separator
    in segment[Text]
    on heap
    is ","
    on allocation failure
        reject with error[OutOfMemory]

declare StdCollections.List[text] named parts
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdText.split
    with source as access: csv_line
    with separator as access: comma_separator
    into result as owner: parts
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- parts содержит ["44100", "2", "16", "stereo"]
end call
```

---

## Форматирование

```
declare text named template_text
    in segment[Text]
    on heap
    is "Device {name} initialized at {rate} Hz"
    on allocation failure
        reject with error[OutOfMemory]

declare text named formatted_result
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdText.format
    with template as access: template_text
    with placeholder "name" as access: device_name
    with placeholder "rate" as copy: sample_rate
    into result as owner: formatted_result
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on error[InvalidTextFormat]
        reject with error[InvalidTextOperation]
    on success
        -- formatted_result содержит
        -- "Device AudioCard initialized at 44100 Hz"
end call
```

---

## Что гарантирует StdText

```
✓ Кодировка всегда UTF-8
✓ Длина в символах и байтах различается явно
✓ Все индексы в символах Unicode не в байтах
✓ Переполнение буфера невозможно структурно
✓ Каждая операция имеет обработку ошибок
✓ Форматирование через именованные заполнители
✓ Независимость от string.h или любой C библиотеки
```

---

*Готово. Переходим к 7.5 — StdIO?*

# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.5 StdIO — Ввод и вывод

---

## Главное правило StdIO

> StdIO предоставляет единый интерфейс ввода-вывода для всех платформ. Один и тот же код работает на Linux, Windows и голом железе. Платформенные различия скрыты за интерфейсом. Программист пишет один раз — компилятор выбирает правильную реализацию.

---

## Подключение

```
use module[StdIO]
```

---

## Платформенный интерфейс

StdIO имеет три реализации:

```
compiler target linux x86-64
    → StdIO использует системные вызовы Linux

compiler target windows x86-64
    → StdIO использует Win32 API

compiler target bare-metal
    → StdIO использует реализацию программиста
```

Код программы не меняется при смене платформы.

---

## Консольный вывод

### Вывод текста

```
declare text named message
    in segment[Text]
    on heap
    is "AudioEngine initialized"
    on allocation failure
        reject with error[OutOfMemory]

call StdIO.write line
    with message as access: message
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- строка выведена с переводом строки
end call

call StdIO.write
    with message as access: message
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- строка выведена без перевода строки
end call
```

### Вывод чисел

```
declare integer[signed, 32bit] named sample_rate on stack is 44100
declare float[64bit] named cpu_usage on stack is 0.73

call StdIO.write integer
    with value as copy: sample_rate
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- выведено "44100"
end call

call StdIO.write float
    with value as copy: cpu_usage
    with decimal places as copy: 2
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- выведено "0.73"
end call
```

### Форматированный вывод

```
call StdIO.write formatted
    with template as access: "Device {name} at {rate} Hz"
    with placeholder "name" as access: device_name
    with placeholder "rate" as copy: sample_rate
    on error[WriteFailure]
        reject with error[IOFailure]
    on error[InvalidTextFormat]
        reject with error[IOFailure]
    on success
        -- выведено "Device AudioCard at 44100 Hz"
end call
```

---

## Консольный ввод

### Чтение строки

```
declare text named user_input
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdIO.read line
    into result as owner: user_input
    on error[ReadFailure]
        reject with error[IOFailure]
    on error[EndOfInput]
        -- конец входного потока
        stop
    on success
        -- user_input содержит введённую строку
        -- перевод строки не включён
end call
```

### Чтение числа

```
declare integer[signed, 32bit] named input_number on stack is 0

call StdIO.read integer
    into result: input_number
    on error[ReadFailure]
        reject with error[IOFailure]
    on error[InvalidTextFormat]
        log_message receives "Not a valid number" and 2
        reject with error[IOFailure]
    on error[EndOfInput]
        stop
    on success
        -- input_number содержит введённое число
end call
```

### Чтение байт

```
declare array[byte, 512] named raw_input
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]

declare integer[unsigned, 32bit] named bytes_read on stack is 0

call StdIO.read bytes
    into buffer as access: raw_input
    maximum count as copy: 512
    on error[ReadFailure]
        reject with error[IOFailure]
    on error[EndOfInput]
        stop
    on success
        bytes_read is result.count
end call
```

---

## Файловый ввод-вывод

### Открытие файла

```
declare StdIO.File named config_file
    on stack
    is default

call StdIO.open file
    with path as access: "/etc/audio.conf"
    with mode as copy: StdIO.FileMode.read only
    into result as owner: config_file
    on error[DeviceNotReady]
        reject with error[FileNotFound]
    on error[PermissionDenied]
        reject with error[AccessDenied]
    on success
        -- config_file готов к чтению
end call
```

Четыре режима открытия:

```
StdIO.FileMode.read only        -- только чтение
StdIO.FileMode.write only       -- только запись — создаёт или очищает
StdIO.FileMode.append           -- добавление в конец
StdIO.FileMode.read write       -- чтение и запись
```

### Чтение из файла

```
declare text named file_content
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

-- Прочитать всю строку
call StdIO.read line from file
    with file as access: config_file
    into result as owner: file_content
    on error[ReadFailure]
        reject with error[IOFailure]
    on error[EndOfInput]
        -- конец файла
        stop
    on success
        -- file_content содержит одну строку
end call

-- Прочитать весь файл
call StdIO.read all from file
    with file as access: config_file
    into result as owner: file_content
    on error[ReadFailure]
        reject with error[IOFailure]
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- file_content содержит весь файл
end call

-- Прочитать N байт
declare array[byte, 256] named file_chunk
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]

declare integer[unsigned, 32bit] named chunk_bytes_read on stack is 0

call StdIO.read bytes from file
    with file as access: config_file
    into buffer as access: file_chunk
    maximum count as copy: 256
    on error[ReadFailure]
        reject with error[IOFailure]
    on error[EndOfInput]
        stop
    on success
        chunk_bytes_read is result.count
end call
```

### Запись в файл

```
declare text named log_entry
    in segment[Text]
    on heap
    is "System initialized successfully"
    on allocation failure
        reject with error[OutOfMemory]

call StdIO.write line to file
    with file as access: log_file
    with message as access: log_entry
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- строка записана с переводом строки
end call

call StdIO.write bytes to file
    with file as access: log_file
    with data as access: raw_buffer
    with count as copy: bytes_to_write
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- байты записаны
end call
```

### Позиционирование в файле

```
declare integer[unsigned, 64bit] named file_position on stack is 0

-- Узнать текущую позицию
call StdIO.get file position
    with file as access: config_file
    on error[ReadFailure]
        reject with error[IOFailure]
    on success
        file_position is result
end call

-- Переместиться к конкретной позиции
call StdIO.seek file
    with file as access: config_file
    with position as copy: 0
    with from as copy: StdIO.SeekFrom.beginning
    on error[ReadFailure]
        reject with error[IOFailure]
    on success
        -- позиция установлена
end call
```

Три варианта `SeekFrom`:

```
StdIO.SeekFrom.beginning    -- от начала файла
StdIO.SeekFrom.current      -- от текущей позиции
StdIO.SeekFrom.end          -- от конца файла
```

### Закрытие файла

```
call StdIO.close file
    with file as owner: config_file
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- файл закрыт
        -- config_file больше не существует
end call
```

---

## Информация о файлах и директориях

### Проверка существования

```
declare boolean named file_exists on stack is false

call StdIO.file exists
    with path as access: "/etc/audio.conf"
    on success
        file_exists is result
end call
```

### Размер файла

```
declare integer[unsigned, 64bit] named file_size on stack is 0

call StdIO.file size
    with path as access: "/etc/audio.conf"
    on error[DeviceNotReady]
        reject with error[FileNotFound]
    on success
        file_size is result
end call
```

### Создание директории

```
call StdIO.create directory
    with path as access: "/var/log/audio"
    on error[PermissionDenied]
        reject with error[AccessDenied]
    on error[DeviceNotReady]
        reject with error[IOFailure]
    on success
        -- директория создана
end call
```

---

## Стандартные потоки

```
-- Стандартный вывод
call StdIO.write to stdout
    with message as access: output_message
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- выведено в stdout
end call

-- Стандартный поток ошибок
call StdIO.write to stderr
    with message as access: error_message
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- выведено в stderr
end call
```

---

## Буферизация

По умолчанию вывод буферизован. Для немедленного вывода — явный сброс:

```
call StdIO.flush stdout
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- буфер сброшен
end call

call StdIO.flush file
    with file as access: log_file
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- буфер файла сброшен
end call
```

---

## Реализация для голого железа

Программист реализует платформенный интерфейс:

```
implement platform interface[StdIO]
    for target[custom-arm-board]

    function write_bytes
        receives
            array[byte, any size] named data as access
        returns
            integer[unsigned, 32bit] named bytes_written
        on error[WriteFailure]
            reject with error[WriteFailure]
        body
            declare integer[unsigned, 32bit] named index on stack is 0
            repeat while index is less than count of data
                hardware write port uart_data_port
                    value data at index index
                    note "Write byte to UART"
                index is index plus 1
            end repeat
            bytes_written is count of data
        end body
    end function

    function read_bytes
        receives
            integer[unsigned, 32bit] named max_count
        returns
            array[byte, max_count] named received_data as owner
        on error[ReadFailure]
            reject with error[ReadFailure]
        body
            declare array[byte, max_count] named buffer
                on heap
                all elements is 0
                on allocation failure
                    reject with error[ReadFailure]

            declare integer[unsigned, 32bit] named index on stack is 0

            repeat while index is less than max_count
                declare byte named uart_status on stack is 0
                hardware read port uart_status_port
                    into uart_status
                if bit[data_ready] of uart_status is set
                    hardware read port uart_data_port
                        into buffer at index index
                    index is index plus 1
                end if
            end repeat

            received_data is buffer as owner
        end body
    end function

end implement
```

---

## Что гарантирует StdIO

```
✓ Один код работает на всех платформах
✓ Платформенные различия скрыты за интерфейсом
✓ Каждая операция имеет обработку ошибок
✓ Файлы закрываются через передачу as owner
✓ Буферизация явная — flush когда нужно
✓ Голое железо реализует тот же интерфейс
✓ Независимость от stdio.h или любой C библиотеки
```

---

*Готово. Переходим к 7.6 — StdTime?*

# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.6 StdTime — Время и таймеры

---

## Главное правило StdTime

> Время в C* всегда явное. Единицы измерения всегда указаны. Переполнение счётчиков обработано. StdTime работает одинаково на системах с операционной системой и на голом железе — через тот же платформенный интерфейс что и StdIO.

---

## Подключение

```
use module[StdTime]
```

---

## Единицы времени

StdTime использует явные типы для каждой единицы времени. Смешивание единиц без преобразования — отклонение компиляции:

```
define type[Nanoseconds]  as integer[unsigned, 64bit]
define type[Microseconds] as integer[unsigned, 64bit]
define type[Milliseconds] as integer[unsigned, 32bit]
define type[Seconds]      as integer[unsigned, 32bit]
define type[Minutes]      as integer[unsigned, 32bit]
define type[Hours]        as integer[unsigned, 32bit]
```

Преобразование между единицами — явное:

```
declare Milliseconds named delay_ms on stack is 500
declare Microseconds named delay_us on stack is 0

call StdTime.milliseconds to microseconds
    with value as copy: delay_ms
    on error[ArithmeticOverflow]
        reject with error[InvalidDuration]
    on success
        delay_us is result
        -- result равен 500000
end call
```

---

## Текущее время

### Монотонное время — для измерений

```
declare Nanoseconds named start_time on stack is 0
declare Nanoseconds named end_time on stack is 0
declare Nanoseconds named elapsed_time on stack is 0

call StdTime.monotonic now
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        start_time is result
end call

-- выполнить работу

call StdTime.monotonic now
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        end_time is result
end call

elapsed_time is end_time minus start_time
```

Монотонное время никогда не идёт назад. Оно не зависит от системных часов. Используется только для измерения интервалов.

### Системное время — для дат и часов

```
declare StdTime.SystemTime named current_time
    on stack
    is default

call StdTime.system now
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        current_time is result
end call

declare integer[unsigned, 32bit] named current_year on stack is 0
declare integer[unsigned, 32bit] named current_month on stack is 0
declare integer[unsigned, 32bit] named current_day on stack is 0
declare integer[unsigned, 32bit] named current_hour on stack is 0
declare integer[unsigned, 32bit] named current_minute on stack is 0
declare integer[unsigned, 32bit] named current_second on stack is 0

current_year   is current_time.year
current_month  is current_time.month
current_day    is current_time.day
current_hour   is current_time.hour
current_minute is current_time.minute
current_second is current_time.second
```

---

## Измерение времени выполнения

### Секундомер

```
declare StdTime.Stopwatch named performance_watch
    on stack
    is default

call StdTime.start stopwatch
    with watch as access: performance_watch
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        -- секундомер запущен
end call

-- выполнить измеряемый код

call StdTime.stop stopwatch
    with watch as access: performance_watch
    on success
        -- секундомер остановлен
end call

declare Nanoseconds named elapsed_nanoseconds on stack is 0

call StdTime.elapsed nanoseconds
    with watch as access: performance_watch
    on success
        elapsed_nanoseconds is result
end call

call StdIO.write formatted
    with template as access: "Execution time: {time} ns"
    with placeholder "time" as copy: elapsed_nanoseconds
    on error[WriteFailure]
        reject with error[IOFailure]
    on success
        -- выведено время выполнения
end call
```

### Сброс секундомера

```
call StdTime.reset stopwatch
    with watch as access: performance_watch
    on success
        -- секундомер сброшен в ноль
end call
```

---

## Задержки

### Задержка в основном потоке

```
declare Milliseconds named sleep_duration on stack is 100

call StdTime.sleep
    with duration as copy: sleep_duration
    on error[InvalidDuration]
        reject with error[InvalidDuration]
    on success
        -- поток спал минимум 100 миллисекунд
end call
```

`sleep` — минимальная гарантия. Реальное время может быть больше из-за планировщика операционной системы. Для точных задержек используется `busy wait`.

### Точная задержка — busy wait

```
declare Microseconds named precise_delay on stack is 50

call StdTime.busy wait
    with duration as copy: precise_delay
    on error[InvalidDuration]
        reject with error[InvalidDuration]
    on success
        -- прошло ровно 50 микросекунд
        -- процессор был занят всё это время
end call
```

`busy wait` — процессор крутится в цикле не уступая управление. Точно но расходует ресурсы. Используется только там где точность критична — например в обработчиках реального времени.

---

## Таймеры

### Одноразовый таймер

```
declare StdTime.Timer named shutdown_timer
    on stack
    is default

call StdTime.create timer
    with timer as access: shutdown_timer
    with duration as copy: 5000
    with duration unit as copy: StdTime.Unit.milliseconds
    repeating false
    on timer fires
        run function handle_shutdown_timeout
    end on timer fires
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        -- таймер создан но не запущен
end call

call StdTime.start timer
    with timer as access: shutdown_timer
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        -- таймер запущен
        -- через 5000 мс вызовется handle_shutdown_timeout
end call
```

### Повторяющийся таймер

```
declare StdTime.Timer named heartbeat_timer
    on stack
    is default

call StdTime.create timer
    with timer as access: heartbeat_timer
    with duration as copy: 1000
    with duration unit as copy: StdTime.Unit.milliseconds
    repeating true
    on timer fires
        run function send_heartbeat_signal
    end on timer fires
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        -- повторяющийся таймер создан
end call

call StdTime.start timer
    with timer as access: heartbeat_timer
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        -- таймер запущен — каждые 1000 мс вызывается функция
end call
```

### Остановка и уничтожение таймера

```
call StdTime.stop timer
    with timer as access: heartbeat_timer
    on error[TimerNotAvailable]
        reject with error[TimerNotAvailable]
    on success
        -- таймер остановлен но не уничтожен
end call

call StdTime.destroy timer
    with timer as owner: heartbeat_timer
    on success
        -- таймер уничтожен
        -- heartbeat_timer больше не существует
end call
```

---

## Работа с датами

### Сравнение времён

```
declare StdTime.SystemTime named time_a on stack is default
declare StdTime.SystemTime named time_b on stack is default
declare boolean named a_is_earlier on stack is false

call StdTime.is earlier than
    with first as copy: time_a
    with second as copy: time_b
    on success
        a_is_earlier is result
end call
```

### Интервал между двумя моментами

```
declare Seconds named interval_seconds on stack is 0

call StdTime.interval between
    with earlier as copy: time_a
    with later as copy: time_b
    on error[InvalidDuration]
        reject with error[InvalidDuration]
    on success
        interval_seconds is result
end call
```

### Добавление времени

```
declare StdTime.SystemTime named future_time on stack is default

call StdTime.add to time
    with base time as copy: current_time
    with add seconds as copy: 3600
    into result: future_time
    on error[ArithmeticOverflow]
        reject with error[InvalidDuration]
    on success
        -- future_time на час позже current_time
end call
```

---

## Форматирование времени

```
declare text named time_string
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdTime.format time
    with time as copy: current_time
    with format as access: "YYYY-MM-DD HH:MM:SS"
    into result as owner: time_string
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on error[InvalidTextFormat]
        reject with error[InvalidTextFormat]
    on success
        -- time_string содержит "2026-05-29 14:30:00"
end call
```

Символы формата:

```
YYYY    — год четыре цифры
MM      — месяц две цифры
DD      — день две цифры
HH      — часы две цифры 24-часовой формат
MM      — минуты две цифры
SS      — секунды две цифры
mmm     — миллисекунды три цифры
```

---

## Реализация для голого железа

```
implement platform interface[StdTime]
    for target[custom-arm-board]

    function monotonic now
        receives
            nothing
        returns
            Nanoseconds named current_ticks
        on error[TimerNotAvailable]
            reject with error[TimerNotAvailable]
        body
            declare integer[unsigned, 32bit] named raw_count on stack is 0

            hardware read register system_tick_counter
                into raw_count

            current_ticks is convert raw_count
                to Nanoseconds
                multiply by tick_period_nanoseconds
                on overflow
                    reject with error[TimerNotAvailable]
        end body
    end function

    function busy wait
        receives
            Microseconds named duration
        returns
            nothing
        on error[InvalidDuration]
            reject with error[InvalidDuration]
        body
            if duration is equal to 0
                reject with error[InvalidDuration]
            end if

            declare Nanoseconds named target_end on stack is 0
            declare Nanoseconds named current_tick on stack is 0

            call monotonic now
                on error[TimerNotAvailable]
                    reject with error[InvalidDuration]
                on success
                    current_tick is result
            end call

            target_end is current_tick plus
                duration multiply by 1000

            repeat while current_tick is less than target_end
                call monotonic now
                    on error[TimerNotAvailable]
                        stop
                    on success
                        current_tick is result
                end call
            end repeat
        end body
    end function

end implement
```

---

## Что гарантирует StdTime

```
✓ Единицы времени всегда явные — смешивание запрещено
✓ Монотонное время никогда не идёт назад
✓ sleep — минимальная гарантия времени
✓ busy wait — точная гарантия времени
✓ Таймеры уничтожаются через передачу as owner
✓ Переполнение счётчиков всегда обработано
✓ Форматирование времени через явные символы
✓ Голое железо реализует тот же интерфейс
✓ Независимость от time.h или любой C библиотеки
```

---

*Готово. Переходим к 7.7 — StdCollections?*
# C* Language Reference
## Раздел 7 — Стандартная библиотека
### 7.7 StdCollections — Коллекции данных

---

## Главное правило StdCollections

> Каждая коллекция в C* знает тип своих элементов, размер, и правила владения. Компилятор проверяет безопасность типов при каждой операции. Переполнение, доступ к пустой коллекции, и выход за границы — всё обработано явно.

---

## Подключение

```
use module[StdCollections]

-- Или отдельные коллекции:
use module[StdCollections.StdList]
use module[StdCollections.StdQueue]
use module[StdCollections.StdStack]
use module[StdCollections.StdDictionary]
use module[StdCollections.StdSet]
use module[StdCollections.StdRingBuffer]
```

---

## StdList — Динамический список

Список с динамическим размером. Элементы хранятся последовательно. Быстрый доступ по индексу.

### Создание

```
declare StdCollections.List[integer[signed, 32bit]] named number_list
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.List.create
    with list as access: number_list
    with initial capacity as copy: 16
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- список создан с начальной ёмкостью 16
end call
```

### Добавление элементов

```
-- Добавить в конец
call StdCollections.List.add last
    with list as access: number_list
    with element as copy: 42
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- 42 добавлен в конец
end call

-- Добавить в начало
call StdCollections.List.add first
    with list as access: number_list
    with element as copy: 10
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- 10 добавлен в начало
end call

-- Добавить по индексу
call StdCollections.List.add at index
    with list as access: number_list
    with element as copy: 25
    with index as copy: 1
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on error[IndexOutOfBounds]
        reject with error[IndexOutOfBounds]
    on success
        -- 25 добавлен на позицию 1
end call
```

### Чтение элементов

```
declare integer[signed, 32bit] named first_element on stack is 0
declare integer[signed, 32bit] named last_element on stack is 0
declare integer[signed, 32bit] named element_at_two on stack is 0

call StdCollections.List.get first
    with list as access: number_list
    on error[CollectionEmpty]
        reject with error[CollectionEmpty]
    on success
        first_element is result
end call

call StdCollections.List.get last
    with list as access: number_list
    on error[CollectionEmpty]
        reject with error[CollectionEmpty]
    on success
        last_element is result
end call

call StdCollections.List.get at index
    with list as access: number_list
    with index as copy: 2
    on error[IndexOutOfBounds]
        reject with error[IndexOutOfBounds]
    on success
        element_at_two is result
end call
```

### Удаление элементов

```
-- Удалить последний
call StdCollections.List.remove last
    with list as access: number_list
    on error[CollectionEmpty]
        reject with error[CollectionEmpty]
    on success
        -- последний элемент удалён
end call

-- Удалить по индексу
call StdCollections.List.remove at index
    with list as access: number_list
    with index as copy: 0
    on error[IndexOutOfBounds]
        reject with error[IndexOutOfBounds]
    on success
        -- элемент на позиции 0 удалён
end call
```

### Обход списка

```
declare integer[unsigned, 32bit] named list_size on stack is 0

call StdCollections.List.count
    with list as access: number_list
    on success
        list_size is result
end call

declare integer[unsigned, 32bit] named current_index on stack is 0
declare integer[signed, 32bit] named current_element on stack is 0

repeat while current_index is less than list_size

    call StdCollections.List.get at index
        with list as access: number_list
        with index as copy: current_index
        on error[IndexOutOfBounds]
            stop
        on success
            current_element is result
    end call

    process_number receives current_element as copy
    current_index is current_index plus 1

end repeat
```

### Уничтожение списка

```
call StdCollections.List.destroy
    with list as owner: number_list
    on success
        -- список уничтожен
        -- number_list больше не существует
end call
```

---

## StdQueue — Очередь FIFO

Первый вошёл — первый вышел. Элементы добавляются в конец, извлекаются из начала.

### Создание и использование

```
declare StdCollections.Queue[text] named message_queue
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.Queue.create
    with queue as access: message_queue
    with maximum capacity as copy: 256
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- очередь создана с максимальной ёмкостью 256
end call

-- Добавить в конец очереди
call StdCollections.Queue.enqueue
    with queue as access: message_queue
    with element as owner: incoming_message
    on error[CollectionFull]
        reject with error[QueueFull]
    on success
        -- сообщение добавлено
end call

-- Извлечь из начала очереди
declare text named next_message
    in segment[Text]
    on heap
    is empty
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.Queue.dequeue
    with queue as access: message_queue
    into result as owner: next_message
    on error[CollectionEmpty]
        reject with error[QueueEmpty]
    on success
        -- next_message содержит первый элемент
end call

-- Посмотреть первый элемент без извлечения
call StdCollections.Queue.peek
    with queue as access: message_queue
    on error[CollectionEmpty]
        reject with error[QueueEmpty]
    on success
        -- result содержит первый элемент as access
end call

-- Размер очереди
declare integer[unsigned, 32bit] named queue_size on stack is 0

call StdCollections.Queue.count
    with queue as access: message_queue
    on success
        queue_size is result
end call

-- Уничтожение
call StdCollections.Queue.destroy
    with queue as owner: message_queue
    on success
        -- очередь уничтожена
end call
```

---

## StdStack — Стек LIFO

Последний вошёл — первый вышел. Элементы добавляются и извлекаются с вершины.

### Создание и использование

```
declare StdCollections.Stack[integer[unsigned, 32bit]] named call_stack
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.Stack.create
    with stack as access: call_stack
    with maximum capacity as copy: 512
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- стек создан
end call

-- Добавить на вершину
call StdCollections.Stack.push
    with stack as access: call_stack
    with element as copy: return_address
    on error[CollectionFull]
        reject with error[StackOverflow]
    on success
        -- элемент добавлен на вершину
end call

-- Извлечь с вершины
declare integer[unsigned, 32bit] named top_value on stack is 0

call StdCollections.Stack.pop
    with stack as access: call_stack
    into result: top_value
    on error[CollectionEmpty]
        reject with error[StackUnderflow]
    on success
        -- top_value содержит верхний элемент
end call

-- Посмотреть вершину без извлечения
call StdCollections.Stack.peek
    with stack as access: call_stack
    on error[CollectionEmpty]
        reject with error[StackUnderflow]
    on success
        -- result содержит верхний элемент as access
end call

-- Уничтожение
call StdCollections.Stack.destroy
    with stack as owner: call_stack
    on success
        -- стек уничтожен
end call
```

---

## StdDictionary — Словарь ключ-значение

Хранит пары ключ-значение. Быстрый поиск по ключу.

### Создание

```
declare StdCollections.Dictionary[text, integer[signed, 32bit]]
    named device_registry
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.Dictionary.create
    with dictionary as access: device_registry
    with initial capacity as copy: 32
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- словарь создан
end call
```

### Добавление и обновление

```
declare text named device_name
    in segment[Text]
    on heap
    is "AudioCard"
    on allocation failure
        reject with error[OutOfMemory]

-- Добавить новую пару
call StdCollections.Dictionary.add
    with dictionary as access: device_registry
    with key as access: device_name
    with value as copy: 42
    on error[DuplicateKey]
        reject with error[DuplicateKey]
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- пара добавлена
end call

-- Обновить существующую пару
call StdCollections.Dictionary.update
    with dictionary as access: device_registry
    with key as access: device_name
    with value as copy: 100
    on error[KeyNotFound]
        reject with error[KeyNotFound]
    on success
        -- значение обновлено
end call

-- Добавить или обновить
call StdCollections.Dictionary.add or update
    with dictionary as access: device_registry
    with key as access: device_name
    with value as copy: 200
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- добавлено если не было, обновлено если было
end call
```

### Чтение и проверка

```
declare integer[signed, 32bit] named device_id on stack is 0
declare boolean named key_exists on stack is false

-- Получить значение
call StdCollections.Dictionary.get
    with dictionary as access: device_registry
    with key as access: device_name
    on error[KeyNotFound]
        reject with error[KeyNotFound]
    on success
        device_id is result
end call

-- Проверить существование ключа
call StdCollections.Dictionary.contains key
    with dictionary as access: device_registry
    with key as access: device_name
    on success
        key_exists is result
end call
```

### Удаление

```
call StdCollections.Dictionary.remove
    with dictionary as access: device_registry
    with key as access: device_name
    on error[KeyNotFound]
        reject with error[KeyNotFound]
    on success
        -- пара удалена
end call
```

### Обход словаря

```
declare integer[unsigned, 32bit] named dictionary_size on stack is 0

call StdCollections.Dictionary.count
    with dictionary as access: device_registry
    on success
        dictionary_size is result
end call

call StdCollections.Dictionary.for each
    with dictionary as access: device_registry
    run function process_device_entry
    on error[CollectionEmpty]
        -- словарь пуст
end call
```

Функция обхода:

```
function process_device_entry
    receives
        text named entry_key as access
        integer[signed, 32bit] named entry_value as copy
    returns
        nothing
    body
        log_message receives entry_key as access and 1
        log_integer receives entry_value
    end body
end function
```

### Уничтожение

```
call StdCollections.Dictionary.destroy
    with dictionary as owner: device_registry
    on success
        -- словарь уничтожен
end call
```

---

## StdSet — Множество уникальных элементов

Хранит только уникальные элементы. Быстрая проверка принадлежности.

### Создание и использование

```
declare StdCollections.Set[text] named active_devices
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.Set.create
    with set as access: active_devices
    with initial capacity as copy: 16
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- множество создано
end call

-- Добавить элемент
call StdCollections.Set.add
    with set as access: active_devices
    with element as access: device_name
    on error[DuplicateKey]
        -- элемент уже есть — не ошибка для множества
        -- просто пропускаем
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- элемент добавлен
end call

-- Проверить принадлежность
declare boolean named device_is_active on stack is false

call StdCollections.Set.contains
    with set as access: active_devices
    with element as access: device_name
    on success
        device_is_active is result
end call

-- Удалить элемент
call StdCollections.Set.remove
    with set as access: active_devices
    with element as access: device_name
    on error[KeyNotFound]
        -- элемента нет — не критично
    on success
        -- элемент удалён
end call

-- Размер множества
declare integer[unsigned, 32bit] named set_size on stack is 0

call StdCollections.Set.count
    with set as access: active_devices
    on success
        set_size is result
end call

-- Уничтожение
call StdCollections.Set.destroy
    with set as owner: active_devices
    on success
        -- множество уничтожено
end call
```

---

## StdRingBuffer — Кольцевой буфер

Буфер фиксированного размера. Новые данные перезаписывают старые при переполнении. Идеален для потоков данных реального времени.

### Создание

```
declare StdCollections.RingBuffer[integer[signed, 16bit]]
    named audio_ring_buffer
    on heap
    is default
    on allocation failure
        reject with error[OutOfMemory]

call StdCollections.RingBuffer.create
    with buffer as access: audio_ring_buffer
    with capacity as copy: 1024
    with on overflow as copy: StdCollections.RingBuffer.OverflowMode.overwrite oldest
    on error[OutOfMemory]
        reject with error[OutOfMemory]
    on success
        -- кольцевой буфер создан на 1024 элемента
end call
```

Три режима переполнения:

```
StdCollections.RingBuffer.OverflowMode.overwrite oldest
    -- новые данные перезаписывают старые

StdCollections.RingBuffer.OverflowMode.reject newest
    -- новые данные отбрасываются при переполнении

StdCollections.RingBuffer.OverflowMode.block sender
    -- отправитель блокируется пока не освободится место
```

### Запись и чтение

```
declare integer[signed, 16bit] named audio_sample on stack is 1024

-- Записать элемент
call StdCollections.RingBuffer.write
    with buffer as access: audio_ring_buffer
    with element as copy: audio_sample
    on error[CollectionFull]
        -- только при режиме reject newest
        reject with error[BufferFull]
    on success
        -- элемент записан
end call

-- Прочитать элемент
declare integer[signed, 16bit] named read_sample on stack is 0

call StdCollections.RingBuffer.read
    with buffer as access: audio_ring_buffer
    into result: read_sample
    on error[CollectionEmpty]
        reject with error[BufferEmpty]
    on success
        -- read_sample содержит прочитанный элемент
end call

-- Сколько элементов доступно
declare integer[unsigned, 32bit] named available_count on stack is 0

call StdCollections.RingBuffer.available
    with buffer as access: audio_ring_buffer
    on success
        available_count is result
end call

-- Сколько свободного места
declare integer[unsigned, 32bit] named free_count on stack is 0

call StdCollections.RingBuffer.free space
    with buffer as access: audio_ring_buffer
    on success
        free_count is result
end call

-- Уничтожение
call StdCollections.RingBuffer.destroy
    with buffer as owner: audio_ring_buffer
    on success
        -- буфер уничтожен
end call
```

---

## Что гарантирует StdCollections

```
✓ Все коллекции типизированы через обобщённые типы
✓ Компилятор проверяет типы при каждой операции
✓ Переполнение всегда обработано явно
✓ Доступ к пустой коллекции всегда обработан явно
✓ Все коллекции уничтожаются через передачу as owner
✓ Обход коллекций через явные функции
✓ Кольцевой буфер безопасен для потоков через каналы
✓ Независимость от любой C библиотеки
```

---

## Раздел 7 завершён

```
7.1 Организация стандартной библиотеки    ✓
7.2 StdMath — математика                  ✓
7.3 StdMemory — управление памятью        ✓
7.4 StdText — работа с текстом            ✓
7.5 StdIO — ввод и вывод                  ✓
7.6 StdTime — время и таймеры             ✓
7.7 StdCollections — коллекции данных     ✓
```

Стандартная библиотека C* полностью описана. Из коробки — всё необходимое. Без зависимостей от C. На любой платформе.

---

# C* Language Reference
## Раздел 8 — Инструменты и практика
### 8.1 IDE C* — Внешний вид и философия

---

## Главное правило IDE

> IDE C* — это рабочий инструмент а не витрина. Каждый элемент интерфейса существует потому что нужен. Никакого декора. Никаких анимаций. Чёрно-белая эстетика терминала с достаточным количеством кнопок чтобы не держать команды в голове.

---

## Цветовая схема

```
Фон                     #000000     чистый чёрный
Текст основной          #FFFFFF     чистый белый
Текст dim               #888888     тёмно-серый — комментарии
Текст bright            #FFFFFF жирный — ключевые слова
Границы и рамки         #444444     средний серый
Кнопки фон              #1A1A1A     почти чёрный
Кнопки текст            #FFFFFF     белый

Единственные цвета:
Ошибки                  #FF3333     красный
Предупреждения          #FFAA00     жёлтый
Успех                   #33FF33     зелёный
```

Три цвета — три состояния. Больше ничего цветного. Никогда.

---

## Подсветка синтаксиса — яркость вместо цвета

```
Ключевые слова языка    БЕЛЫЙ ЖИРНЫЙ
    function, declare, if, repeat, module...

Имена переменных        белый обычный
    audio_buffer, sample_rate, current_index...

Комментарии             серый dim
    -- это комментарий

Текстовые литералы      белый курсив
    "AudioEngine initialized"

Числовые литералы       белый подчёркнутый
    42, 0xFF, 0b10110101, 3.14

Типы                    белый жирный
    integer[signed, 32bit], float[64bit], boolean

Ошибки в коде           красное подчёркивание
    ~~~~~~~~~~~~

Предупреждения          жёлтое подчёркивание
    ............
```

---

## Раскладка интерфейса

```
┌─────────────────────────────────────────────────────────────────┐
│ C* IDE v1.0                              project: AudioSystem   │
├──────────────┬──────────────────────────────────────────────────┤
│              │                                                  │
│  ПРОЕКТ      │  AudioEngine.cstar                               │
│  ━━━━━━━━━━  │  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
│              │                                                  │
│  star/       │   1  module AudioEngine                         │
│   main       │   2      version[1.0]                           │
│   modules/   │   3      uses memory[Region]                    │
│    Audio     │   4      depends on module[LowLevelDriver]      │
│    Driver    │   5                                             │
│   types/     │   6      public function write_audio_sample     │
│    Sample    │   7          receives                           │
│              │   8              integer[signed, 16bit]         │
│  rules/      │   9                  named left_channel         │
│   project    │  10              integer[signed, 16bit]         │
│              │  11                  named right_channel        │
│  map/        │  12          returns                            │
│   project    │  13              nothing                        │
│              │  14          on error[BufferFull]               │
│  foreign/    │  15              reject with error[BufferFull]  │
│   project    │  16          body                               │
│              │  17  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~               │
│              │      ОШИБКА: null check missing                 │
│              │      buffer_ptr не проверен на null             │
│              │                                                  │
├──────────────┴──────────────────────────────────────────────────┤
│ ДЕЙСТВИЯ                                                        │
│ [ COMPILE ]  [ RUN ]  [ STOP ]  [ FORMAT ]  [ CHECK ]          │
│ [ VERBOSE ]  [ NORMAL ]  [ SILENT ]  [ SAVE ]  [ SAVE ALL ]    │
├─────────────────────────────────────────────────────────────────┤
│ ВЫВОД КОМПИЛЯТОРА                                               │
│ ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━  │
│ Stage 1 — Lexical Analysis                                  ✓  │
│ Stage 2 — Syntax Analysis                                   ✓  │
│ Stage 3 — Type Checking                                     ✓  │
│ Stage 4 — Level Traversal                                       │
│                                                                 │
│ ✗ LEVEL VIOLATION — Null check missing                          │
│   AudioEngine.cstar line 17                                     │
│   Pointer [buffer_ptr] used without null check                  │
│                                                                 │
│ Result: REJECTED at Stage 4         Time: 0.31 seconds          │
└─────────────────────────────────────────────────────────────────┘
```

---

## Панель кнопок — полный список

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ОСНОВНЫЕ ДЕЙСТВИЯ
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ COMPILE ]     Скомпилировать проект
[ RUN ]         Запустить программу
[ STOP ]        Остановить выполнение
[ FORMAT ]      Отформатировать текущий файл
[ CHECK ]       Проверить без полной компиляции
                (только синтаксис и типы)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
РЕЖИМ КОМПИЛЯТОРА
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ VERBOSE ]     Подробный вывод — всё
[ NORMAL  ]     Обычный вывод (по умолчанию)
[ SILENT  ]     Тихий вывод — только результат

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ФАЙЛ
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ SAVE ]        Сохранить текущий файл
[ SAVE ALL ]    Сохранить все файлы
[ NEW FILE ]    Создать новый файл
[ OPEN ]        Открыть файл

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ОТЛАДКА
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ WATCH ]       Режим наблюдения — реальное время
[ STEP ]        Режим шагов — точки останова
[ BREAK ]       Поставить точку останова
[ CLEAR ]       Убрать все точки останова
[ MEMORY ]      Показать состояние памяти

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
ПРОЕКТ
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
[ NEW PROJECT ] Создать новый проект
[ OPEN PROJECT] Открыть проект
[ BUILD ]       Собрать финальный исполняемый файл
[ CLEAN ]       Очистить папку build/
[ TARGET ]      Выбрать платформу компиляции
```

---

## Панель проекта

Левая панель показывает структуру проекта:

```
┌──────────────┐
│ ПРОЕКТ       │
│ ━━━━━━━━━━━  │
│              │
│ ▶ star/      │  ← раскрывается
│   ▼ modules/ │  ← раскрыта
│     Audio    │  ← файл
│     Driver   │  ← файл
│   types/     │
│   main       │
│              │
│ ▶ rules/     │
│ ▶ map/       │
│ ▶ foreign/   │
│ ▶ build/     │  ← только для чтения
│ ▶ watch/     │  ← только для чтения
│              │
│ ━━━━━━━━━━━  │
│ FILES: 12    │
│ ERRORS: 1    │  ← красный
│ WARNINGS: 0  │
└──────────────┘
```

---

## Панель вывода компилятора

Нижняя панель. Три вкладки:

```
[ COMPILER ] [ DEBUGGER ] [ MEMORY ]
```

**Вкладка COMPILER** — вывод компилятора в реальном времени. Стадии появляются по одной по мере прохождения.

**Вкладка DEBUGGER** — вывод отладчика. Значения переменных, состояние потоков.

**Вкладка MEMORY** — карта памяти. Сегменты, занятое место, пулы.

---

## Строка состояния

Самая нижняя строка — всегда видна:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
 AudioEngine.cstar  │  line 17  col 4  │  NORMAL  │  linux x86-64
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Четыре поля всегда видны:
```
Текущий файл    — что открыто
Позиция         — строка и столбец курсора
Режим           — VERBOSE / NORMAL / SILENT
Платформа       — целевая платформа компиляции
```

---

## Горячие клавиши

```
Ctrl+B          [ COMPILE ]
Ctrl+R          [ RUN ]
Ctrl+.          [ STOP ]
Ctrl+F          [ FORMAT ]
Ctrl+K          [ CHECK ]
Ctrl+S          [ SAVE ]
Ctrl+Shift+S    [ SAVE ALL ]
Ctrl+D          [ WATCH ] режим наблюдения
Ctrl+Shift+D    [ STEP ] режим шагов
F9              [ BREAK ] точка останова
Ctrl+Shift+B    [ BUILD ]
```

---

## Что IDE гарантирует программисту

```
✓ Ошибки подчёркнуты красным прямо в коде
✓ Предупреждения подчёркнуты жёлтым
✓ Вывод компилятора появляется в реальном времени
✓ Три режима компилятора переключаются одной кнопкой
✓ Структура проекта всегда видна слева
✓ Текущий статус всегда виден снизу
✓ Никаких цветов кроме трёх — красный жёлтый зелёный
✓ Никаких анимаций — только информация
```

---

*Готово. Переходим к 8.2 — Форматирование кода?*
# C* Language Reference
## Раздел 8 — Инструменты и практика
### 8.2 Форматирование кода

---

## Главное правило форматирования

> Форматирование в C* не является вкусовщиной. Существует один правильный способ форматировать каждую конструкцию. Форматировщик встроен в компилятор. Кнопка [ FORMAT ] приводит любой код к единственному правильному виду. Весь код на C* выглядит одинаково — независимо от того кто его написал.

---

## Почему один стиль для всех

```
Традиционно:                В C*:
    Каждая команда            Один стиль
    спорит о стиле            Никаких споров
    Разные форматы            Любой код читается
    в разных проектах         одинаково
    Форматировщики            Форматировщик
    с сотнями настроек        без настроек
```

Форматировщик C* не имеет файла настроек. Не имеет параметров. Одна команда — один результат.

---

## Правила отступов

### Базовый отступ

Четыре пробела на каждый уровень вложенности. Всегда. Табуляция запрещена.

```
program Example                         -- уровень 0, нет отступа

    function do_work                    -- уровень 1, 4 пробела
        receives                        -- уровень 2, 8 пробелов
            integer[signed, 32bit] named value
        returns                         -- уровень 2, 8 пробелов
            nothing
        body                            -- уровень 2, 8 пробелов
            if value is greater than 0  -- уровень 3, 12 пробелов
                log_message             -- уровень 4, 16 пробелов
            end if                      -- уровень 3, 12 пробелов
        end body                        -- уровень 2, 8 пробелов
    end function                        -- уровень 1, 4 пробела

end program                             -- уровень 0, нет отступа
```

---

## Правила пустых строк

### Между функциями — одна пустая строка

```
    function first_function
        receives
            nothing
        returns
            nothing
        body
            -- код
        end body
    end function
                                        ← одна пустая строка
    function second_function
        receives
            nothing
        returns
            nothing
        body
            -- код
        end body
    end function
```

### Внутри функции — пустые строки между логическими блоками

```
        body
            declare integer[signed, 32bit] named first on stack is 0
            declare integer[signed, 32bit] named second on stack is 0
                                        ← пустая строка
            call read_first_value
                on error[ReadFailed]
                    reject with error[ReadFailed]
                on success
                    first is result
            end call
                                        ← пустая строка
            call read_second_value
                on error[ReadFailed]
                    reject with error[ReadFailed]
                on success
                    second is result
            end call
                                        ← пустая строка
            declare integer[signed, 32bit] named total on stack is 0
            total is first plus second
        end body
```

### Максимум одна пустая строка подряд

Две и более пустых строки подряд — форматировщик сжимает до одной.

---

## Правила именования

### Переменные и функции — слова через подчёркивание

```
-- Правильно:
audio_buffer
sample_rate
current_index
write_audio_sample
calculate_total_size

-- Неправильно — форматировщик не исправляет имена
-- но компилятор предупреждает:
audioBuffer         ← camelCase запрещён
AudioBuffer         ← PascalCase запрещён
ab                  ← слишком коротко
temp                ← неинформативно
```

### Типы — PascalCase

```
-- Правильно:
AudioSample
DeviceControlRegister
ConnectionState
PlayerScore

-- Неправильно:
audio_sample        ← snake_case для типов запрещён
audiosample         ← нет разделения слов
```

### Константы — слова через подчёркивание заглавными буквами

```
-- Правильно:
MAX_BUFFER_SIZE
SAMPLE_RATE_DEFAULT
PI_VALUE
APPLICATION_NAME

-- Неправильно:
maxBufferSize       ← camelCase
max_buffer_size     ← строчные буквы для констант запрещены
```

### Модули — PascalCase

```
-- Правильно:
AudioEngine
LowLevelDriver
StdMath

-- Неправильно:
audio_engine        ← snake_case для модулей запрещён
audioengine         ← нет разделения слов
```

---

## Правила для типов

### Каждое свойство типа на своей строке

```
-- Правильно:
integer[signed, 32bit]
float[64bit]
pointer[to integer[signed, 32bit]]

-- Длинные типы — перенос:
array[
    integer[signed, 16bit],
    1024
]
```

### Объявление переменной — одна строка если помещается

```
-- Помещается — одна строка:
declare integer[signed, 32bit] named counter on stack is 0

-- Не помещается — перенос после named:
declare array[integer[signed, 16bit], 1024] named
    audio_sample_buffer
    on heap
    all elements is 0
    on allocation failure
        reject with error[OutOfMemory]
```

---

## Правила для вызовов функций

### Короткий вызов — одна строка

```
log_message receives "Started" and 1
```

### Длинный вызов — каждый параметр на своей строке

```
call calculate_rectangle_area
    with width as copy: room_width
    with height as copy: room_height
    on error[ArithmeticOverflow]
        reject with error[CalculationFailed]
    on success
        room_area is area
end call
```

### Граница — 80 символов в строке

Строка длиннее 80 символов — форматировщик переносит. Это не рекомендация — это правило.

---

## Правила для комментариев

### Однострочный комментарий — через пробел после --

```
-- Правильно
--Неправильно — нет пробела после --
```

### Комментарий на строке с кодом — два пробела перед --

```
declare integer[signed, 32bit] named counter on stack is 0  -- счётчик итераций
                                                            ↑
                                                     два пробела
```

### Многострочный комментарий — выравнивание текста

```
--[
    Это многострочный комментарий.
    Каждая строка начинается с четырёх пробелов
    относительно маркеров --[ и ]--
]--
```

### Комментарий перед функцией — обязательный формат

```
--[
    Функция: write_audio_sample
    Назначение: записывает аудио семпл в буфер устройства
    Вызывается: из потока audio_processing_thread
    Ограничения: не выделяет память на куче
]--
function write_audio_sample
    ...
end function
```

Форматировщик проверяет наличие комментария перед каждой `public` функцией. Отсутствие — предупреждение.

---

## Правила для блоков условий

### Простое условие — одна строка

```
if value is greater than 0
    -- код
end if
```

### Сложное условие — блок check с выравниванием

```
if check
    value is greater than 0
    and value is less than 100
    and status is equal to active
end check
    -- код
end if
```

### Цепочка условий — выравнивание otherwise

```
if connection_state is equal to connected
    process_data
otherwise if connection_state is equal to connecting
    wait_for_connection
otherwise
    reject with error[UnknownState]
end otherwise
end otherwise if
end if
```

---

## Правила для циклов

### Счётчик цикла объявляется прямо перед циклом

```
declare integer[unsigned, 32bit] named current_index on stack is 0

repeat while current_index is less than buffer_size
    process_item receives current_index
    current_index is current_index plus 1
end repeat
```

### Инкремент счётчика — последняя строка тела цикла

```
repeat while current_index is less than buffer_size
    -- весь код цикла
    -- ...
    current_index is current_index plus 1  ← всегда последним
end repeat
```

---

## Как работает кнопка [ FORMAT ]

```
1. Форматировщик читает текущий файл
2. Применяет все правила форматирования
3. Перезаписывает файл
4. Курсор возвращается на ту же логическую строку

Что форматировщик исправляет:
    ✓ Отступы — приводит к четырём пробелам
    ✓ Пустые строки — убирает лишние
    ✓ Длинные строки — переносит по правилам
    ✓ Пробелы вокруг операторов — добавляет где нет
    ✓ Комментарии — выравнивает

Что форматировщик НЕ исправляет:
    ✗ Имена переменных — только предупреждает
    ✗ Логику кода — никогда
    ✗ Порядок объявлений — только предупреждает
```

---

## Автоформатирование при сохранении

По умолчанию — форматировщик запускается при каждом сохранении:

```
compiler mode normal
compiler format on save enabled
```

Отключить:

```
compiler format on save disabled
    note "Manual formatting only"
```

---

## Что гарантирует форматировщик

```
✓ Весь код C* выглядит одинаково
✓ Никаких споров о стиле в команде
✓ Форматировщик без настроек — один результат
✓ Длинные строки всегда переносятся по правилам
✓ Комментарии перед публичными функциями обязательны
✓ Имена проверяются и вызывают предупреждения
✓ Форматирование при сохранении по умолчанию
```

---

*Готово. Переходим к 8.3 — Организация проекта?*

# C* Language Reference
## Раздел 8 — Инструменты и практика
### 8.3 Организация проекта

---

## Главное правило организации

> Структура проекта C* стандартна для всех проектов. Компилятор знает где искать каждый тип файла. Новый разработчик открывает любой проект на C* и сразу понимает где что лежит — потому что везде одинаково.

---

## Стандартная структура проекта

```
my_project/
│
├── star/                       ← исходный код
│   ├── main.cstar              ← точка входа
│   ├── modules/                ← модули проекта
│   │   ├── AudioEngine.cstar
│   │   ├── LowLevelDriver.cstar
│   │   └── EffectsProcessor.cstar
│   └── types/                  ← пользовательские типы
│       ├── AudioSample.cstar
│       └── DeviceState.cstar
│
├── rules/                      ← правила компилятора
│   ├── audio.cstar-rules       ← правила для аудио кода
│   ├── realtime.cstar-rules    ← правила для реального времени
│   └── project.cstar-rules     ← общие правила проекта
│
├── foreign/                    ← мосты к C
│   ├── libc.cstar-foreign      ← мост к стандартной C библиотеке
│   └── project.cstar-foreign   ← реестр всех внешних функций
│
├── map/                        ← карта модулей
│   └── project.cstar-map       ← единственный файл карты
│
├── platforms/                  ← платформенные реализации
│   ├── linux/
│   │   └── io_impl.cstar
│   ├── windows/
│   │   └── io_impl.cstar
│   └── bare_metal/
│       └── io_impl.cstar
│
├── build/                      ← результаты компиляции
│   ├── objects/                ← объектные файлы
│   ├── AudioSystem             ← исполняемый файл Linux
│   └── AudioSystem.exe         ← исполняемый файл Windows
│
├── watch/                      ← логи отладчика
│   ├── memory.log              ← состояние памяти
│   ├── threads.log             ← состояние потоков
│   └── trace.log               ← трассировка выполнения
│
└── project.cstar-config        ← настройки проекта
```

---

## Файл настроек проекта

`project.cstar-config` — единственный файл конфигурации. Живёт в корне проекта:

```
project AudioSystem
    version[1.0]
    author["Project Team"]
    description "Real-time audio processing system"

    compiler
        mode normal
        format on save enabled
        optimizations enabled
        target linux x86-64
    end compiler

    entry point
        file "star/main.cstar"
        program AudioSystem
    end entry point

    map
        file "map/project.cstar-map"
    end map

    rules
        file "rules/project.cstar-rules"
        file "rules/audio.cstar-rules"
        file "rules/realtime.cstar-rules"
    end rules

    foreign
        file "foreign/project.cstar-foreign"
    end foreign

    build
        output directory "build/"
        executable name "AudioSystem"
    end build

    watch
        output directory "watch/"
        memory log enabled
        thread log enabled
        trace log disabled
    end watch

end project
```

---

## Папка star/ — исходный код

### Файл main.cstar

Единственный файл в корне `star/`. Содержит только точку входа программы:

```
compiler mode normal
compiler format on save enabled

program AudioSystem

    use module[AudioEngine]
    use module[LowLevelDriver]
    use module[StdIO]
    use module[StdTime]

    declare constant text named version_string
        in segment[Text]
        is "1.0.0"

    body

        call StdIO.write formatted
            with template as access: "AudioSystem v{version} starting"
            with placeholder "version" as access: version_string
            on error[WriteFailure]
                reject with error[IOFailure]
            on success
                -- продолжаем
        end call

        call AudioEngine.initialize
            on error[InitializationFailed]
                call StdIO.write line
                    with message as access: "Initialization failed"
                    on error[WriteFailure]
                        -- ничего не делаем
                    on success
                        -- продолжаем
                end call
            on success
                -- продолжаем
        end call

        call AudioEngine.run main loop
            on error[RuntimeFailure]
                reject with error[RuntimeFailure]
            on success
                -- программа завершилась нормально
        end call

    end body

end program
```

### Правило одного файла на модуль

Один файл — один модуль. Имя файла совпадает с именем модуля:

```
AudioEngine.cstar       → module AudioEngine
LowLevelDriver.cstar    → module LowLevelDriver
AudioSample.cstar       → define type[AudioSample]
```

Компилятор проверяет это соответствие. Несовпадение — предупреждение.

---

## Папка types/ — пользовательские типы

Типы которые используются несколькими модулями — выносятся в отдельные файлы:

```
star/types/AudioSample.cstar:

--[
    Тип: AudioSample
    Назначение: стереофонический аудио семпл
    Используется: AudioEngine, EffectsProcessor
]--
define type[AudioSample]
    lives in segment[Structures]
    alignment 4 bytes
    contains
        integer[signed, 16bit] named left_channel
            default 0
        integer[signed, 16bit] named right_channel
            default 0
        integer[unsigned, 32bit] named timestamp
            default 0
        boolean named is_silent
            default true
        byte named reserved
            default 0
            note "alignment padding"
    end contains
end type
```

Типы используемые только одним модулем — объявляются внутри файла модуля.

---

## Папка rules/ — правила компилятора

Правила разделяются по теме. Каждая тема — отдельный файл:

```
rules/audio.cstar-rules     ← правила для аудио функций
rules/realtime.cstar-rules  ← правила для реального времени
rules/hardware.cstar-rules  ← правила для работы с железом
rules/project.cstar-rules   ← общие правила проекта
```

Общие правила проекта `project.cstar-rules` подключают остальные:

```
compiler rules named ProjectRules
    version[1.0]

    include rule set from "audio.cstar-rules"
    include rule set from "realtime.cstar-rules"
    include rule set from "hardware.cstar-rules"

    define compiler rule named AllModulesHaveVersion
        description "Every module must declare a version"
        severity error
        applies to modules
            all modules in project
        end applies to
        requires
            version declaration present
        end requires
        on violation
            message "Module missing version declaration"
            hint "Add version[X.Y] to module header"
        end on violation
    end compiler rule

end compiler rules
```

---

## Папка foreign/ — мосты к C

Каждая C библиотека — отдельный файл:

```
foreign/libc.cstar-foreign      ← мост к libc
foreign/libpthread.cstar-foreign ← мост к pthreads
foreign/libm.cstar-foreign      ← мост к libm
```

Реестр всех мостов `project.cstar-foreign`:

```
foreign registry named ProjectExternalDependencies

    include gateway file "libc.cstar-foreign"
    include gateway file "libpthread.cstar-foreign"

end foreign registry
```

---

## Папка platforms/ — платформенные реализации

Когда проект поддерживает несколько платформ:

```
platforms/
    linux/
        io_impl.cstar       ← реализация StdIO для Linux
        time_impl.cstar     ← реализация StdTime для Linux
    windows/
        io_impl.cstar
        time_impl.cstar
    bare_metal/
        io_impl.cstar       ← реализация через UART
        time_impl.cstar     ← реализация через системный таймер
```

Компилятор выбирает папку автоматически по `compiler target` в конфиге.

---

## Папка build/ — результаты компиляции

Генерируется автоматически. Никогда не редактируется вручную. Никогда не добавляется в систему контроля версий:

```
build/
    objects/
        AudioEngine.o
        LowLevelDriver.o
        EffectsProcessor.o
    AudioSystem           ← исполняемый файл
    AudioSystem.map       ← карта памяти программы
    AudioSystem.symbols   ← таблица символов для отладчика
```

---

## Папка watch/ — логи отладчика

Генерируется при работе отладчика. Содержит снимки состояния программы:

```
watch/
    memory.log          ← состояние памяти в реальном времени
    threads.log         ← состояние потоков
    trace.log           ← трассировка вызовов функций
    variables.log       ← значения переменных по времени
```

Формат логов — читаемый текст. Можно открыть в любом редакторе:

```
[00:00:01.234] MEMORY
    Heap used:     12,344 bytes
    Heap free:     53,192 bytes
    Stack depth:   3 frames
    Active pools:  2

[00:00:01.235] THREAD audio_processing_thread
    State:         running
    Stack used:    2,048 bytes
    Channel audio_input_channel: 47 items

[00:00:01.236] VARIABLE current_sample
    Type:          AudioSample
    Location:      heap
    left_channel:  1024
    right_channel: 1008
    timestamp:     1234567
    is_silent:     false
```

---

## Система контроля версий

Файлы которые добавляются в репозиторий:

```
✓ star/             исходный код
✓ rules/            правила компилятора
✓ foreign/          мосты к C
✓ map/              карта модулей
✓ platforms/        платформенные реализации
✓ project.cstar-config  настройки проекта
```

Файлы которые НЕ добавляются:

```
✗ build/            генерируется компилятором
✗ watch/            генерируется отладчиком
```

Стандартный `.gitignore` для проекта C*:

```
build/
watch/
```

---

## Создание нового проекта

Кнопка [ NEW PROJECT ] в IDE создаёт всю структуру автоматически:

```
C* IDE v1.0
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
NEW PROJECT

Project name:    AudioSystem
Author:          _
Target platform: [ linux x86-64 ] [ windows ] [ bare-metal ]
Version:         1.0

[ CREATE ]  [ CANCEL ]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

После нажатия [ CREATE ]:

```
Creating project structure...

    ✓ star/main.cstar
    ✓ star/modules/
    ✓ star/types/
    ✓ rules/project.cstar-rules
    ✓ foreign/project.cstar-foreign
    ✓ map/project.cstar-map
    ✓ platforms/linux/
    ✓ project.cstar-config

Project AudioSystem created successfully.
Opening main.cstar...
```

---

## Что гарантирует стандартная структура

```
✓ Любой проект C* имеет одинаковую структуру
✓ Компилятор знает где искать каждый файл
✓ Новый разработчик ориентируется сразу
✓ build/ и watch/ никогда не редактируются вручную
✓ Один модуль — один файл — одно имя
✓ Платформенные реализации изолированы в platforms/
✓ IDE создаёт структуру автоматически
```

---

*Готово. Переходим к 8.4 — Отладка?*

# C* Language Reference
## Раздел 8 — Инструменты и практика
### 8.5 Рекомендации по стилю

---

## Главное правило стиля

> Стиль C* — это не эстетика. Это коммуникация. Код пишется один раз но читается много раз. Каждое решение о стиле должно делать код более понятным для следующего человека который его откроет — даже если этим человеком будешь ты сам через полгода.

---

## Именование — самое важное

### Имя должно отвечать на вопрос "что это?"

```
-- Плохо — отвечает на "что делает код":
declare integer[signed, 32bit] named counter on stack is 0
declare boolean named flag on stack is false
declare byte named buf on stack is 0

-- Хорошо — отвечает на "что это такое":
declare integer[signed, 32bit] named processed_sample_count on stack is 0
declare boolean named device_is_initialized on stack is false
declare byte named incoming_midi_byte on stack is 0
```

### Функция называется по действию которое выполняет

```
-- Плохо:
function audio on stack is 0
function data
function process

-- Хорошо:
function write_audio_sample
function calculate_buffer_checksum
function initialize_hardware_device
```

### Булевы переменные начинаются с вопроса

```
-- Хорошо — читается как утверждение:
declare boolean named device_is_ready on stack is false
declare boolean named buffer_has_data on stack is false
declare boolean named connection_was_established on stack is false
declare boolean named sample_is_silent on stack is true
```

### Счётчики и индексы — явно называть что считают

```
-- Плохо:
declare integer[unsigned, 32bit] named i on stack is 0
declare integer[unsigned, 32bit] named n on stack is 0
declare integer[unsigned, 32bit] named count on stack is 0

-- Хорошо:
declare integer[unsigned, 32bit] named current_sample_index on stack is 0
declare integer[unsigned, 32bit] named processed_frame_count on stack is 0
declare integer[unsigned, 32bit] named retry_attempt_count on stack is 0
```

---

## Функции — контракт прежде всего

### Пиши блоки on error до того как писать body

Сначала думай что может пойти не так. Потом пиши как должно работать:

```
-- Правильный порядок мышления:
function open_audio_device
    receives
        integer[unsigned, 32bit] named device_id
    returns
        pointer[to AudioDevice] named opened_device
    -- Сначала — что может пойти не так:
    on error[DeviceNotFound]
        reject with error[DeviceNotFound]
    on error[PermissionDenied]
        reject with error[PermissionDenied]
    on error[DeviceAlreadyOpen]
        reject with error[DeviceAlreadyOpen]
    -- Потом — как работает:
    body
        -- код
    end body
end function
```

### Функция делает одно

Если название функции содержит "и" — скорее всего это две функции:

```
-- Плохо — делает два дела:
function initialize_device_and_start_capture
function validate_and_process_sample

-- Хорошо — каждая делает одно:
function initialize_device
function start_capture
function validate_sample
function process_sample
```

### Короткие функции лучше длинных

Если тело функции не помещается на один экран — скорее всего её нужно разбить. Ориентир: 30-40 строк тела максимум.

---

## Память — явность важнее краткости

### Всегда указывай on stack или on heap явно

Даже если кажется очевидным:

```
-- Не пропускай — пиши всегда:
declare integer[signed, 32bit] named sample_rate on stack is 44100
declare byte named audio_buffer on heap is 0
```

### Release близко к allocate — видно кто освобождает

```
-- Хорошо — allocate и release в одной функции:
function process_one_frame
    body
        declare byte named frame_buffer on heap is 0

        call allocate and fill frame_buffer
            ...
        end call

        call process frame_buffer
            ...
        end call

        release frame_buffer    ← близко к allocate
    end body
end function

-- Плохо — release в другом месте:
-- тяжело понять кто владеет и кто освобождает
```

### Предпочитай as access когда владение не нужно

```
-- Если функция только читает — передавай as access:
call analyze_audio
    with data as access: audio_buffer    ← не забирает владение
    ...
end call

-- as owner — только когда функция должна владеть и освобождать:
call consume_and_release
    with data as owner: audio_buffer     ← забирает владение
    ...
end call
```

---

## Ошибки — обрабатывай конкретно

### Не игнорируй ошибки молча

```
-- Плохо — ошибка проглочена:
call read_sensor
    on error[SensorFailure]
        -- ничего не делаем
    on success
        sensor_value is result
end call

-- Хорошо — ошибка залогирована даже если некритична:
call read_sensor
    on error[SensorFailure]
        log_message receives "Sensor read failed — using last value" and 2
    on success
        sensor_value is result
end call
```

### Создавай конкретные ошибки вместо общих

```
-- Плохо — слишком общая ошибка:
reject with error[Failed]
reject with error[Error]

-- Хорошо — конкретная ошибка с контекстом:
reject with error[AudioDeviceInitializationFailed]
reject with error[BufferAllocationExceededMaximumSize]
```

### Обрабатывай ошибки на правильном уровне

```
-- Плохо — низкоуровневая ошибка всплывает на верх:
function main_loop
    on error[NullPointerAccess]    ← это слишком низкоуровнево для main
        reject with error[NullPointerAccess]

-- Хорошо — преобразуй в ошибку своего уровня:
function main_loop
    on error[SystemInitializationFailed]    ← понятно на этом уровне
        reject with error[SystemInitializationFailed]
```

---

## Комментарии — объясняй почему не что

### Комментарий объясняет решение а не действие

```
-- Плохо — повторяет код:
-- увеличить счётчик на единицу
current_index is current_index plus 1

-- Хорошо — объясняет почему:
-- пропускаем нулевой семпл — он используется как маркер конца потока
current_index is current_index plus 1
```

### Комментируй неочевидные числа

```
-- Плохо:
declare integer[unsigned, 32bit] named buffer_size on stack is 4096

-- Хорошо:
-- 4096 байт = 1024 семпла по 4 байта — один фрейм при 44100 Гц
declare integer[unsigned, 32bit] named buffer_size on stack is 4096
```

### Комментируй аппаратные адреса всегда

```
declare hardware pointer[to byte] named vga_buffer
    at address 0xB8000
    size 4000 bytes
    access write only
    managed by hardware
    note "VGA text mode buffer — 80x25 символов по 2 байта каждый"
    --    ↑ это не опционально — это требование стиля
```

---

## Структура файла — один модуль один файл

### Стандартный порядок внутри файла модуля

```
--[
    Модуль: AudioEngine
    Назначение: обработка аудио данных в реальном времени
    Зависит от: LowLevelDriver, StdMath
    Автор: Project Team
    Версия: 1.0
]--

module AudioEngine
    version[1.0]
    uses memory[Region]
    depends on module[LowLevelDriver]
    depends on module[StdMath]

    -- 1. Пользовательские ошибки модуля
    define error[AudioEngineInitializationFailed]
        ...
    end error

    -- 2. Приватные константы
    declare constant integer[unsigned, 32bit] named MAX_BUFFER_SIZE is 4096

    -- 3. Приватные типы (если не вынесены в types/)
    define type[InternalBuffer]
        ...
    end type

    -- 4. Инициализация и завершение
    on module load
        ...
    end on

    on module unload
        ...
    end on

    -- 5. Приватные функции
    private function validate_buffer
        ...
    end function

    -- 6. Внутренние функции
    internal function sync_with_driver
        ...
    end function

    -- 7. Публичные функции — интерфейс модуля
    public function initialize
        ...
    end function

    public function write_audio_sample
        ...
    end function

end module
```

---

## Циклы — явность превыше краткости

### Всегда именуй вложенные циклы

```
-- Плохо — непонятно из какого цикла выходим:
repeat while outer_condition
    repeat while inner_condition
        if found
            stop    ← из какого цикла?
        end if
    end repeat
end repeat

-- Хорошо — именованный выход:
repeat while outer_condition
    named outer_search_loop

    repeat while inner_condition
        named inner_search_loop

        if found
            stop loop[outer_search_loop]    ← явно и понятно
        end if

    end repeat

end repeat
```

### Объявляй максимум итераций для критичных циклов

```
-- Хорошо — защита от бесконечного выполнения:
repeat while waiting_for_response is equal to true
    maximum iterations 1000
    on limit reached
        reject with error[DeviceResponseTimeout]

    check_for_response
    wait_microseconds receives 100

end repeat
```

---

## Многопоточность — явность владения

### Всегда документируй какой поток владеет данными

```
--[
    audio_master_buffer объявлен в capture_thread
    передаётся as owner в audio_processing_thread через audio_input_channel
    после передачи capture_thread не имеет доступа
]--
declare byte named audio_master_buffer on heap is 0
```

### Каналы называй по направлению данных

```
-- Хорошо — из имени понятно направление:
declare channel named capture_to_processing_channel
    of type AudioSample
    ...

declare channel named processing_to_playback_channel
    of type AudioSample
    ...

-- Плохо — неясно куда идут данные:
declare channel named audio_channel_one
declare channel named channel_a
```

---

## Чего никогда не делать

```
✗ Не используй однобуквенные имена даже для счётчиков
✗ Не оставляй пустые блоки без комментария
✗ Не пиши вложенность глубже пяти уровней
✗ Не создавай функции длиннее сорока строк тела
✗ Не игнорируй ошибки молча
✗ Не используй магические числа без комментария
✗ Не передавай as owner если as access достаточно
✗ Не смешивай логику разных уровней в одной функции
✗ Не откладывай release далеко от allocate
✗ Не называй функцию с союзом "и" — раздели на две
```

---

## Чего всегда делать

```
✓ Имя отвечает на вопрос "что это такое"
✓ Функция делает одно действие
✓ Ошибки обрабатываются конкретно
✓ Комментарии объясняют почему а не что
✓ Аппаратные адреса всегда документированы
✓ Вложенные циклы всегда именованы
✓ Булевы переменные читаются как утверждение
✓ Release близко к allocate
✓ Публичные функции имеют комментарий-заголовок
✓ Модуль начинается с комментария-заголовка
```

---

## Раздел 8 завершён

```
8.1 IDE C* — внешний вид и философия    ✓
8.2 Форматирование кода                 ✓
8.3 Организация проекта                 ✓
8.4 Отладка                             ✓
8.5 Рекомендации по стилю              ✓
```

Инструменты и практика C* полностью описаны. Язык знает как должен выглядеть код, как организован проект, как работает отладчик, и как писать хороший код.

---

## Книга C* Language Reference завершена

```
Раздел 1 — Синтаксис                   ✓
Раздел 2 — Память и владение           ✓
Раздел 3 — Управление потоком          ✓
Раздел 4 — Типы и структуры данных     ✓
Раздел 5 — Система и железо            ✓
Раздел 6 — Компилятор и уровень        ✓
Раздел 7 — Стандартная библиотека      ✓
Раздел 8 — Инструменты и практика      ✓
```
