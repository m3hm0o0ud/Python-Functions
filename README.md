# Python-Functions

### الدوال في بايثون (Python Functions)

الدوال في بايثون هي كتلة من التعليمات البرمجية التي تنفذ فقط عندما يتم استدعاؤها. تساعد الدوال في تنظيم الكود، وإعادة استخدامه، وتقليل التكرار في البرامج.

### تمرير البيانات إلى الدالة
يمكن تمرير البيانات إلى الدالة كمعطيات (Parameters)، ويمكن أن تعيد الدالة بيانات كنتيجة بعد معالجتها.

### إنشاء الدالة في بايثون
يتم تعريف الدوال في بايثون باستخدام الكلمة المفتاحية `def` متبوعة باسم الدالة وأقواس تحتوي على المعطيات (إن وجدت).

**مثال:**
```python
def my_function():
    print("Hello from a function")
```

### استدعاء الدالة
لا يتم تنفيذ الدالة حتى يتم استدعاؤها. يتم استدعاء الدالة بكتابة اسم الدالة متبوعًا بالأقواس:

**مثال:**
```python
my_function()
```

### المعطيات (Arguments)
يمكن تمرير معلومات إلى الدوال كمعطيات (Arguments). يتم تحديد المعطيات بعد اسم الدالة داخل الأقواس. يمكنك إضافة عدد غير محدد من المعطيات بفصلها بفواصل.

**مثال:**
```python
def my_function(fname):
    print(fname + " Refsnes")

my_function("Emil")
my_function("Tobias")
my_function("Linus")
```

### الفرق بين المعطيات (Arguments) والوسائط (Parameters)
- **المعطيات (Arguments):** هي القيم التي يتم إرسالها إلى الدالة عند استدعائها.
- **الوسائط (Parameters):** هي المتغيرات المعرفة داخل تعريف الدالة والتي تستقبل المعطيات.

### عدد المعطيات
يجب استدعاء الدالة بعدد المعطيات الصحيحة كما هو متوقع في تعريف الدالة. على سبيل المثال، إذا كانت الدالة تتوقع معطياتين، فيجب عليك تمرير معطياتين فقط.

**مثال:**
```python
def my_function(fname, lname):
    print(fname + " " + lname)

my_function("Emil", "Refsnes")
```

إذا حاولت استدعاء الدالة بعدد خاطئ من المعطيات، ستحدث خطأ.

### معطيات عشوائية (*args)
إذا لم تكن تعلم مسبقاً عدد المعطيات التي سيتم تمريرها إلى الدالة، يمكنك إضافة `*` قبل اسم الوسيط لجعل الدالة تستقبل عدد غير محدد من المعطيات على شكل tuple.

**مثال:**
```python
def my_function(*kids):
    print("The youngest child is " + kids[2])

my_function("Emil", "Tobias", "Linus")
```

### معطيات مسماة (Keyword Arguments)
يمكن أيضاً تمرير المعطيات باستخدام الصيغة `key = value`. في هذه الحالة، لا يهم ترتيب المعطيات.

**مثال:**
```python
def my_function(child3, child2, child1):
    print("The youngest child is " + child3)

my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")
```

### معطيات مسماة عشوائية (**kwargs)
إذا لم تكن تعرف عدد المعطيات المسماة التي سيتم تمريرها، يمكنك إضافة `**` قبل اسم الوسيط لجعل الدالة تستقبل هذه المعطيات على شكل قاموس (dictionary).

**مثال:**
```python
def my_function(**kid):
    print("His last name is " + kid["lname"])

my_function(fname = "Tobias", lname = "Refsnes")
```

### قيمة افتراضية للمعطيات
يمكنك تحديد قيمة افتراضية للوسيط. إذا لم يتم تمرير معطى عند استدعاء الدالة، سيتم استخدام القيمة الافتراضية.

**مثال:**
```python
def my_function(country = "Norway"):
    print("I am from " + country)

my_function("Sweden")
my_function("India")
my_function()
```

### تمرير قائمة كمعطى
يمكنك تمرير أي نوع من البيانات إلى الدالة كمعطى، مثل النصوص، الأرقام، القوائم، والقواميس.

**مثال:**
```python
def my_function(food):
    for x in food:
        print(x)

fruits = ["apple", "banana", "cherry"]
my_function(fruits)
```

### إرجاع القيم (Return)
لإرجاع قيمة من الدالة، يتم استخدام الكلمة المفتاحية `return`. هذه القيمة يمكن استخدامها خارج الدالة.

**مثال:**
```python
def my_function(x):
    return 5 * x

print(my_function(3))
```

### استخدام `pass`
إذا كانت لديك دالة فارغة وتحتاج إلى تفادي حدوث خطأ، يمكنك استخدام الكلمة المفتاحية `pass`.

**مثال:**
```python
def my_function():
    pass
```

### المعطيات الموضعية فقط (Positional-Only Arguments)
يمكنك تحديد أن الدالة تستقبل فقط معطيات موضعية بإضافة `/` بعد المعطيات.

**مثال:**
```python
def my_function(x, /):
    print(x)

my_function(3)
```

### المعطيات المسماة فقط (Keyword-Only Arguments)
يمكنك تحديد أن الدالة تستقبل فقط معطيات مسماة بإضافة `*` قبل المعطيات.

**مثال:**
```python
def my_function(*, x):
    print(x)

my_function(x = 3)
```

### الجمع بين المعطيات الموضعية والمسماة
يمكنك الجمع بين المعطيات الموضعية والمسماة في نفس الدالة. المعطيات قبل `/` تعتبر موضعية، والمعطيات بعد `*` تعتبر مسماة.

**مثال:**
```python
def my_function(a, b, /, *, c, d):
    print(a + b + c + d)

my_function(5, 6, c = 7, d = 8)
```

### التكرار (Recursion)
بايثون تدعم التكرار (recursion)، حيث يمكن للدالة استدعاء نفسها. هذا الأسلوب مفيد للتعامل مع البيانات المتكررة أو الوصول إلى نتيجة عبر عمليات متتابعة.

**مثال:**
```python
def tri_recursion(k):
    if k > 0:
        result = k + tri_recursion(k - 1)
        print(result)
    else:
        result = 0
    return result

print("\n\nRecursion Example Results")
tri_recursion(6)
```

التكرار مفيد لكنه يتطلب الحذر، حيث أن الخطأ في كتابة التكرار قد يؤدي إلى نفاد الذاكرة أو استهلاك المعالج.
