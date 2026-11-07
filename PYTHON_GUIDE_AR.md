# دليل بايثون الشامل للمبتدئين

هذا الدليل العربي يشرح أساسيات Python بأمثلة عملية. يمكنك نسخ الأمثلة إلى ملفات بامتداد `.py` وتشغيلها باستخدام `python اسم_الملف.py` (أو `python3` بحسب نظامك).

> **مهم:** بايثون تعتمد على المسافات البادئة. استخدم عادةً أربع مسافات داخل الشروط والحلقات والدوال، ولا تخلطها بعلامات الجدولة.

## فهرس المحتويات

1. ما هي بايثون وتجهيز بيئة العمل
2. الطباعة والتعليقات والمتغيّرات
3. أنواع البيانات والتحويل بينها
4. العمليات الحسابية والمقارنات والمنطق
5. إدخال المستخدم والشروط
6. الحلقات
7. النصوص
8. القوائم والصفوف والمجموعات والقواميس
9. الدوال
10. التعامل مع الأخطاء
11. الملفات
12. الوحدات والحزم وبيئة العمل
13. البرمجة كائنية التوجّه
14. أدوات مفيدة ومواضيع إضافية
15. مشاريع تدريبية
16. تمارين ومفاتيح إجابة مختصرة

---

## 1. ما هي بايثون؟

بايثون لغة برمجة عامة الاستخدام، معروفة بصياغتها المقروءة. تُستخدم في الأتمتة، وتطوير الويب، وتحليل البيانات، والذكاء الاصطناعي، والتعليم، وغيرها. هذه الأمثلة تعمل على Python 3.

تحقق من تثبيتها بفتح الطرفية وكتابة:

```bash
python --version
```

وقد يكون الأمر على بعض الأنظمة:

```bash
python3 --version
```

أنشئ ملفًا مثل `hello.py` واكتب:

```python
print("مرحبًا بالعالم!")
```

ثم شغّله من الطرفية:

```bash
python hello.py
```

## 2. الطباعة والتعليقات والمتغيّرات

الدالة `print` تعرض القيم:

```python
print("أهلًا")
print(42)
print("النتيجة:", 2 + 3)
```

التعليق يبدأ بعلامة `#`، ولا ينفذه البرنامج:

```python
# هذا تعليق يشرح السطر التالي
print("صباح الخير")
```

المتغيّر اسم يشير إلى قيمة. لا تحتاج إلى التصريح عن نوعه مسبقًا:

```python
name = "سارة"
age = 20
height = 1.68
is_student = True

print(name)
print(f"اسمي {name} وعمري {age}")
```

أسماء المتغيّرات حساسة لحالة الأحرف، وتُكتب عادةً بحروف صغيرة مع شرطة سفلية: `user_name`. لا تبدأ الاسم برقم ولا تستخدم كلمات بايثون المحجوزة مثل `if` و`for`.

## 3. أنواع البيانات والتحويل بينها

الأنواع الأساسية:

```python
text = "مرحبا"       # str: نص
whole_number = 12     # int: عدد صحيح
decimal_number = 2.5  # float: عدد عشري
is_ready = False      # bool: صحيح أو خطأ
nothing = None        # NoneType: لا توجد قيمة
```

اعرف نوع قيمة باستخدام `type`:

```python
print(type(text))
print(type(whole_number))
```

التحويل بين الأنواع:

```python
age_text = "21"
age = int(age_text)
price = float("3.75")
message = str(age)

print(age + 1)
```

قد يفشل التحوي�� إذا لم يكن النص مناسبًا، مثل `int("مرحبا")`. سنتناول معالجة ذلك في قسم الأخطاء.

## 4. العمليات

### حسابية

```python
a = 10
b = 3

print(a + b)   # جمع: 13
print(a - b)   # طرح: 7
print(a * b)   # ضرب: 30
print(a / b)   # قسمة عادية: 3.333...
print(a // b)  # قسمة صحيحة: 3
print(a % b)   # باقي القسمة: 1
print(a ** b)  # أس: 1000
```

### مقارنات

تعيد المقارنات قيمة منطقية `True` أو `False`:

```python
x = 5
print(x == 5)  # يساوي
print(x != 3)  # لا يساوي
print(x > 2)
print(x >= 5)
print(x < 10)
print(x <= 4)
```

`=` للإسناد، أما `==` فللمقارنة.

### منطقية

```python
age = 22
has_ticket = True

print(age >= 18 and has_ticket)  # كلا الشرطين صحيح
print(age < 18 or has_ticket)    # واحد على الأقل صحيح
print(not has_ticket)            # عكس القيمة
```

## 5. إدخال المستخدم والشروط

`input` تقرأ نصًا من المستخدم. حوّل الإدخال إلى رقم عند الحاجة:

```python
name = input("ما اسمك؟ ")
age = int(input("كم عمرك؟ "))
print(f"أهلًا {name}. بعد سنة سيكون عمرك {age + 1}.")
```

الشروط تستخدم `if` و`elif` و`else`:

```python
score = int(input("أدخل درجتك: "))

if score >= 90:
    print("ممتاز")
elif score >= 70:
    print("جيد")
else:
    print("تحتاج إلى مزيد من التدريب")
```

يمكن جمع الشروط، مثل `if age >= 18 and has_id:`. انتبه إلى النقطتين `:` والمسافة البادئة بعد كل شرط.

## 6. الحلقات

### حلقة `for`

تكرّر على عناصر مجموعة أو على مجال من الأرقام:

```python
for number in range(1, 4):
    print(number)  # 1 ثم 2 ثم 3

for letter in "Python":
    print(letter)
```

`range(stop)` يبدأ من صفر ولا يشمل `stop`. ويمكن استخدام `range(start, stop, step)`:

```python
for number in range(2, 11, 2):
    print(number)  # 2، 4، 6، 8، 10
```

### حلقة `while`

تستمر طالما الشرط صحيح. يجب تحديث الحالة كي لا تصبح الحلقة لا نهائية:

```python
count = 1
while count <= 3:
    print(count)
    count += 1
```

### `break` و`continue`

`break` تنهي الحلقة، و`continue` تنتقل إلى التكرار التالي:

```python
for number in range(1, 6):
    if number == 2:
        continue
    if number == 5:
        break
    print(number)
```

## 7. النصوص

النصوص من النوع `str`، ويمكن استخدام اقتباس مفرد أو مزدوج:

```python
text = "Python لغة ممتعة"
print(len(text))
print(text.upper())
print(text.lower())
print(text.replace("ممتعة", "مفيدة"))
print(text.startswith("Python"))
```

الفهرسة تبدأ من الصفر، والفهرسة السالبة تبدأ من آخر النص:

```python
word = "Python"
print(word[0])   # P
print(word[-1])  # n
print(word[1:4]) # yth
```

النصوص غير قابلة للتعديل في مكانها؛ العمليات عليها تنشئ نصًا جديدًا. نسّق النصوص باستخدام f-string:

```python
name = "علي"
score = 95
print(f"حصل {name} على {score} درجة")
```

## 8. مجموعات البيانات

### القوائم `list`

قائمة مرتبة وقابلة للتعديل، وتسمح بتكرار القيم:

```python
fruits = ["تفاح", "موز", "برتقال"]
fruits.append("عنب")
fruits[0] = "كمثرى"
print(fruits)
print(fruits[1])
print(len(fruits))

for fruit in fruits:
    print(fruit)
```

عمليات مفيدة: `append` للإضافة، `remove` للحذف بالقيمة، `pop` للحذف وإرجاع عنصر، و`sort` للترتيب. انتبه إلى أن `sort()` تعدّل القائمة نفسها.

### الصفوف الثابتة `tuple`

صف مرتب لا يمكن تغيير عناصره بعد إنشائه:

```python
point = (4, 7)
print(point[0])
```

استخدمه عندما تريد مجموعة قيم ثابتة.

### المجموعات `set`

مجموعة غير مرتبة من القيم الفريدة:

```python
colors = {"أحمر", "أزرق", "أحمر"}
colors.add("أخضر")
print(colors)  # لن يظهر الأحمر مرتين
```

يمكن استخدامها لإزالة التكرار أو لاختبار وجود عنصر بسرعة:

```python
unique_numbers = set([1, 2, 2, 3])
print(unique_numbers)
```

### القواميس `dict`

تخزّن بيانات على شكل مفتاح وقيمة:

```python
person = {
    "name": "نور",
    "age": 24,
    "city": "عمّان",
}

print(person["name"])
person["age"] = 25
person["job"] = "مصممة"
print(person.get("email", "غير متوفر"))

for key, value in person.items():
    print(key, value)
```

استخدم `get` عندما قد لا يكون المفتاح موجودًا، لتجنب `KeyError`.

### فهم القوائم (List comprehension)

طريقة مختصرة لإنشاء قائمة:

```python
squares = [number ** 2 for number in range(1, 6)]
even_numbers = [number for number in range(10) if number % 2 == 0]
print(squares)
print(even_numbers)
```

## 9. الدوال

الدالة تجمع أوامر قابلة لإعادة الاستخدام. عرّفها بـ `def`:

```python
def greet(name):
    return f"مرحبًا يا {name}!"

message = greet("ريم")
print(message)
```

- **المعاملات** هي الأسماء بين قوسَي تعريف الدالة.
- **القيم الممرّرة** هي القيم المستخدمة عند استدعائها.
- `return` تعيد نتيجة. إذا لم تكتبها فالدالة تعيد `None`.

قيمة افتراضية ومعاملات مسماة:

```python
def power(number, exponent=2):
    return number ** exponent

print(power(4))
print(power(2, exponent=3))
```

يمكن إرجاع أكثر من قيمة على هيئة صف:

```python
def min_max(numbers):
    return min(numbers), max(numbers)

smallest, largest = min_max([8, 2, 5])
print(smallest, largest)
```

## 10. التعامل مع الأخطاء

قد تحدث أخطاء وقت التشغيل. استخدم `try` و`except` لمعالجة المتوقع منها:

```python
try:
    age = int(input("أدخل عمرك: "))
except ValueError:
    print("الرجاء إدخال عدد صحيح")
else:
    print(f"عمرك {age}")
```

- `try`: أوامر قد تنتج خطأ.
- `except`: طريقة معالجة خطأ محدد.
- `else`: ينفذ عند عدم حدوث خطأ.
- `finally`: ينفذ سواء حدث خطأ أم لا.

التقط أنواع الأخطاء التي تتوقعها بدل استخدام `except:` العام الذي قد يخفي مشكلات غير متوقعة.

## 11. الملفات

استخدم `with open` حتى يُغلق الملف تلقائيًا. حدّد الترميز، خصوصًا للملفات العربية:

```python
with open("notes.txt", "w", encoding="utf-8") as file:
    file.write("ملاحظتي الأولى\n")
    file.write("ملاحظتي الثانية\n")
```

أوضاع شائعة:

- `"r"`: قراءة.
- `"w"`: كتابة مع استبدال محتوى الملف الموجود.
- `"a"`: إضافة إلى نهاية الملف.

قراءة الملف:

```python
with open("notes.txt", "r", encoding="utf-8") as file:
    content = file.read()

print(content)
```

للقراءة سطرًا سطرًا:

```python
with open("notes.txt", encoding="utf-8") as file:
    for line in file:
        print(line.rstrip())
```

## 12. الوحدات والحزم وبيئة العمل

الوحدة ملف Python يمكن استيراده. المكتبة القياسية تأتي مع بايثون:

```python
import math
print(math.sqrt(25))

from random import randint
print(randint(1, 6))
```

إذا كان لديك ملف `helpers.py` في المجلد نفسه، يمكنك استخدام دواله عبر `import helpers`.

تثبيت مكتبة خارجية يتم غالبًا باستخدام `pip`:

```bash
python -m pip install requests
```

في المشاريع الجدية، أنشئ بيئة افتراضية لعزل المكتبات:

```bash
python -m venv .venv
```

التفعيل يختلف بحسب نظام التشغيل:

```bash
# Linux أو macOS
source .venv/bin/activate

# Windows PowerShell
.venv\Scripts\Activate.ps1
```

بعدها ثبّت الحزم داخل البيئة. لا تثبّت حزمًا من مصادر غير موثوقة، ولا تضع كلمات المرور أو مفاتيح الخدمات في مستودع عام.

## 13. البرمجة كائنية التوجّه

الصنف `class` يصف نوعًا من الكائنات. الكائن يجمع بيانات وسلوكًا:

```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        print(f"{self.name} يقول: هوهو!")

my_dog = Dog("لولو", 3)
print(my_dog.name)
my_dog.bark()
```

`__init__` تُستدعى عند إنشاء كائن، و`self` تشير إلى الكائن الحالي. مثال على الوراثة:

```python
class GuideDog(Dog):
    def guide(self):
        print(f"{self.name} يساعد صاحبه")

buddy = GuideDog("Buddy", 4)
buddy.bark()
buddy.guide()
```

لا تحتاج إلى استخدام الأصناف في كل برنامج؛ استخدمها عندما تجعل بنية البيانات والسلوك أوضح.

## 14. أدوات ومفاهيم مفيدة

### `enumerate` و`zip`

```python
names = ["سلمى", "آدم"]
for index, name in enumerate(names, start=1):
    print(index, name)

names = ["سلمى", "آدم"]
scores = [90, 85]
for name, score in zip(names, scores):
    print(name, score)
```

### المكررات والمولّدات

المولّد ينتج القيم عند الحاجة باستخدام `yield`، وهو مفيد عندما لا تريد تخزين كل النتائج مرة واحدة:

```python
def count_up_to(limit):
    number = 1
    while number <= limit:
        yield number
        number += 1

for value in count_up_to(3):
    print(value)
```

### اختبار بسيط

```python
def add(a, b):
    return a + b

assert add(2, 3) == 5
```

للمشاريع الأكبر تعلّم إطار الاختبارات المدمج `unittest` أو مكتبة اختبار موثوقة.

## 15. مشاريع تدريبية

### أ. آلة حاسبة بسيطة

```python
first = float(input("الرقم الأول: "))
operator = input("العملية (+، -، *، /): ")
second = float(input("الرقم الثاني: "))

if operator == "+":
    result = first + second
elif operator == "-":
    result = first - second
elif operator == "*":
    result = first * second
elif operator == "/":
    if second == 0:
        result = None
        print("لا يمكن القسمة على صفر")
    else:
        result = first / second
else:
    result = None
    print("عملية غير معروفة")

if result is not None:
    print("النتيجة:", result)
```

### ب. لعبة تخمين رقم

```python
import random

secret = random.randint(1, 10)
guess = None

while guess != secret:
    try:
        guess = int(input("خمّن رقمًا من 1 إلى 10: "))
    except ValueError:
        print("أدخل رقمًا صحيحًا")
        continue

    if guess < secret:
        print("أعلى قليلًا")
    elif guess > secret:
        print("أقل قليلًا")

print("أحسنت! خمنت الرقم")
```

### ج. قائمة مهام في الذاكرة

```python
tasks = []

while True:
    command = input("اكتب add أو list أو quit: ").strip().lower()

    if command == "add":
        tasks.append(input("المهمة: ").strip())
    elif command == "list":
        if not tasks:
            print("لا توجد مهام")
        for index, task in enumerate(tasks, start=1):
            print(f"{index}. {task}")
    elif command == "quit":
        break
    else:
        print("أمر غير معروف")
```

## 16. تمارين

1. أنشئ متغيّرين لرقمين واطبع مجموعهما ومتوسطهما.
2. اطلب عددًا، واطبع هل هو زوجي أم فردي باستخدام `%`.
3. اطبع الأعداد من 1 إلى 20 باستخدام حلقة، ثم اطبع مجموعها.
4. أنشئ قائمة أسماء واطبع كل اسم مع رقمه باستخدام `enumerate`.
5. اكتب دالة تستقبل قائمة أرقام وتعيد مجموعها.
6. اطلب من المستخدم رقمًا داخل `try` واطبع رسالة مناسبة إذا لم يكن الإدخال صحيحًا.

### حلول مقترحة لبعض التمارين

```python
# 2. زوجي أم فردي
number = int(input("أدخل عددًا: "))
if number % 2 == 0:
    print("زوجي")
else:
    print("فردي")

# 5. جمع عناصر قائمة
def sum_numbers(numbers):
    return sum(numbers)

print(sum_numbers([1, 2, 3]))
```

## نصائح للتعلّم

- اكتب الأمثلة وشغّلها بنفسك؛ القراءة وحدها لا تكفي.
- غيّر القيم وتوقّع الناتج قبل التشغيل.
- اقرأ رسالة الخطأ وحدد رقم السطر، ثم افحص أسماء المتغيّرات والمسافات والأنواع.
- قسّم المسألة إلى خطوات صغيرة واكتب أسماء واضحة.
- تعلّم أساسيات Git واختبارات البرامج عند بدء مشاريع أطول.
- بعد الأساسيات، اختر مجالًا واحدًا وطبّق مشروعًا صغيرًا فيه بدل محاولة تعلّم كل المكتبات دفعة واحدة.

## مسار مقترح بعد هذا الدليل

1. أعد كتابة المشاريع دون نسخ، ثم أضف ميزات إليها.
2. تعلّم قراءة وكتابة JSON، واستخدام `pathlib` للتعامل مع المسارات.
3. تعلّم الاختبارات، وتصحيح الأخطاء، وتنظيم المشروع إلى ملفات.
4. اختر تخصصًا: تطوير الويب، تحليل البيانات، الأتمتة، أو مجالًا آخر.

هذا الدليل نقطة انطلاق شاملة، وليس مرجعًا لكل مكتبات بايثون؛ فالمكتبات والمجالات واسعة وتتغير بحسب احتياج المشروع.
