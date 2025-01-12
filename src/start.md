## بـٰسم الله الرحمن الرحيم

في هذا الجزء، سنتعرف إن شاء الله على اللغة وكيف يمكنك كتابة برامجك بلغة `نظم`.

سوف نقوم بإنشاء ملف ويجب أن يكون بامتداد `.نظم`. في العادة يكون اسم هذا الملف `البداية.نظم`.

سيكون تعاملنا فقط مع دالة `البداية`، الدالة التي يبدأ منها تنفيذ البرنامج الخاص بك.

```nazm
دالة البداية(){
    /* هنا سيكون كود برنامجك */
}
```

دالة `البداية` هى الدالة التي يبدأ منها تنفيذ أي برنامج، في الحقيقة، أغلب لغات البرمجة لديها نفس المفهوم لدالة `البداية`، فكل برنامج له نقطة بداية يبدأ تنفيذ الأوامر منها.

### كتابة أول برنامج لك

إن أول برنامج لك سيكون عبارة عن إظهار رسالة للمستخدم، نص تلك الرسالة `"هذا أول برنامج لي بلغة نظم"`:

```nazm
دالة البداية(){
    اظهر_("هذا أول برنامج لي بلغة نظم")؛
}
```

لاحظ الأمر **`اظهر_`** وهو الذي سيقوم بإظهار الرسالة الموجودة بين القوسين.

لاحظ أيضاً وجود الفاصلة المنقوطة **`؛`** في آخر الأمر.

قم الآن بفتح شاشة تنفيذ الأوامر (Terminal) عند نفس مسار الملف، وقم بكتابة الأمر **`nazmc`** ثم اسم الملف **`البداية.نظم`**:

```shell
$ nazmc البداية.نظم
$ ./البداية
```

قُم بتنفيذ الأمر وسوف تلاحظ ظهور رسالة **`هذا أول برنامج لي بلغة نظم`** على الشاشة.

قُم الآن بتكرار الأمر **`اظهر_`** وقُم بإضافة رسالة أخرى، على سبيل المثال `"هذه رسالة أخرى"`:

```nazm
دالة البداية(){
    اظهر_("هذا أول برنامج لي بلغة نظم")؛
    اظهر_("هذه رسالة أخرى")؛
}
```

لاحظ مرةً أخرى وجود الفاصلة المنقوطة **`؛`** في آخر كل أمر. قُم الآن بتنفيذ البرنامج على شاشة التنفيذ باستخدام الأوامر السابقة:

```shell
$ nazmc البداية.نظم
$ ./البداية
```

وستلاحظ ظهور رسالة **`هذا أول برنامج لي بلغة نظم`** ثم تحتها رسالة **`هذه رسالة أخرى`**، هكذا:

```text, rtl
هذا أول برنامج لي بلغة نظم
هذه رسالة أخرى
```

### الفاصلة المنقوطة

تُستخدم الفاصلة المنقوطة في لغة `نظم` لإنهاء التعليمات. تعتبر الفاصلة المنقوطة علامة ضرورية لتحديد نهاية كل سطر من التعليمات.

إذا قُمنا بإزالة الفاصلة المنقوطة من السطر الأول في المثال السابق:

```nazm
دالة البداية(){
    اظهر_("هذا السطر بدون فاصلة منقوطة")
    اظهر_("هذا بفاصلة منقوطة")؛
}
```

فإن البرنامج لن يتنفذ، وسيقوم مترجم `نظم` بإظهار هذا الخطأ على الشاشة (لاحظ أنه يدلُّك على مكان الخطأ بالضبط):

<pre>
<div class="hljs" style="padding-right: 10px; padding-top: 17px;"><font color="#F14C4C"><b>خطأ</b></font><b>:</b> <b>يُتوقع فاصلة منقوطة `؛`، ولكن تم العثور على `اظهر_`</b>
<font color="#3B8EEA"><b> --&gt;</b></font> البداية.نظم:2:41
<font color="#3B8EEA"><b> </b></font> <font color="#3B8EEA"><b>|</b></font>
<font color="#3B8EEA"><b>2</b></font> <font color="#3B8EEA"><b>|</b></font>     اظهر_(&quot;هذا السطر بدون فاصلة منقوطة&quot;)
<font color="#3B8EEA"><b> </b></font> <font color="#3B8EEA"><b>|</b></font>                                         <font color="#F14C4C"><b>^قُم هنا بإضافة فاصلة منقوطة `؛`</b></font>
<font color="#3B8EEA"><b>3</b></font> <font color="#3B8EEA"><b>|</b></font>     اظهر_(&quot;هذا بفاصلة منقوطة&quot;)؛
<font color="#3B8EEA"><b> </b></font> <font color="#3B8EEA"><b>|</b></font>     <font color="#3B8EEA"><b>-----رمز غير متوقع</b></font>

</div>
</pre>

بالطبع يمكنك إهمال الفاصلة المنقوطة في حالة وحيدة، وهى التي سنناقشها إن شاء الله في باب [التحكم في التنفيذ](start/control-flow.md).

### المسافات

لاحظ أن المسافات والسطور الفارغة في الكود بين الرموز غير مؤثرة على الكود وليس كما في بعض اللغات الأخرى التي تعتمد على المسافات، فيمكنك في `نظم` كتابة الكود بهذا الشكل:

```nazm
دالة البداية    (        )    {
    اظهر_     (
         "هذا الرسالة الأولى"
    )   ؛


    اظهر_("وهذه الرسالة الثانية"  ) ؛
}
```

> [!إرشاد]
> إضافة المسافات الكبيرة كما في المثال السابق قد يجعل شكل الكود أقل جمالاً من ناحية القراءة، أو حتى صعباً في القراءة، لذا يجب أن تراعي هذا. من الأفضل استخدام المسافات بطريقة تجعل الكود واضحًا ومنظمًا.

### اظهر أم اظهر\_

في لغة `نظم`، يوجد خياران لعرض الرسائل على الشاشة:

1. **`اظهر`** بدون شَرطة سُفلية **`_`**:

   هذا الأمر يقوم بإظهار الرسالة بدون الانتقال إلى سطر جديد بعد الرسالة:

   ```nazm
   دالة البداية(){
       اظهر("هذه الرسالة الأولى")؛
       اظهر("وهذه الرسالة الثانية")؛
   }
   ```

   لاحظ أن الرسالتين تظهران في نفس السطر بدون أي مسافة بينهما عند التنفيذ:

   ```text, rtl
   هذه الرسالة الأولىوهذه الرسالة الثانية
   ```

2. **`اظهر_`** بشَرطة سُفلية **`_`**:

   هذا الأمر يقوم بإظهار الرسالة ثم ينتقل إلى سطر جديد:

   ```nazm
   دالة البداية(){
       اظهر("هذه الرسالة الأولى")؛
       اظهر("وهذه الرسالة الثانية")؛
   }
   ```

   لاحظ هنا أن الرسالة الثانية ظهرت في سطر جديد بعد الرسالة الأولى:

   ```text ,rtl
   هذه الرسالة الأولى
   وهذه الرسالة الثانية
   ```
