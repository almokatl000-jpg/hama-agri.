<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>كلية الهندسة الزراعية - جامعة حماة</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@600;700;800&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        /* --- المتغيرات اللونية --- */
        :root {
            --primary-green: #2E7D32;
            --dark-green: #1B5E20;
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --text-main: #2c3e50;
            --accent-blue: #1565C0;
        }

        body {
            font-family: 'Tajawal', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            margin: 0; padding: 0; line-height: 1.8;
        }

        h1, h2, h3, button { font-family: 'Cairo', sans-serif; }

        /* --- الرأس (Header) --- */
        header {
            background: linear-gradient(135deg, var(--primary-green), var(--dark-green));
            color: white;
            padding: 15px 10px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
            position: sticky; top: 0; z-index: 100;
        }

        .header-container {
            max-width: 1000px; margin: 0 auto;
            display: flex; align-items: center; justify-content: space-between;
        }

        .header-text { text-align: center; flex-grow: 1; padding: 0 10px; }
        header h1 { font-size: 1.1rem; margin: 0; font-weight: 800; }
        header p { margin: 2px 0 0; font-size: 0.8rem; opacity: 0.9; }

        .logo {
            width: 65px; height: 65px;
            background-color: white; border-radius: 50%; padding: 3px;
            object-fit: contain; box-shadow: 0 2px 8px rgba(0,0,0,0.2);
        }

        /* --- الحاوية --- */
        .container { max-width: 900px; margin: 25px auto; padding: 0 15px; }

        /* --- العناوين الجانبية --- */
        .section-header {
            display: flex; align-items: center; margin: 35px 0 20px 0;
            border-bottom: 2px solid #e0e0e0; padding-bottom: 10px;
        }
        .section-icon {
            background-color: var(--primary-green); color: white;
            width: 35px; height: 35px; border-radius: 8px;
            display: flex; align-items: center; justify-content: center;
            font-size: 1.1rem; margin-left: 15px;
        }
        .section-header h2 { margin: 0; color: var(--dark-green); font-size: 1.4rem; }

        /* --- البطاقات العامة --- */
        .card {
            background-color: var(--card-bg); border-radius: 12px;
            padding: 20px; box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            margin-bottom: 20px; border: 1px solid #eee;
        }

        /* --- عارض الصور المتحرك --- */
        .slideshow-container {
            width: 100%;
            overflow: hidden;
            border-radius: 12px;
            margin-bottom: 20px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
            position: relative;
        }
        .slides-wrapper {
            width: 400%; /* 4 صور */
            display: flex;
            animation: slideAnimation 20s infinite; /* مدة العرض */
        }
        .slide-image {
            width: 25%;
            height: auto;
            max-height: 400px;
            object-fit: cover; /* لضمان ملء الصورة للمساحة بشكل جميل */
        }
        
        /* حركة الانزلاق */
        @keyframes slideAnimation {
            0%, 20% { margin-right: 0; }
            25%, 45% { margin-right: -100%; }
            50%, 70% { margin-right: -200%; }
            75%, 95% { margin-right: -300%; }
            100% { margin-right: 0; }
        }

        /* --- جدول السنوات --- */
        .years-table { width: 100%; border-collapse: collapse; margin-top: 10px; }
        .years-table tr { border-bottom: 1px solid #eee; }
        .years-table td { padding: 12px; font-weight: 600; }
        .years-table td:first-child { color: var(--primary-green); width: 40%; }

        /* --- القوائم المنسدلة (Accordion) --- */
        .accordion-btn {
            background-color: white; color: var(--dark-green);
            cursor: pointer; padding: 18px; width: 100%; text-align: right;
            border: none; outline: none; transition: 0.3s;
            font-weight: 700; font-size: 1.1rem; border-radius: 10px;
            margin-bottom: 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.05);
            display: flex; justify-content: space-between; align-items: center;
            border-right: 4px solid var(--primary-green);
        }
        .active, .accordion-btn:hover { background-color: var(--primary-green); color: white; }
        .accordion-btn:after { content: '\002B'; font-size: 20px; font-weight: bold; }
        .active:after { content: "\2212"; }

        .panel {
            padding: 0 18px; background-color: white; max-height: 0;
            overflow: hidden; transition: max-height 0.3s ease-out;
            margin-bottom: 15px; border-radius: 0 0 10px 10px;
            border-left: 1px solid #ddd; border-right: 1px solid #ddd; border-bottom: 1px solid #ddd;
        }
        .panel-content { padding: 20px 5px; }
        .job-title { color: var(--primary-green); font-weight: bold; display: block; margin-top: 15px; border-bottom: 1px dashed #ccc; padding-bottom: 5px; }
        .dept-list { margin: 10px 0; padding-right: 20px; }
        .dept-list li { font-size: 0.95rem; margin-bottom: 5px; color: #555; }

        /* --- صندوق المستقبل (AI) --- */
        .ai-box {
            background: linear-gradient(45deg, var(--accent-blue), #0D47A1); color: white;
            padding: 20px; border-radius: 10px; margin-top: 20px; text-align: center;
            position: relative; overflow: hidden;
        }
        .ai-box::after {
            content: "AI"; position: absolute; left: -10px; bottom: -10px;
            font-size: 80px; opacity: 0.1; font-weight: bold;
        }

        /* --- شبكة المخابر --- */
        .labs-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
        }
        .lab-card {
            background: white; border: 1px solid #eee; border-radius: 10px;
            padding: 15px; box-shadow: 0 3px 6px rgba(0,0,0,0.04);
            transition: transform 0.2s;
        }
        .lab-card:hover { transform: translateY(-5px); border-color: var(--primary-green); }
        .lab-header { display: flex; align-items: center; margin-bottom: 10px; border-bottom: 2px solid #f0f0f0; padding-bottom: 8px; }
        .lab-icon { font-size: 1.5rem; margin-left: 10px; }
        .lab-title { font-weight: 700; color: var(--dark-green); font-size: 1rem; }
        .lab-desc { font-size: 0.85rem; color: #666; margin: 0; line-height: 1.6; }

        /* --- الفوتر والروابط --- */
        footer { text-align: center; padding: 40px 20px; background-color: var(--text-main); color: #ddd; margin-top: 50px; font-size: 0.9rem; }
        .footer-links { margin-bottom: 25px; display: flex; justify-content: center; gap: 15px; flex-wrap: wrap; }
        .footer-links a { 
            color: white; text-decoration: none; background: rgba(255,255,255,0.1); 
            padding: 10px 20px; border-radius: 30px; transition: 0.3s; 
            border: 1px solid rgba(255,255,255,0.2); font-weight: bold; font-size: 0.9rem;
            display: flex; align-items: center; gap: 8px;
        }
        .footer-links a:hover { background: var(--primary-green); border-color: var(--primary-green); transform: translateY(-3px); }

        @media (max-width: 600px) {
            .header-container { justify-content: space-between; }
            .logo { width: 50px; height: 50px; }
            .years-table td { display: block; width: 100%; padding: 5px 12px; }
            .years-table tr { border-bottom: 1px solid #eee; padding: 10px 0; display: block; }
            .footer-links { flex-direction: column; align-items: center; }
            .footer-links a { width: 80%; justify-content: center; }
            .slide-image { max-height: 250px; }
        }
    </style>
</head>
<body>

    <header>
        <div class="header-container">
            <img src="https://i.ibb.co/39gKpwDP/Picsart-25-12-28-01-31-29-698.png" alt="شعار الجامعة" class="logo">
            
            <div class="header-text">
                <h1>جامعة حماة - كلية الهندسة الزراعية</h1>
                <p>نحو تميز أكاديمي وتنمية مستدامة</p>
            </div>

            <img src="https://i.ibb.co/b5HLTRcS/138-20251223163427.png" alt="شعار الكلية" class="logo">
        </div>
    </header>

    <div class="container">

        <div class="section-header">
            <div class="section-icon">🏛️</div>
            <h2>التعريف بالكلية</h2>
        </div>
        <div class="card">
            
            <div class="slideshow-container">
                <div class="slides-wrapper">
                    <img src="https://i.ibb.co/wNczP4qL/Untitled28-20251228081306.png" class="slide-image" alt="صورة للكلية 1">
                    <img src="https://i.ibb.co/wFz8r0HD/New-Picture-300x258.png" class="slide-image" alt="صورة للكلية 2">
                    <img src="https://i.ibb.co/s9v9NYqr/Untitled28-20251228081127.png" class="slide-image" alt="صورة للكلية 3">
                    <img src="https://i.ibb.co/nTBm308/Untitled28-20251228081115.png" class="slide-image" alt="صورة للكلية 4">
                </div>
            </div>

            <p style="margin-top: 20px; line-height: 1.9;">
                تأسست كلية الهندسة الزراعية بجامعة حماة عام 2011 لإعداد متخصصين ودعم القطاع الزراعي عبر بيئة بحثية متطورة.
                <br><br>
                وهي <strong>كلية هندسية تطبيقية بامتياز</strong>، تخرّج مهندساً قادراً على حل مشاكل القطاع الزراعي باستخدام الأدوات الهندسية، وتجمع بين الشغف بالهندسة وحب الطبيعة.
            </p>
        </div>

        <div class="section-header">
            <div class="section-icon">🎯</div>
            <h2>الأهــــداف</h2>
        </div>
        <div class="card">
            <ul style="padding-right: 20px; color: #444;">
                <li>إعداد خريجين متخصصين لتطوير واستثمار القطاع الزراعي.</li>
                <li>توفير برامج دراسية حديثة تواكب التطور العلمي.</li>
                <li>مشاركة خبرات الهيئة التدريسية لخدمة المجتمع الزراعي.</li>
                <li>تحقيق التميز الأكاديمي لتكون مؤسسة رائدة إقليمياً.</li>
            </ul>
        </div>

        <div class="section-header">
            <div class="section-icon">📚</div>
            <h2>نظام الدراسة</h2>
        </div>
        <div class="card">
            <p>مدة الدراسة <strong>خمس سنوات</strong>، ويبدأ التخصص بعد السنة الثالثة.</p>
            <table class="years-table">
                <tr><td>السنة الأولى</td><td>14 مادة</td></tr>
                <tr><td>السنة الثانية</td><td>14 مادة</td></tr>
                <tr><td>السنة الثالثة</td><td>12 مادة</td></tr>
                <tr><td>الرابعة والخامسة</td><td>12 مادة (حسب التخصص)</td></tr>
            </table>
        </div>

        <div class="section-header">
            <div class="section-icon">🎓</div>
            <h2>التخصصات (اضغط للتفاصيل)</h2>
        </div>

        <button class="accordion-btn">🌿 قسم الإنتاج النباتي</button>
        <div class="panel">
            <div class="panel-content">
                <p>يهتم بزراعة المحاصيل الحقلية والأشجار المثمرة والخضروات وتحسينها وراثياً.</p>
                <span class="job-title">📚 المواد الدراسية:</span>
                <ul class="dept-list"><li>المحاصيل الحقلية</li><li>البساتين والفاكهة</li><li>الزراعة المحمية</li><li>أمراض النبات</li></ul>
                <span class="job-title">💼 مجالات العمل:</span>
                <ul class="dept-list"><li>إدارة المزارع والمشاتل</li><li>شركات الأسمدة والبذور</li><li>مراكز البحوث</li></ul>
            </div>
        </div>

        <button class="accordion-btn">🐄 قسم الإنتاج الحيواني</button>
        <div class="panel">
            <div class="panel-content">
                <p>تربية ورعاية الحيوانات لإنتاج الغذاء (لحوم، حليب، بيض) بكفاءة عالية.</p>
                <span class="job-title">📚 المواد الدراسية:</span>
                <ul class="dept-list"><li>تغذية الحيوان</li><li>تربية الدواجن</li><li>إنتاج الأبقار والأغنام</li><li>التحسين الوراثي</li></ul>
                <span class="job-title">💼 مجالات العمل:</span>
                <ul class="dept-list"><li>مداجن ومزارع الأبقار</li><li>معامل الأعلاف</li><li>الاستزراع السمكي</li></ul>
            </div>
        </div>

        <button class="accordion-btn">📊 قسم الاقتصاد الزراعي</button>
        <div class="panel">
            <div class="panel-content">
                <p>إدارة المشاريع الزراعية لتحقيق أعلى ربح وجدوى اقتصادية.</p>
                <span class="job-title">📚 المواد الدراسية:</span>
                <ul class="dept-list"><li>إدارة المزارع</li><li>التسويق الزراعي</li><li>دراسة الجدوى</li><li>الإحصاء</li></ul>
                <span class="job-title">💼 مجالات العمل:</span>
                <ul class="dept-list"><li>البنوك الزراعية</li><li>المنظمات الدولية (FAO)</li><li>إدارة الشركات الزراعية</li></ul>
            </div>
        </div>

        <button class="accordion-btn">🍞 قسم علوم الأغذية</button>
        <div class="panel">
            <div class="panel-content">
                <p>تحويل المواد الزراعية الخام إلى منتجات غذائية آمنة وصحية.</p>
                <span class="job-title">📚 المواد الدراسية:</span>
                <ul class="dept-list"><li>تكنولوجيا الألبان والحبوب</li><li>حفظ وتصنيع الأغذية</li><li>الأحياء الدقيقة</li></ul>
                <span class="job-title">💼 مجالات العمل:</span>
                <ul class="dept-list"><li>مصانع الأغذية (جودة وإنتاج)</li><li>مخابر الرقابة الغذائية</li><li>المطاحن</li></ul>
            </div>
        </div>

        <button class="accordion-btn">☀️ قسم الموارد والطاقات</button>
        <div class="panel">
            <div class="panel-content">
                <p>إدارة المياه والتربة واستخدام الطاقة النظيفة في الزراعة.</p>
                <span class="job-title">📚 المواد الدراسية:</span>
                <ul class="dept-list"><li>هندسة الري</li><li>علوم التربة</li><li>الطاقة الشمسية</li><li>الأرصاد الجوية</li></ul>
                <span class="job-title">💼 مجالات العمل:</span>
                <ul class="dept-list"><li>شركات الطاقة الشمسية</li><li>شبكات الري</li><li>استصلاح الأراضي</li></ul>
            </div>
        </div>

        <div class="ai-box">
            <h3 style="margin: 0 0 10px 0;">🚀 رؤية نحو المستقبل</h3>
            <p style="font-size: 0.95rem; margin: 0;">
                يتم العمل على إضافة تخصص جديد وفريد: 
                <br><strong>"ربط الهندسة الزراعية بالذكاء الاصطناعي"</strong>
                <br>هذا التخصص موجود حالياً في الصين فقط، ونسعى لنكون الرواد فيه.
            </p>
        </div>

        <div class="section-header">
            <div class="section-icon">🔬</div>
            <h2>المخابر العلمية</h2>
        </div>
        
        <div class="labs-grid">
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">⚗️</span><span class="lab-title">مخبر الكيمياء</span></div><p class="lab-desc">إجراء التحاليل الكيميائية للمواد الزراعية، وتقدير العناصر الغذائية في العينات النباتية والأسمدة.</p></div>
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">🌱</span><span class="lab-title">مخبر التربة والنبات</span></div><p class="lab-desc">تحليل عينات التربة لتحديد خصوبتها، وتشخيص الأمراض النباتية الفطرية والبكتيرية.</p></div>
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">🍎</span><span class="lab-title">مخبر علوم الأغذية</span></div><p class="lab-desc">فحص جودة المنتجات الغذائية (ألبان، معلبات) والتأكد من سلامتها وخلوها من الملوثات.</p></div>
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">🦗</span><span class="lab-title">مخبر الحشرات والوقاية</span></div><p class="lab-desc">تصنيف الحشرات الضارة والنافعة، ودراسة طرق المكافحة الحيوية والكيميائية للآفات.</p></div>
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">🐄</span><span class="lab-title">مخبر الإنتاج الحيواني</span></div><p class="lab-desc">تحليل الأعلاف وقيمتها الغذائية، وإجراء الدراسات المتعلقة بفسيولوجيا الحيوان.</p></div>
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">💻</span><span class="lab-title">مخبر الحاسوب</span></div><p class="lab-desc">تطبيقات البرمجة والإحصاء الحيوي في الزراعة، وتصميم التجارب وتحليل البيانات البحثية.</p></div>
            <div class="lab-card"><div class="lab-header"><span class="lab-icon">🎓</span><span class="lab-title">مخبر الدراسات العليا</span></div><p class="lab-desc">مجهز بأجهزة متطورة لطلاب الماجستير والدكتوراه لإجراء الأبحاث العلمية الدقيقة.</p></div>
        </div>

    </div>

    <footer>
        <div class="footer-links">
            <a href="https://www.facebook.com/share/1Do4ykqe9X/" target="_blank">🌐 الصفحة الرسمية للكلية</a>
            <a href="https://www.facebook.com/share/1DHWFss1Wr/" target="_blank">📢 الهيئة الطلابية</a>
        </div>
        <p>جميع الحقوق محفوظة &copy; 2025 - جامعة حماة</p>
        <p>كلية الهندسة الزراعية - سلمية</p>
    </footer>

    <script>
        var acc = document.getElementsByClassName("accordion-btn");
        for (var i = 0; i < acc.length; i++) {
            acc[i].addEventListener("click", function() {
                this.classList.toggle("active");
                var panel = this.nextElementSibling;
                if (panel.style.maxHeight) { panel.style.maxHeight = null; } 
                else { panel.style.maxHeight = panel.scrollHeight + "px"; } 
            });
        }
    </script>

</body>
</html>
