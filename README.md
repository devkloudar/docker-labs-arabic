# 🐳 docker-labs-arabic  
**مختبرات Docker بالعربي**  
من تقديم: [devKloud بالعربي](https://github.com/devkloudar)  
@devkloud-arabic  

---

## 🎯 الفكرة

هذا المستودع مخصص لمجموعة من **المختبرات الأسبوعية (Docker Labs)** التي أقدّمها على قناة **devKloud بالعربي** في يوتيوب.  
كل أسبوع سيتم إنشاء **تجربة جديدة باستخدام Docker** لشرح أداة أو تقنية أو فكرة عملية في مجال DevOps و Cloud.

---

## 🧩 الهدف من المشروع

- تبسيط مفاهيم Docker وتوضيحها للمبتدئين والمتوسطين.  
- توفير أمثلة عملية يمكن تشغيلها محليًا بسهولة.  
- تعليم بناء بيئات وخدمات حقيقية باستخدام Docker و Docker Compose.  
- ربط المختبرات بفيديوهات تعليمية على يوتيوب لشرح كل خطوة بالتفصيل.

---

## 🗂️ هيكل المستودع

```
docker-labs-arabic/
├── 01-projectname/        # أول مختبر (مثلاً Nginx Proxy + Let's Encrypt)
├── 02-projectname/        # مختبر الأسبوع التالي
├── 03-projectname/        # مختبر آخر
└── README.md     # هذا الملف
```

كل مجلد يمثل **مختبرًا مستقلًا** يحتوي على:
- `docker-compose.yml`
- تعليمات الاستخدام في ملف `README.md`
- ملفات إضافية (config, env, data…)

---

## 🧠 المواضيع المقترحة

بعض المختبرات التي سيتم العمل عليها:

| الرقم | العنوان | الوصف |
|--------|----------|-------|
| 01 | استضافة Excalidraw باستخدام Docker | شرح Nginx Proxy + Let's Encrypt + تطبيق Excalidraw |

---

## 🚀 كيفية الاستخدام

1. **استنسخ المستودع:**
   ```bash
   git clone https://github.com/devkloudar/docker-labs-arabic.git
   cd docker-labs-arabic
   ```

2. **ادخل إلى المختبر الذي تريده:**
   ```bash
   cd 01-excalidraw-nginx
   ```

3. **شغّل التجربة:**
   ```bash
   docker compose up -d
   ```

4. **اتبع التعليمات في ملف README داخل كل مختبر.**

---

## 🎥 القناة التعليمية

يمكنك متابعة جميع المختبرات بالفيديو عبر قناة  
📺 [devKloud بالعربي على يوتيوب](https://www.youtube.com/@devkloud-arabic)  

كل أسبوع سيتم رفع **فيديو جديد + مختبر عملي جديد**.

---

## 🤝 المساهمة

هل ترغب في اقتراح مختبر جديد أو تحسين أحد المشاريع؟  
مرحبًا بك في المساهمة عن طريق:

- **فتح Issue** لاقتراح فكرة  
- **إرسال Pull Request** لإضافة مختبر جديد أو تحسين أحد الملفات

---

## 🧑‍💻 الصيانة

**devKloud بالعربي**  
GitHub / YouTube / Twitter: [@devkloud-arabic](https://youtube.com/@devkloud-arabic)
GitHub: [@devkloud-arabic](https://github.com/devkloud-arabic)

---

## 📜 الترخيص

جميع المحتويات مفتوحة المصدر تحت رخصة **MIT License**.  
يمكنك نسخها وتعديلها لأغراض تعليمية.

---

> 🌟 لا تنسَ دعم المشروع بنجمة ⭐ على GitHub إذا أعجبك المحتوى!

