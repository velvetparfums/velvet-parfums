<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VELVET PARFUMS | عطور فيلقيت</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-color: #f9f7f2;
            --card-bg: #ffffff;
            --accent-gold: #786e4f;
            --accent-gold-light: #9e926c;
            --text-dark: #2c2a29;
            --text-muted: #66625c;
            --border-color: #e8e4dc;
            --shadow: 0 10px 30px rgba(0,0,0,0.04);
            --danger-color: #c0392b;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Tajawal', sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-dark);
            line-height: 1.6;
            padding-bottom: 90px;
        }

        header {
            background-color: var(--card-bg);
            text-align: center;
            padding: 25px 20px;
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 15px rgba(0,0,0,0.02);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .header-title-container {
            margin: 0 auto;
            text-align: center;
        }

        .logo-svg {
            width: 55px;
            height: 55px;
            margin-bottom: 5px;
        }

        .brand-title {
            font-family: 'Cinzel', serif;
            font-size: 20px;
            font-weight: 700;
            letter-spacing: 2px;
            color: var(--accent-gold);
        }

        .brand-subtitle {
            font-family: 'Cinzel', serif;
            font-size: 10px;
            letter-spacing: 2px;
            color: var(--text-muted);
            text-transform: uppercase;
        }

        .btn-admin-toggle {
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            padding: 8px 14px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 13px;
            color: var(--accent-gold);
            font-weight: bold;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 20px;
        }

        /* لوحة التحكم للإضافة */
        .admin-banner {
            display: none;
            background: #ffffff;
            border: 2px solid var(--accent-gold);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 30px;
        }

        .admin-banner.active {
            display: block;
        }

        .admin-banner h3 {
            color: var(--accent-gold);
            font-size: 17px;
            margin-bottom: 15px;
            text-align: center;
        }

        .admin-form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 12px;
            margin-bottom: 15px;
        }

        .admin-form-grid input, .admin-form-grid select, .admin-form-grid textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 13px;
            outline: none;
            background: var(--bg-color);
        }

        .file-input-wrapper {
            grid-column: 1 / -1;
            background: #f2eee9;
            padding: 15px;
            border-radius: 6px;
            text-align: center;
            border: 1px dashed var(--accent-gold-light);
        }

        .btn-add {
            background-color: var(--accent-gold);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            font-size: 15px;
        }

        .btn-add:hover {
            background-color: var(--accent-gold-light);
        }

        /* التصنيفات وعرض المنتجات */
        .categories-nav {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .cat-btn {
            background-color: transparent;
            border: 1px solid var(--border-color);
            padding: 8px 20px;
            border-radius: 30px;
            cursor: pointer;
            font-size: 14px;
            color: var(--text-dark);
        }

        .cat-btn.active, .cat-btn:hover {
            background-color: var(--accent-gold);
            color: white;
            border-color: var(--accent-gold);
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 25px;
        }

        .empty-state {
            grid-column: 1 / -1;
            text-align: center;
            padding: 50px 20px;
            color: var(--text-muted);
            font-size: 15px;
            background: var(--card-bg);
            border-radius: 12px;
            border: 1px solid var(--border-color);
        }

        .product-card {
            background-color: var(--card-bg);
            border-radius: 12px;
            overflow: hidden;
            border: 1px solid var(--border-color);
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            position: relative;
        }

        .product-img {
            width: 100%;
            height: 220px;
            object-fit: contain;
            background-color: #f7f5f0;
            padding: 10px;
        }

        /* صندوق رفع وتعديل الصورة لكل عطر مباشرة */
        .img-update-box {
            padding: 8px;
            background: #f2eee9;
            text-align: center;
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
        }

        .product-info {
            padding: 15px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .product-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background: rgba(120, 110, 79, 0.9);
            color: white;
            padding: 3px 10px;
            border-radius: 20px;
            font-size: 11px;
            font-weight: bold;
            z-index: 10;
        }

        .product-title {
            font-size: 16px;
            font-weight: 700;
            color: var(--text-dark);
            margin-bottom: 5px;
        }

        .product-desc {
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 8px;
        }

        .product-notes {
            background: var(--bg-color);
            padding: 5px 8px;
            border-radius: 6px;
            font-size: 11px;
            color: var(--accent-gold);
            margin-bottom: 12px;
        }

        .product-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-top: auto;
            padding-top: 8px;
            border-top: 1px solid var(--border-color);
            gap: 6px;
        }

        .product-price-input {
            width: 70px;
            padding: 4px;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            font-size: 14px;
            font-weight: bold;
            color: var(--accent-gold);
            outline: none;
            background: var(--bg-color);
            text-align: center;
        }

        .actions-group {
            display: flex;
            gap: 4px;
        }

        .btn-order {
            background-color: var(--accent-gold);
            color: white;
            border: none;
            padding: 6px 10px;
            border-radius: 6px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
        }

        .btn-delete {
            background-color: #fae1dd;
            color: var(--danger-color);
            border: 1px solid var(--danger-color);
            padding: 6px 8px;
            border-radius: 6px;
            font-size: 11px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn-delete:hover {
            background-color: var(--danger-color);
            color: white;
        }

        .cart-bar {
            position: fixed;
            bottom: 15px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--accent-gold);
            color: white;
            padding: 12px 28px;
            border-radius: 50px;
            box-shadow: 0 10px 25px rgba(120, 110, 79, 0.4);
            display: flex;
            align-items: center;
            gap: 12px;
            z-index: 99;
            cursor: pointer;
            font-weight: bold;
        }

        .cart-count {
            background: white;
            color: var(--accent-gold);
            width: 24px;
            height: 24px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 14px;
        }

        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: var(--text-muted);
            font-size: 13px;
            border-top: 1px solid var(--border-color);
        }
    </style>
</head>
<body>

    <header>
        <div style="width: 80px;"></div>
        <div class="header-title-container">
            <svg class="logo-svg" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M 25,25 L 45,75 Q 50,85 55,75 L 80,25 Q 70,25 65,38 L 50,68 L 35,30 Q 30,25 25,25 Z" fill="#786E4F"/>
                <path d="M 50,25 C 68,25 80,35 80,50 C 80,63 68,72 50,72 L 50,60 C 62,60 70,54 70,48 C 70,40 60,35 50,35 Z" fill="#786E4F"/>
            </svg>
            <div class="brand-title">VELVET PARFUMS</div>
            <div class="brand-subtitle">عطور فيلقيت</div>
        </div>
        <button class="btn-admin-toggle" onclick="toggleAdminPanel()">🔒 الإدارة</button>
    </header>

    <div class="container">

        <!-- لوحة التحكم للإضافة -->
        <div class="admin-banner" id="admin-panel">
            <h3>✨ لوحة إضافة عطر جديد وتحديد التصنيف</h3>
            
            <div class="admin-form-grid">
                <input type="text" id="new-name" placeholder="اسم العطر (مثال: عطر نيش فاخر)">
                <input type="number" id="new-price" placeholder="السعر (د.ل)">
                <select id="new-cat">
                    <option value="شرقي">شرقي</option>
                    <option value="رجالي">رجالي</option>
                    <option value="نسائي">نسائي</option>
                    <option value="نيش">نيش</option>
                </select>
                <input type="text" id="new-notes" placeholder="مكونات النوتات العطرية (مثال: برغموت، عود، فانيليا)">
                <textarea id="new-desc" placeholder="الوصف والمواصفات الكاملة للعطر..." style="grid-column: 1 / -1; height: 60px;"></textarea>
                
                <div class="file-input-wrapper">
                    <label style="display: block; margin-bottom: 5px; font-weight: bold; color: var(--accent-gold);">📷 اختر صورة العطر من هاتفك:</label>
                    <input type="file" id="new-img-file" accept="image/*">
                </div>
            </div>
            
            <button class="btn-add" onclick="addNewPerfume()">+ نشر العطر فوراً في المتجر</button>
        </div>

        <!-- التصنيفات -->
        <div class="categories-nav">
            <button class="cat-btn active" onclick="filterPerfumes('الكل', this)">الكل</button>
            <button class="cat-btn" onclick="filterPerfumes('شرقي', this)">شرقي</button>
            <button class="cat-btn" onclick="filterPerfumes('رجالي', this)">رجالي</button>
            <button class="cat-btn" onclick="filterPerfumes('نسائي', this)">نسائي</button>
            <button class="cat-btn" onclick="filterPerfumes('نيش', this)">نيش</button>
        </div>

        <!-- شبكة العطور -->
        <div class="products-grid" id="products-container"></div>

    </div>

    <!-- شريط السلة الدائم -->
    <div class="cart-bar" onclick="sendCartToMessenger()">
        <span>🛒 إرسال الطلب عبر Facebook Messenger</span>
        <div class="cart-count" id="cart-count">0</div>
    </div>

    <footer>
        <p>© VELVET PARFUMS | جميع الحقوق محفوظة وتطوير VELVET PARFUMS</p>
    </footer>

    <script>
        const FB_PAGE_ID = "61596110442092";

        // قاعدة بيانات تضم 100 عطر عالمي جاهزة بالأسماء والوصف والنوتات (جاهزة لإضافة صورك وأسعارك)
        let perfumesList = [
            // --- قسم النيش الفاخر (Niche) ---
            { id: 1, name: "Baccarat Rouge 540 Extrait", price: 0, category: "نيش", desc: "أيقونة النيش الفاخرة بنوتات الزعفران والياسمين الثابتة.", notes: "زعفران | لوز مر | ياسمين", img: "" },
            { id: 2, name: "Parfums de Marly Layton", price: 0, category: "نيش", desc: "توليفة ملكية دافئة تجمع التفاح واللافندر والفانيليا الساحرة.", notes: "تفاح | لافندر | فانيليا دافئة", img: "" },
            { id: 3, name: "Parfums de Marly Herod", price: 0, category: "نيش", desc: "عطر التبغ الفاخر الممزوج بالقرفة والفانيليا الشرقية.", notes: "تبغ | قرفة | فانيليا", img: "" },
            { id: 4, name: "Parfums de Marly Pegasus", price: 0, category: "نيش", desc: "نفحات اللوز البودري والفانيليا لإطلالة نيش راقية وجذابة.", notes: "لوز مر | فانيليا | خشب صندل", img: "" },
            { id: 5, name: "Parfums de Marly Sedley", price: 0, category: "نيش", desc: "انتعاش الحمضيات والنعناع الأخضر لأيام الصيف الحارة.", notes: "نعناع | حمضيات | خشب أرز", img: "" },
            { id: 6, name: "Kilian Angel's Share", price: 0, category: "نيش", desc: "رائحة الكونياك الفاخرة الممزوجة بالقرفة والبلوط الدافئ.", notes: "كونياك | قرفة | بلوط", img: "" },
            { id: 7, name: "Kilian Good Girl Gone Bad", price: 0, category: "نيش", desc: "عاصفة زهرية بيضاء مغرية من الياسمين ومسك الروم.", notes: "ياسمين | مسك رومي | ورد", img: "" },
            { id: 8, name: "Tom Ford Lost Cherry", price: 0, category: "نيش", desc: "عبق الكرز الأسود الشهواني مع اللوز المر واللوز.", notes: "كرز أسود | لوز مر | حبوب تونس", img: "" },
            { id: 9, name: "Tom Ford Tobacco Vanille", price: 0, category: "نيش", desc: "دفء أوراق التبغ العتيقة مع فانيليا بوربون الغنية.", notes: "تبغ فاخر | فانيليا | أخشاب", img: "" },
            { id: 10, name: "Tom Ford Oud Wood", price: 0, category: "نيش", desc: "أفخم أخشاب العود المدخنة بلمسات الهيل وخشب الأرز.", notes: "عود | هيل | خشب أرز", img: "" },
            { id: 11, name: "Tom Ford Bitter Peach", price: 0, category: "نيش", desc: "خوخ غني وناضج بلمسات دافئة من الروم ومسك الروم.", notes: "خوخ | برتقال دموي | باتشولي", img: "" },
            { id: 12, name: "Xerjoff Erba Pura", price: 0, category: "نيش", desc: "قنبلة الفواكه الاستوائية المنعشة مع المسك الأبيض الثابت.", notes: "فواكه استوائية | برتقال صقلي | مسك أبيض", img: "" },
            { id: 13, name: "Xerjoff Naxos", price: 0, category: "نيش", desc: "لوحة فنية تجمع العسل الفاخر والتبغ وأزهار اللافندر.", notes: "عسل | تبغ | لافندر | قرفة", img: "" },
            { id: 14, name: "Xerjoff Accento", price: 0, category: "نيش", desc: "أناقة الأناناس والصفير والمسك الثابت المليء بالحيوية.", notes: "أناناس | صفير | مسك | فانيليا", img: "" },
            { id: 15, name: "Maison Francis Kurkdjian Grand Soir", price: 0, category: "نيش", desc: "عنبر ملكي دافئ وفخم يناسب السهرات والأجواء الباردة.", notes: "عنبر | فانيليا | لاباندا", img: "" },
            { id: 16, name: "Maison Francis Kurkdjian Aqua Universalis", price: 0, category: "نيش", desc: "رائحة النظافة المطلقة والمنعشة كالقميص الأبيض الجديد.", notes: "حمضيات | زنابق الوادي | زهور بيضاء", img: "" },
            { id: 17, name: "Creed Silver Mountain Water", price: 0, category: "نيش", desc: "انتعاش الجبال الثلجية والشاي الأخضر والكشمش الأسود.", notes: "شاي أخضر | كشمش | مسك", img: "" },
            { id: 18, name: "Creed Millesime Imperial", price: 0, category: "نيش", desc: "فخامة الفواكه البحرية المالحة والأخشاب الصيفية المنعشة.", notes: "ملح بحري | فواكه | خشب صندل", img: "" },
            { id: 19, name: "Creed Green Irish Tweed", price: 0, category: "نيش", desc: "كلاسيكية الريف الإنجليزي الأخضر بنوتات الفريزيا والسوسن.", notes: "إريش | لويزة | خشب ساج", img: "" },
            { id: 20, name: "Initio Oud for Greatness", price: 0, category: "نيش", desc: "قوة العود الطبيعي الممزوج بالزعفران وجوزة الطيب الأسطورية.", notes: "عود طبيعي | زعفران | جوزة الطيب", img: "" },
            { id: 21, name: "Initio Side Effect", price: 0, category: "نيش", desc: "مزيج مسكر ومدمن من الروم والفانيليا والتبغ والقرفة.", notes: "روم | فانيليا | تبغ | قرفة", img: "" },
            { id: 22, name: "Byredo Gypsy Water", price: 0, category: "نيش", desc: "روح الطبيعة الحرة بنوتات الصنوبر والبرغموت والفانيليا الناعمة.", notes: "صنوبر | برغموت | فانيليا خشبية", img: "" },
            { id: 23, name: "Byredo Bal d'Afrique", price: 0, category: "نيش", desc: "لوحة عطرية دافئة تمزج زهر البرتقال بأخشاب الأرز والعنبر.", notes: "زهر برتقال | ليمون | عنبر", img: "" },
            { id: 24, name: "Mancera Cedrat Boise", price: 0, category: "نيش", desc: "انتعاش الليمون والحمضيات مع قاعدة خشبية دخانية مميزة.", notes: "ليمون | كشمش أسود | أخشاب", img: "" },
            { id: 25, name: "Mancera Red Tobacco", price: 0, category: "نيش", desc: "تبغ أحمر ناري قوي وثابت جداً مع التوابل الحارة.", notes: "تبغ | قرفة | العود الأبيض", img: "" },
            { id: 26, name: "Montale Intense Cafe", price: 0, category: "نيش", desc: "قهوة عربية دافئة ممزوجة بعبق الورد التركي والفانيليا.", notes: "قهوة | ورد تركي | فانيليا مسك", img: "" },
            { id: 27, name: "Orto Parisi Megamare", price: 0, category: "نيش", desc: "عطر بحري عمودق ومالح ذو ثبات وفوحان خارق.", notes: "نوتات بحرية | أعشاب بحرية | طحالب", img: "" },
            { id: 28, name: "Nasomatto Black Afgano", price: 0, category: "نيش", desc: "الغموض الشرقي الداكن بنوتات الحشيش الفاخر والأخشاب المدخنة.", notes: "حشيش فاخر | تبغ | أخشاب العود", img: "" },
            { id: 29, name: "Tiziana Terenzi Kirke", price: 0, category: "نيش", desc: "فاكهة العاطفة الاستوائية الساحرة مع المسك الدافئ الجذاب.", notes: "فاكهة العاطفة | خوخ | مسك", img: "" },
            { id: 30, name: "Amouage Interlude Man", price: 0, category: "نيش", desc: "عطر الأساطير والدخان والبخور والأخشاب الشرقية الثابتة.", notes: "بخور | أوريجانو | عود | جلد", img: "" },

            // --- قسم العطور الرجالية (Men) ---
            { id: 31, name: "Creed Aventus", price: 0, category: "رجالي", desc: "ملك العطور الرجالية بنوتات الأناناس والأخشاب والدخان.", notes: "أناناس | أخشاب الأرز | مسك", img: "" },
            { id: 32, name: "Bleu de Chanel EDP", price: 0, category: "رجالي", desc: "أناقة الحمضيات والبخور والأخشاب العطرية الساحرة.", notes: "حمضيات | بخور | أخشاب صندل", img: "" },
            { id: 33, name: "Dior Sauvage Elixir", price: 0, category: "رجالي", desc: "تركيز مكثف وتوابل حارة فاخرة مع الخزامى واللافندر.", notes: "قرفة | جوزة الطيب | خزامى", img: "" },
            { id: 34, name: "Dior Sauvage EDT", price: 0, category: "رجالي", desc: "البرغموت المنعش والأمبروكسان الجذاب لكل الأوقات.", notes: "برغموت | فلفل أسود | أمبروكسان", img: "" },
            { id: 35, name: "Giorgio Armani Acqua Di Gio Parfum", price: 0, category: "رجالي", desc: "انتعاش أمواج البحر العميقة مع البخور والأخشاب المعدنية.", notes: "نوتات بحرية | إكليل الجبل | بخور", img: "" },
            { id: 36, name: "Armani Code Parfum", price: 0, category: "رجالي", desc: "فول التونكا الدافئ مع السوسن وأخشاب الأرز العميقة.", notes: "سوسن | فول تونكا | أخشاب أرز", img: "" },
            { id: 37, name: "Versace Eros EDP", price: 0, category: "رجالي", desc: "نعناع منعش مع التفاح الفانيليا وحبوب التونكا الجذابة.", notes: "نعناع | تفاح حامض | فانيليا", img: "" },
            { id: 38, name: "Versace Dylan Blue", price: 0, category: "رجالي", desc: "حمضيات متوسطية منعشة مع البخور والمسك والأعشاب.", notes: "برغموت | جريب فروت | بخور", img: "" },
            { id: 39, name: "Paco Rabanne 1 Million Elixir", price: 0, category: "رجالي", desc: "مزيج غني من الفانيليا والورد التركي وحبوب التونكا الحشوية.", notes: "فانيليا | ورد تركي | تونكا", img: "" },
            { id: 40, name: "Paco Rabanne Invictus Victory", price: 0, category: "رجالي", desc: "انتعاش الليمون الحامض مع قوة الفانيليا والعنبر.", notes: "ليمون | فلفل وردي | فانيليا", img: "" },
            { id: 41, name: "Jean Paul Gaultier Le Male Le Parfum", price: 0, category: "رجالي", desc: "هال وهيل وزهور السوسن مع الفانيليا الشرقية الدافئة.", notes: "هيل | لافندر | فانيليا شرقية", img: "" },
            { id: 42, name: "Jean Paul Gaultier Scandal Pour Homme", price: 0, category: "رجالي", desc: "كراميل حلو مع الميرمية والماندرين لإطلالة جريئة.", notes: "كراميل | ميرمية | نجيل الهند", img: "" },
            { id: 43, name: "Tom Ford Ombre Leather", price: 0, category: "رجالي", desc: "عبير الجلود الفاخرة النقية مع الهيل والياسمين البري.", notes: "جلد أسود | هيل | ياسمين بري", img: "" },
            { id: 44, name: "Tom Ford Noir Extreme", price: 0, category: "رجالي", desc: "توابل هندية وفانيليا غنية مع كولفي الحليب الساحر.", notes: "كولفي | توابل | فانيليا خشبية", img: "" },
            { id: 45, name: "Hermes Terre d'Hermes", price: 0, category: "رجالي", desc: "رائحة الأرض والمعادن وأشجار البرتقال والفلفل الحار.", notes: "برتقال | فلفل | أخشاب الأرز", img: "" },
            { id: 46, name: "Bleu de Chanel Parfum", price: 0, category: "رجالي", desc: "أعلى درجات الفخامة الخشبية العطرية الناعمة والثابتة.", notes: "قشر ليمون | خشب صندل | أرز", img: "" },
            { id: 47, name: "Yves Saint Laurent Y EDP", price: 0, category: "رجالي", desc: "تفاح مقرمش مع الميرمية والزنجبيل لإطلالة شبابية حيوية.", notes: "تفاح | زنجبيل | ميرمية", img: "" },
            { id: 48, name: "Yves Saint Laurent La Nuit de L'Homme", price: 0, category: "رجالي", desc: "عطر السهرات الرومانسي بالهيل واللافندر والأخشاب الدافئة.", notes: "هيل | لافندر | خشب الأرز", img: "" },
            { id: 49, name: "Dolce & Gabbana The One EDP", price: 0, category: "رجالي", desc: "دفء التبغ والعنبر والجريب فروت لإطلالة أنيقة للغاية.", notes: "جريب فروت | كزبرة | تبغ وعنبر", img: "" },
            { id: 50, name: "Dolce & Gabbana Light Blue Eau Intense", price: 0, category: "رجالي", desc: "انتعاش مياه البحر المتوسط الحامضة والمنعشة بصيف ليبيا.", notes: "جريب فروت | مياه بحر | مسك", img: "" },
            { id: 51, name: "Prada Luna Rossa Carbon", price: 0, category: "رجالي", desc: "معادن باردة ومعدنية مع اللافندر والخزامى الأنيق.", notes: "لافندر | فلفل معدني | باتشولي", img: "" },
            { id: 52, name: "Bvlgari Man In Black", price: 0, category: "رجالي", desc: "توابل داكنة وجلود فاخرة مع الروم والعنبر الشرقي.", notes: "روم | توابل | جلد وعنبر", img: "" },
            { id: 53, name: "Montblanc Explorer", price: 0, category: "رجالي", desc: "برغموت إيطالي منعش مع نجيل الهند والأخشاب الرجولية.", notes: "برغموت | نجيل الهند | جلد الكاكاو", img: "" },
            { id: 54, name: "Azzaro The Most Wanted Parfum", price: 0, category: "رجالي", desc: "زنجبيل حار مع الشوكولاتة وفانيليا البوربون الدافئة.", notes: "زنجبيل | روائح خشبية | فانيليا", img: "" },
            { id: 55, name: "Carolina Herrera Bad Boy Le Parfum", price: 0, category: "رجالي", desc: "القنب والمريمية والجلود في توليفة عطرية عصرية جريئة.", notes: "قنب | مريمية | جلود سوداء", img: "" },
            { id: 56, name: "Lalique Encre Noire", price: 0, category: "رجالي", desc: "سيد النوتات الخشبية والنجيل الهند الداكن والغامض.", notes: "نجيل هندي | سرو | مسك أخشاب", img: "" },
            { id: 57, name: "Davidoff Cool Water", price: 0, category: "رجالي", desc: "الكلاسيكية المنعشة بنوتات النعناع ومياه البحر الخالدة.", notes: "نعناع | ماء البحر | لافندر", img: "" },
            { id: 58, name: "Issey Miyake L'Eau d'Issey Pour Homme", price: 0, category: "رجالي", desc: "يوسوكي ياباني وحمضيات خفيفة مع نوتات خشبية صيفية.", notes: "يوسو | ليمون | توابل مائية", img: "" },
            { id: 59, name: "Burberry Hero EDP", price: 0, category: "رجالي", desc: "أرز أطلسي دافئ مع إبرة الصقنوبر والجاوي الفاخر.", notes: "أرز الأطلس | صنوبر | جاوي", img: "" },
            { id: 60, name: "Ralph Lauren Polo Blue Parfum", price: 0, category: "رجالي", desc: "يوسفي ونوتات أكسجين بحرية مع نجيل الهند الفاخر.", notes: "يوسفي | مريمية | نجيل الهند", img: "" },

            // --- قسم العطور النسائية (Women) ---
            { id: 61, name: "Dior J'adore EDP", price: 0, category: "نسائي", desc: "باقة زهرية أنثوية خالدة من الياسمين والورد والكمثرى.", notes: "ياسمين | ورد جوري | كمثرى", img: "" },
            { id: 62, name: "Yves Saint Laurent Libre Intense", price: 0, category: "نسائي", desc: "لافندر فرنسي ناعم مع أوركيد الفانيليا الدافئة والجذابة.", notes: "لافندر | أوركيد | فانيليا مدغشقر", img: "" },
            { id: 63, name: "Chanel Coco Mademoiselle", price: 0, category: "نسائي", desc: "أناقة البرتقال المنعش مع الورد التركي والباتشولي النقي.", notes: "برتقال | ورد | باتشولي", img: "" },
            { id: 64, name: "Chanel No. 5", price: 0, category: "نسائي", desc: "عطر الأساطير الألدهيدي الزهري الخالد والفاخر.", notes: "ألدهيدات | ياسمين | ورد | مسك", img: "" },
            { id: 65, name: "Carolina Herrera Good Girl", price: 0, category: "نسائي", desc: "توليفة اللوز والقهوة ومسك الروم في زجاجة الحذاء الأيقونية.", notes: "لوز | قهوة | مسك رومي | كاكاو", img: "" },
            { id: 66, name: "Lancome La Vie Est Belle", price: 0, category: "نسائي", desc: "سعادة السوسن والياسمين مع حلاوة الباتشولي والفانيليا.", notes: "سوسن | ياسمين | برالين وفانيليا", img: "" },
            { id: 67, name: "Lancome Idole", price: 0, category: "نسائي", desc: "ورد نقي مع الياسمين والكمثرى لإطلالة عصرية مشرقة.", notes: "ورد أخضر | ياسمين | كمثرى", img: "" },
            { id: 68, name: "Giorgio Armani My Way", price: 0, category: "نسائي", desc: "زهر البرتقال ومسك الروم الهندي مع فانيليا مدغشقر.", notes: "زهر برتقال | مسك رومي | فانيليا", img: "" },
            { id: 69, name: "Giorgio Armani Si EDP", price: 0, category: "نسائي", desc: "رحيق الكشمش الأسود مع الورد وخشب الأرز الراقي.", notes: "كشمش أسود | ورد فريزيا | باتشولي", img: "" },
            { id: 70, name: "Valentino Donna Born In Roma", price: 0, category: "نسائي", desc: "ياسمين فاخر مع فانيليا دافئة ولمسات خشبية عصرية.", notes: "ياسمين | فانيليا بوربون | أخشاب", img: "" },
            { id: 71, name: "Marc Jacobs Daisy", price: 0, category: "نسائي", desc: "فراولة برية وفريزيا وبنفسج لعطر صيفي مرح ومنعش.", notes: "فراولة | بنفسج | أوراق ياسمين", img: "" },
            { id: 72, name: "Gucci Bloom", price: 0, category: "نسائي", desc: "حديقة أزهار بيضاء غنية بعبق مسك الروم والياسمين البري.", notes: "مسك رومي | ياسمين | زهر رانجون", img: "" },
            { id: 73, name: "Gucci Flora Gorgeous Gardenia", price: 0, category: "نسائي", desc: "زهرة الغاردينيا البيضاء مع زهر الكمثرى والسكر البني.", notes: "غاردينيا | زهر كمثرى | سكر بني", img: "" },
            { id: 74, name: "Paco Rabanne Olympéa", price: 0, category: "نسائي", desc: "فانيليا مالحة فريدة مع زهر الياسمين واليوسفي الأخضر.", notes: "فانيليا مالحة | ياسمين مائي | زنجبيل", img: "" },
            { id: 75, name: "Viktor & Rolf Flowerbomb", price: 0, category: "نسائي", desc: "قنبلة أزهار مذهلة من الشاي والياسمين والورد والباتشولي.", notes: "شاي | ياسمين | ورد | باتشولي", img: "" },
            { id: 76, name: "Tom Ford Black Orchid", price: 0, category: "نسائي", desc: "أوركيد سوداء داكنة مع الشوكولاتة والتوابل والكمأة الفاخرة.", notes: "أوركيد سوداء | شوكولاتة | كمأة", img: "" },
            { id: 77, name: "Tom Ford Velvet Orchid", price: 0, category: "نسائي", desc: "زهور أوركيد مخملية مع العسل والروم والفانيليا الدافئة.", notes: "عسل | روم | أوركيد مخملي", img: "" },
            { id: 78, name: "Burberry Her EDP", price: 0, category: "نسائي", desc: "توت بري وفراولة مقرمشة مع قاعدة مسكية خشبية ناعمة.", notes: "توت بري | فراولة | مسك وعنبر", img: "" },
            { id: 79, name: "Versace Bright Crystal", price: 0, category: "نسائي", desc: "رمان منعش مع زهر الياسمين والفاوانيا الصيفية الرقيقة.", notes: "رمان | فاوانيا | مسك وعنبر", img: "" },
            { id: 80, name: "Jean Paul Gaultier La Belle", price: 0, category: "نسائي", desc: "كمثرى ناضجة وحسية مع فانيليا ونوتات شرقية دافئة.", notes: "كمثرى | نجيل الهند | فانيليا", img: "" },
            { id: 81, name: "Prada Paradoxe", price: 0, category: "نسائي", desc: "زهر البرتقال والعنبر الأبيض في زجاجة مثلثة عصرية فريدة.", notes: "زهر برتقال | عنبر أبيض | مسك", img: "" },
            { id: 82, name: "Hermes Twilly d'Hermes", price: 0, category: "نسائي", desc: "زنجبيل منعش مع مسروب التوليب وخشب الصندل الشبابي.", notes: "زنجبيل | مسك رومي | خشب صندل", img: "" },
            { id: 83, name: "Narciso Rodriguez For Her", price: 0, category: "نسائي", desc: "مسك مصري ساحر مع زهر البرتقال والأوسمانثوس الناعم.", notes: "مسك | زهر برتقال | أوسمانثوس", img: "" },
            { id: 84, name: "Calvin Klein Euphoria", price: 0, category: "نسائي", desc: "رمان وأوركيد أسود مع الماهوجني لإطلالة شرقية غامضة.", notes: "رمان | أوركيد أسود | ماهوجني", img: "" },
            { id: 85, name: "Jo Malone English Pear & Freesia", price: 0, category: "نسائي", desc: "كمثرى إنجليزية ناضجة مع فريزيا بيضاء وأخشاب العنبر.", notes: "كمثرى | فريزيا | باتشولي", img: "" },
            { id: 86, name: "Chloe EDP", price: 0, category: "نسائي", desc: "ورد بلغاري فاخر وبودرة ناعمة مع الفاوانيا واللوز.", notes: "ورد بلغاري | فاوانيا | عسل", img: "" },
            { id: 87, name: "DKNY Be Delicious", price: 0, category: "نسائي", desc: "تفاح أخضر مقرمش ومنعش للغاية لأجواء الصيف الحيوية.", notes: "تفاح أخضر | خيار | ماغنوليا", img: "" },
            { id: 88, name: "Alien Mugler", price: 0, category: "نسائي", desc: "ياسمين سامباك غامض وعميق مع أخشاب الكشمير والعنبر.", notes: "ياسمين | أخشاب كشمير | عنبر أبيض", img: "" },
            { id: 89, name: "Angel Mugler", price: 0, category: "نسائي", desc: "شوكولاتة داكنة وباتشولي وفواكه حمراء في عطر أيقوني مميز.", notes: "باتشولي | شوكولاتة | توت بري", img: "" },
            { id: 90, name: "Salvatore Ferragamo Signorina", price: 0, category: "نسائي", desc: "توت رديء وفلفل وردي مع الباناكوتا والمسك الناعم.", notes: "فلفل وردي | باناكوتا | باتشولي", img: "" },

            // --- قسم العطور الشرقية (Oriental) ---
            { id: 91, name: "دهن العود المعتق الملكي", price: 0, category: "شرقي", desc: "أصالة العود الكمبودي المعتق بثبات وفوحان شرقي عالي.", notes: "عود كمبودي | عنبر | خشب صندل", img: "" },
            { id: 92, name: "مسك الختام الأبيض", price: 0, category: "شرقي", desc: "مسك نقي وبودري مخملي يمنح شعور النظافة المطلقة.", notes: "مسك أبيض | بودرة | ورد طائفي", img: "" },
            { id: 93, name: "عنبر الملوك الخالص", price: 0, category: "شرقي", desc: "دفء العنبر الشرقي الأصيل الممزوج بالتوابل والزعفران.", notes: "عنبر دافئ | زعفران | هيل", img: "" },
            { id: 94, name: "ورد طائفي معتق", price: 0, category: "شرقي", desc: "عبير الورد الطائفي الفاخر المقطر بعناية فائقة.", notes: "ورد طائفي | دهن عود خفيف | مسك", img: "" },
            { id: 95, name: "خلاصة العود الهندي", price: 0, category: "شرقي", desc: "عبق أخشاب العود الهندي القديم والثقيل للمجالس الرسمية.", notes: "عود هندي معتق | بخور | جلد", img: "" },
            { id: 96, name: "مسك العروس الفاخر", price: 0, category: "شرقي", desc: "مزيج كريمي أنثوي من المسك الأبيض والفانيليا الخفيفة.", notes: "مسك أبيض | فانيليا كريمية | زهور", img: "" },
            { id: 97, name: "لبان الدكور العماني", price: 0, category: "شرقي", desc: "بخور لبان الدكور الملكي المنقى لأجواء المنازل والمجالس.", notes: "لبان عماني | صمغ طبيعي | بخور", img: "" },
            { id: 98, name: "مخلط الملك الفاخر", price: 0, category: "شرقي", desc: "توليفة متوازنة تجمع الورد والزعفران والعود والعنبر.", notes: "زعفران | ورد | عود | عنبر", img: "" },
            { id: 99, name: "مسك الرمان السحري", price: 0, category: "شرقي", desc: "انتعاش حبات الرمان الحلوة الممزوجة بعبق المسك الأبيض.", notes: "رمان أحمر | مسك أبيض | توت", img: "" },
            { id: 100, name: "توليفة عطور فيلقيت الخاصة", price: 0, category: "شرقي", desc: "العطر الحصري والخاص بمتجرنا المميز في طرابلس.", notes: "توليفة سرية | عود وخشب صندل", img: "" }
        ];

        let currentFilter = 'الكل';
        let selectedCart = [];

        function toggleAdminPanel() {
            const panel = document.getElementById('admin-panel');
            panel.style.display = (panel.style.display === 'block') ? 'none' : 'block';
        }

        function displayPerfumes(items) {
            const container = document.getElementById('products-container');
            container.innerHTML = '';

            let filteredItems = items;
            if (currentFilter !== 'الكل') {
                filteredItems = items.filter(p => p.category === currentFilter);
            }

            if (filteredItems.length === 0) {
                container.innerHTML = `
                    <div class="empty-state">
                        <p>لا توجد عطور مضافة حالياً في هذا القسم.</p>
                    </div>
                `;
                return;
            }

            filteredItems.forEach(item => {
                const card = document.createElement('div');
                card.className = 'product-card';
                
                // إذا لم يتم رفع صورة عطر، نضع أيقونة أو صورة افتراضية فاخرة
                const imgSrc = item.img ? item.img : 'https://images.unsplash.com/photo-1588405748880-12d1d2a59f75?auto=format&fit=crop&q=80&w=600';

                card.innerHTML = `
                    <div class="product-badge">${item.category}</div>
                    <img src="${imgSrc}" class="product-img" alt="${item.name}">
                    
                    <!-- خانة رفع أو تغيير صورة العطر مباشرة من الهاتف -->
                    <div class="img-update-box">
                        <label style="font-size: 11px; color: var(--accent-gold); cursor: pointer; font-weight: bold;">
                            📷 تغيير صورة العطر
                            <input type="file" accept="image/*" style="display: none;" onchange="updatePerfumeImage(${item.id}, this)">
                        </label>
                    </div>

                    <div class="product-info">
                        <div class="product-title">${item.name}</div>
                        <div class="product-desc">${item.desc}</div>
                        <div class="product-notes">${item.notes}</div>
                        
                        <!-- تغيير التصنيف مباشرة -->
                        <div style="margin-bottom: 10px; display: flex; align-items: center; gap: 6px;">
                            <span style="font-size: 11px; color: var(--text-muted);">التصنيف:</span>
                            <select onchange="changePerfumeCategory(${item.id}, this.value)" style="font-size: 11px; padding: 2px 4px; border: 1px solid var(--border-color); border-radius: 4px; background: var(--bg-color); outline: none; cursor: pointer;">
                                <option value="شرقي" ${item.category === 'شرقي' ? 'selected' : ''}>شرقي</option>
                                <option value="رجالي" ${item.category === 'رجالي' ? 'selected' : ''}>رجالي</option>
                                <option value="نسائي" ${item.category === 'نسائي' ? 'selected' : ''}>نسائي</option>
                                <option value="نيش" ${item.category === 'نيش' ? 'selected' : ''}>نيش</option>
                            </select>
                        </div>

                        <div class="product-footer">
                            <div style="display: flex; align-items: center; gap: 4px;">
                                <input type="number" class="product-price-input" value="${item.price}" onchange="updatePerfumePrice(${item.id}, this.value)" title="السعر د.ل">
                                <span style="font-size: 11px; font-weight: bold; color: var(--accent-gold);">د.ل</span>
                            </div>
                            <div class="actions-group">
                                <button class="btn-order" onclick="addToCart(${item.id})">+ طلب</button>
                                <button class="btn-delete" onclick="deletePerfume(${item.id})" title="حذف">حذف</button>
                            </div>
                        </div>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        function compressAndProcessImage(file, callback) {
            const reader = new FileReader();
            reader.readAsDataURL(file);
            reader.onload = function(event) {
                const img = new Image();
                img.src = event.target.result;
                img.onload = function() {
                    const canvas = document.createElement('canvas');
                    const MAX_WIDTH = 500;
                    const scaleFactor = MAX_WIDTH / img.width;
                    canvas.width = MAX_WIDTH;
                    canvas.height = img.height * scaleFactor;

                    const ctx = canvas.getContext('2d');
                    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
                    
                    const compressedDataUrl = canvas.toDataURL('image/jpeg', 0.75);
                    callback(compressedDataUrl);
                }
            }
        }

        // تحديث صورة عطر معين مباشرة
        function updatePerfumeImage(id, inputElement) {
            if (inputElement.files && inputElement.files[0]) {
                compressAndProcessImage(inputElement.files[0], function(compressedImg) {
                    const item = perfumesList.find(p => p.id === id);
                    if (item) {
                        item.img = compressedImg;
                        displayPerfumes(perfumesList);
                    }
                });
            }
        }

        function addNewPerfume() {
            const name = document.getElementById('new-name').value.trim();
            const price = document.getElementById('new-price').value.trim() || 0;
            const cat = document.getElementById('new-cat').value;
            const notes = document.getElementById('new-notes').value.trim() || "تركيبة عطرة مميزة";
            const desc = document.getElementById('new-desc').value.trim() || "عطر فاخر ومميز من تشكيلة فيلقيت.";
            const fileInput = document.getElementById('new-img-file');

            if(!name) {
                alert('الرجاء كتابة اسم العطر على الأقل.');
                return;
            }

            if (fileInput.files && fileInput.files[0]) {
                compressAndProcessImage(fileInput.files[0], function(compressedImg) {
                    savePerfumeItem(name, price, cat, notes, desc, compressedImg);
                });
            } else {
                savePerfumeItem(name, price, cat, notes, desc, "");
            }
        }

        function savePerfumeItem(name, price, cat, notes, desc, imgUrl) {
            const newItem = {
                id: Date.now(),
                name: name,
                price: parseFloat(price),
                category: cat,
                desc: desc,
                notes: notes,
                img: imgUrl
            };

            perfumesList.unshift(newItem);
            displayPerfumes(perfumesList);
            
            document.getElementById('new-name').value = '';
            document.getElementById('new-price').value = '';
            document.getElementById('new-notes').value = '';
            document.getElementById('new-desc').value = '';
            document.getElementById('new-img-file').value = '';
            toggleAdminPanel();

            alert(`تمت إضافة عطر "${name}" بنجاح!`);
        }

        function updatePerfumePrice(id, newPrice) {
            const item = perfumesList.find(p => p.id === id);
            if(item) {
                item.price = parseFloat(newPrice) || 0;
            }
        }

        function deletePerfume(id) {
            if (confirm('هل أنت متأكد من حذف هذا العطر نهائياً؟')) {
                perfumesList = perfumesList.filter(p => p.id !== id);
                displayPerfumes(perfumesList);
            }
        }

        function changePerfumeCategory(id, newCat) {
            const perfume = perfumesList.find(p => p.id === id);
            if (perfume) {
                perfume.category = newCat;
                displayPerfumes(perfumesList);
            }
        }

        function filterPerfumes(category, btnElement) {
            currentFilter = category;
            document.querySelectorAll('.cat-btn').forEach(b => b.classList.remove('active'));
            btnElement.classList.add('active');
            displayPerfumes(perfumesList);
        }

        function addToCart(id) {
            const item = perfumesList.find(p => p.id === id);
            if(item) {
                selectedCart.push({ name: item.name, price: item.price });
                document.getElementById('cart-count').innerText = selectedCart.length;
            }
        }

        function sendCartToMessenger() {
            if(selectedCart.length === 0) {
                alert('اختر عطراً أولاً لإرسال الطلب عبر الماسنجر.');
                return;
            }

            let totalPrice = 0;
            let summaryText = "أهلاً VELVET PARFUMS 👋 ، أرغب في طلب العطور التالية:\n\n";

            selectedCart.forEach((item, index) => {
                summaryTest += `${index + 1}. ${item.name} - ${item.price} د.ل\n`;
                totalPrice += item.price;
            });

            summaryText += `\nإجمالي المبلغ: ${totalPrice} د.ل`;
            
            const messengerUrl = `https://m.me/${FB_PAGE_ID}?text=${encodeURIComponent(summaryText)}`;
            window.open(messengerUrl, '_blank');
        }

        displayPerfumes(perfumesList);
    </script>
</body>
</html>
