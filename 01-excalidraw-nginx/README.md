
# 🧠 استضافة Excalidraw محليًا باستخدام Nginx Proxy و Let's Encrypt  
**تمت الصيانة بواسطة [devKloud بالعربي](https://github.com/devkloudar)**  


يسمح لك هذا الإعداد باستضافة [Excalidraw](https://github.com/excalidraw/excalidraw) على الخادم الخاص بك باستخدام Docker Compose.  
يقوم تلقائيًا بإعداد **الوكيل العكسي (Reverse Proxy)**، وشهادات **HTTPS (Let's Encrypt)**، وتوجيه النطاقات باستخدام  
[`nginx-proxy`](https://github.com/nginx-proxy/nginx-proxy) و [`acme-companion`](https://github.com/nginx-proxy/acme-companion).

---

## 🧩 نظرة عامة على المعمارية

| الخدمة | الوصف |
|----------|-------|
| **nginx-proxy** | يقوم بتوجيه حركة المرور تلقائيًا إلى الحاويات بناءً على اسم النطاق (VIRTUAL_HOST). |
| **acme-companion** | يصدر ويجدد شهادات Let's Encrypt تلقائيًا. |
| **draw (Excalidraw)** | تطبيق Excalidraw نفسه. |

تتشارك جميع الحاويات في شبكة Docker واحدة باسم `proxy`.

---

## ⚙️ المتطلبات المسبقة

قبل التشغيل، تأكد من توفر التالي:

- 🐳 **Docker** و **Docker Compose** مثبتان على الخادم  
- 🌍 اسم نطاق صالح (مثل: `draw.example.com`)  
- 📬 عنوان بريد إلكتروني صالح لإشعارات Let's Encrypt  
- 🔓 فتح المنفذين **80** و **443** على الخادم

---

## 📁 هيكل المجلدات

```
excalidraw/
├── docker-compose.yml
└── data/
    ├── certs/        # الشهادات (تدار تلقائيًا)
    ├── vhost/        # إعدادات Nginx المخصصة (اختياري)
    ├── html/         # مجلد HTML الافتراضي
    └── acme/         # بيانات ACME للتوثيق
```

سيتم إنشاء جميع المجلدات تلقائيًا عند تشغيل الحاويات.

---

## 🚀 كيفية التشغيل

1. **استنساخ المشروع أو نسخ الملفات:**
   ```bash
   git clone https://github.com/devkloudar/docker-labs-arabic.git
   cd 01-excalidraw-nginx
   ```

2. **تعديل المتغيرات في ملف `docker-compose.yml`:**  
   - استبدل `example.com` باسم نطاقك.  
   - غيّر `info@example.com` إلى بريدك الإلكتروني.

   مثال:
   ```yaml
   environment:
     - VIRTUAL_HOST=draw.mydomain.com
     - LETSENCRYPT_HOST=draw.mydomain.com
     - LETSENCRYPT_EMAIL=me@mydomain.com
   ```

3. **تشغيل الحاويات:**
   ```bash
   docker compose up -d
   ```

4. **الوصول إلى التطبيق:**  
   افتح المتصفح وانتقل إلى 👉 **https://draw.mydomain.com**

---

## 🧰 أوامر مفيدة

| الإجراء | الأمر |
|---------|--------|
| عرض السجلات | `docker compose logs -f` |
| إعادة التشغيل | `docker compose restart` |
| إيقاف الحاويات | `docker compose down` |
| تجديد الشهادات يدويًا | `docker exec nginx-proxy-acme acme.sh --renew-all --force` |

---

## 🔐 ملاحظات حول HTTPS

- يتم إصدار وتجديد الشهادات **تلقائيًا** عبر `acme-companion`.  
- يتم التجديد التلقائي كل ~60 يومًا.  
- يمكنك التجديد يدويًا بالأمر الموضح أعلاه.

---

## 🧹 تنظيف النظام

لإزالة جميع الحاويات والملفات:
```bash
docker compose down -v
```

---

## ❤️ تمت الصيانة بواسطة

**devKloud بالعربي**  
GitHub: [@devkloudar](https://github.com/devkloudar)
Youtube: [@devkloud-arabic](https://youtube.com/devkloud-arabic)
