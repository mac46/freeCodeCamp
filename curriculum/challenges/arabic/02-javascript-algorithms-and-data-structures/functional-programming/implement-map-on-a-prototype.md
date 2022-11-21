---
id: 587d7b8f367417b2b2512b62
title: تنفيذ دالة map على Prototype
challengeType: 1
forumTopicId: 301230
dashedName: implement-map-on-a-prototype
---

# --description--

كما رأيتم من تطبيق `Array.prototype.map()`، أو `map()` من قبل، فدالة `map` ترجع array من نفس طول الـ array التي استُدعت الدالة عليها. وهي إلى ذلك لا تغير القائمة (array) الأصلية، مادام أن وظيفتها لإعادة التفعيل (callback function) لا تفعل ذلك.

بمعنى آخر، `map` هي وظيفة خالصة (pure function)، ومخرجها يعتمد فقط على مدخلاتها. إضافةً إلى ذلك، فإنها تأخذ وظيفة أخرى كحجة (argument) لها.

قد تتعلم الكثير عن دالة `map` إذا قمت بتنفيذ الإصدار الخاص بك منها. من المستحسن أن تستخدم حلقات `for` التكرارية أو `Array.prototype.forEach()`.

# --instructions--

اكتب `Array.prototype.myMap()` الخاص بك، والذي يجب أن يتصرف مثل `Array.prototype.map()`. يجب ألا تستخدم دالة `map` المدمجة. يمكن الوصول إلى مثيل (instance) `Array` في دالة `myMap` باستخدام `this`.

# --hints--

يجب أن يساوي `[23, 65, 98, 5, 13].myMap(item => item * 2)` قيمة `[46, 130, 196, 10, 26]`.

```js
const _test_s = [46, 130, 196, 10, 13];
const _callback = item => item * 2;
assert(JSON.stringify(_test_s.map(_callback)) === JSON.stringify(_test_s.myMap(_callback)));
```

يجب ألا يستخدم الكود الخاص بك دالة `map`.

```js
assert(!code.match(/\.?[\s\S]*?map/g));
```

# --seed--

## --seed-contents--

```js
Array.prototype.myMap = function(callback) {
  const newArray = [];
  // Only change code below this line

  // Only change code above this line
  return newArray;
};
```

# --solutions--

```js
Array.prototype.myMap = function(callback) {
  const newArray = [];
  for (const elem of this) {
    newArray.push(callback(elem));
  }
  return newArray;
};

// Test case
const s = [23, 65, 98, 5];
const doubled_s = s.myMap(item => item * 2);
```