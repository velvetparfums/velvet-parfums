<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>VELVET PARFUMS | عطور فيلقيت</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-color: #f9f7f2;
            --card-bg: #ffffff;
            --accent-gold: #b39359;
            --accent-gold-dark: #8c703b;
            --text-dark: #2c2a29;
            --text-muted: #66625c;
            --border-color: #e8e4dc;
            --shadow: 0 6px 20px rgba(0,0,0,0.05);
            --danger-color: #c0392b;
            --success-color: #27ae60;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Tajawal', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-dark);
            line-height: 1.5;
            padding-bottom: 100px;
        }

        header {
            background-color: var(--card-bg);
            padding: 15px 12px;
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.03);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .header-title-container {
            text-align: center;
            cursor: pointer;
        }

        .logo-svg {
            width: 48px;
            height: 48px;
            margin: 0 auto;
            display: block;
        }

        .brand-title {
            font-family: 'Cinzel', serif;
            font-size: 16px;
            font-weight: 700;
            letter-spacing: 1.5px;
            color: var(--accent-gold-dark);
            margin-top: 2px;
        }

        .brand-subtitle {
            font-family: 'Cinzel', serif;
            font-size: 8px;
            letter-spacing: 1.5px;
            color: var(--text-muted);
            text-transform: uppercase;
        }

        .container {
            width: 100%;
            max-width: 1100px;
            margin: 0 auto;
            padding: 12px;
        }

        .admin-banner {
            display: none;
            background: #ffffff;
            border: 1.5px solid var(--accent-gold);
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 20px;
        }

        .admin-banner h3 {
            color: var(--accent-gold-dark);
            font-size: 15px;
            margin-bottom: 12px;
            text-align: center;
        }

        .admin-form-grid {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 12px;
        }

        .admin-form-grid input, .admin-form-grid select, .admin-form-grid textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            font-size: 13px;
            outline: none;
            background: var(--bg-color);
        }

        .file-input-wrapper {
            background: #f2eee9;
            padding: 12px;
            border-radius: 8px;
            text-align: center;
            border: 1px dashed var(--accent-gold);
        }

        .admin-actions-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 8px;
            margin-top: 10px;
        }

        .btn-add {
            background-color: var(--accent-gold);
            color: white;
            border: none;
            padding: 12px;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            font-size: 14px;
        }

        .btn-backup {
            background-color: var(--success-color);
            color: white;
            border: none;
            padding: 10px;
            border-radius: 8px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
        }

        .btn-restore {
            background-color: #2980b9;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 8px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
        }

        .categories-nav {
            display: flex;
            gap: 8px;
            margin-bottom: 20px;
            overflow-x: auto;
            padding-bottom: 5px;
            -webkit-overflow-scrolling: touch;
        }

        .categories-nav::-webkit-scrollbar {
            display: none;
        }

        .cat-btn {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 6px 16px;
            border-radius: 20px;
            cursor: pointer;
            font-size: 13px;
            color: var(--text-dark);
            white-space: nowrap;
            flex-shrink: 0;
        }

        .cat-btn.active {
            background-color: var(--accent-gold);
            color: white;
            border-color: var(--accent-gold);
            font-weight: bold;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(155px, 1fr));
            gap: 12px;
        }

        @media (min-width: 600px) {
            .products-grid {
                grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
                gap: 20px;
            }
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
            height: 150px;
            object-fit: cover;
            background-color: #f7f5f0;
        }

        @media (min-width: 600px) {
            .product-img {
                height: 220px;
            }
        }

        .img-update-box {
            display: none;
            padding: 5px;
            background: #f2eee9;
            text-align: center;
            border-top: 1px solid var(--border-color);
            border-bottom: 1px solid var(--border-color);
        }

        .product-info {
            padding: 10px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .product-badge {
            position: absolute;
            top: 8px;
            right: 8px;
            background: rgba(139, 112, 59, 0.9);
            color: white;
            padding: 2px 8px;
            border-radius: 12px;
            font-size: 10px;
            font-weight: bold;
            z-index: 5;
        }

        .product-title {
            font-size: 13px;
            font-weight: 700;
            color: var(--text-dark);
            margin-bottom: 4px;
            line-height: 1.3;
        }

        .product-desc {
            font-size: 11px;
            color: var(--text-muted);
            margin-bottom: 6px;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .product-notes {
            background: var(--bg-color);
            padding: 4px 6px;
            border-radius: 4px;
            font-size: 10px;
            color: var(--accent-gold-dark);
            margin-bottom: 8px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .product-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-top: auto;
            padding-top: 6px;
            border-top: 1px solid var(--border-color);
            gap: 4px;
        }

        .product-price-display {
            font-size: 14px;
            font-weight: bold;
            color: var(--accent-gold-dark);
        }

        .product-price-input {
            display: none;
            width: 55px;
            padding: 3px;
            border: 1px solid var(--border-color);
            border-radius: 4px;
            font-size: 12px;
            font-weight: bold;
            color: var(--accent-gold-dark);
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
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 11px;
            font-weight: bold;
            cursor: pointer;
        }

        .btn-delete {
            display: none;
            background-color: #fae1dd;
            color: var(--danger-color);
            border: 1px solid var(--danger-color);
            padding: 6px 6px;
            border-radius: 6px;
            font-size: 10px;
            cursor: pointer;
            font-weight: bold;
        }

        /* نافذة بيانات التوصيل للزبون */
        .checkout-modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 15px;
        }

        .checkout-content {
            background: white;
            padding: 20px;
            border-radius: 12px;
            width: 100%;
            max-width: 400px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        .checkout-content h3 {
            color: var(--accent-gold-dark);
            margin-bottom: 15px;
            font-size: 16px;
            text-align: center;
        }

        .checkout-form-group {
            margin-bottom: 10px;
        }

        .checkout-form-group label {
            display: block;
            font-size: 12px;
            margin-bottom: 4px;
            font-weight: bold;
        }

        .checkout-form-group input, .checkout-form-group textarea {
            width: 100%;
            padding: 8px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 13px;
            outline: none;
        }

        .cart-bar {
            position: fixed;
            bottom: 12px;
            left: 5%;
            width: 90%;
            background: var(--accent-gold-dark);
            color: white;
            padding: 12px 18px;
            border-radius: 30px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            display: flex;
            align-items: center;
            justify-content: space-between;
            z-index: 99;
            cursor: pointer;
            font-weight: bold;
            font-size: 13px;
        }

        .cart-count {
            background: white;
            color: var(--accent-gold-dark);
            width: 22px;
            height: 22px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 12px;
        }

        footer {
            text-align: center;
            margin-top: 30px;
            padding: 15px;
            color: var(--text-muted);
            font-size: 11px;
            border-top: 1px solid var(--border-color);
        }
    </style>
</head>
<body class="customer-mode">

    <header>
        <div class="header-title-container" onclick="handleLogoTripleClick()">
            <svg class="logo-svg" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M 28 30 L 48 76 C 49 78 51 78 52 76 L 72 30 Q 74 25 68 25 C 65 25 62 27 60 32 L 50 58 L 40 32 C 38 27 35 25 32 25 Q 26 25 28 30 Z" fill="#B39359"/>
                <path d="M 50 32 C 58 32 68 37 68 46 C 68 55 58 60 50 60 L 50 53 C 56 53 62 49 62 46 C 62 42 56 38 50 38 Z" fill="#B39359"/>
            </svg>
            <div class="brand-title">VELVET PARFUMS</div>
            <div class="brand-subtitle">PREMIUM FRAGRANCES</div>
        </div>
    </header>

    <div class="container">

        <div class="admin-banner" id="admin-panel">
            <h3>✨ لوحة الإدارة الشاملة (خاصة بالمالك)</h3>
            <div class="admin-form-grid">
                <input type="text" id="new-name" placeholder="اسم العطر">
                <input type="number" id="new-price" placeholder="السعر (د.ل)">
                <select id="new-cat">
                    <option value="شرقي">شرقي</option>
                    <option value="رجالي">رجالي</option>
                    <option value="نسائي">نسائي</option>
                    <option value="نيش">نيش</option>
                </select>
                <input type="text" id="new-notes" placeholder="النوتات (برغموت، عود)">
                <textarea id="new-desc" placeholder="الوصف الكامل للعطر..."></textarea>
                
                <div class="file-input-wrapper">
                    <label style="display: block; font-weight: bold; color: var(--accent-gold-dark); font-size: 12px;">📷 اختر صورة العطر</label>
                    <input type="file" id="new-img-file" accept="image/*" style="margin-top: 5px;">
                </div>
            </div>
            
            <button class="btn-add" onclick="addNewPerfume()">+ نشر عطر جديد</button>

            <div class="admin-actions-row">
                <button class="btn-backup" onclick="exportData()">📥 تصدير ملف التعديلات</button>
                <button class="btn-restore" onclick="document.getElementById('import-file').click()">📤 استيراد ملف التعديلات</button>
                <input type="file" id="import-file" accept=".json" style="display:none" onchange="importData(this)">
            </div>
        </div>

        <div class="categories-nav">
            <button class="cat-btn active" onclick="filterPerfumes('الكل', this)">الكل</button>
            <button class="cat-btn" onclick="filterPerfumes('شرقي', this)">شرقي</button>
            <button class="cat-btn" onclick="filterPerfumes('رجالي', this)">رجالي</button>
            <button class="cat-btn" onclick="filterPerfumes('نسائي', this)">نسائي</button>
            <button class="cat-btn" onclick="filterPerfumes('نيش', this)">نيش</button>
        </div>

        <div class="products-grid" id="products-container"></div>

    </div>

    <!-- شريط السلة وإتمام الطلب -->
    <div class="cart-bar" onclick="openCheckoutModal()">
        <span>🛒 إتمام الطلب وتحديد التوصيل</span>
        <div class="cart-count" id="cart-count">0</div>
    </div>

    <!-- نافذة إدخال بيانات التوصيل للزبون -->
    <div class="checkout-modal" id="checkout-modal">
        <div class="checkout-content">
            <h3>📍 بيانات التوصيل واستلام الطلب</h3>
            <div class="checkout-form-group">
                <label>الاسم الكامل:</label>
                <input type="text" id="cust-name" placeholder="أدخل اسمك الكريم">
            </div>
            <div class="checkout-form-group">
                <label>رقم الهاتف:</label>
                <input type="tel" id="cust-phone" placeholder="رقم الهاتف للتواصل (مثال: 091XXXXXXX)">
            </div>
            <div class="checkout-form-group">
                <label>عنوان التوصيل (المنطقة / الشارع):</label>
                <textarea id="cust-address" placeholder="أدخل عنوانك بالتفصيل (مثال: طرابلس، زناتة، قرب...)" style="height: 60px;"></textarea>
            </div>
            <div style="display: flex; gap: 8px; margin-top: 15px;">
                <button class="btn-add" onclick="submitOrderToMessenger()" style="background: var(--success-color);">إرسال الطلب عبر الماسنجر</button>
                <button class="btn-add" onclick="closeCheckoutModal()" style="background: #95a5a6;">إلغاء</button>
            </div>
        </div>
    </div>

    <footer>
        <p>© VELVET PARFUMS | طرابلس، ليبيا</p>
    </footer>

    <script>
        const FB_PAGE_ID = "61596110442092";
        let isAdminMode = false;
        const ADMIN_SECRET = "velvet2026";

        let clickCount = 0;
        let clickTimer = null;

        function handleLogoTripleClick() {
            clickCount++;
            if (clickCount === 1) {
                clickTimer = setTimeout(() => {
                    clickCount = 0;
                }, 600);
            } else if (clickCount === 3) {
                clearTimeout(clickTimer);
                clickCount = 0;
                verifyAdminAccess();
            }
        }

        function verifyAdminAccess() {
            const pass = prompt("الرجاء إدخال كلمة مرور المشرف:");
            if (pass === ADMIN_SECRET) {
                isAdminMode = !isAdminMode;
                document.getElementById('admin-panel').style.display = isAdminMode ? 'block' : 'none';
                displayPerfumes(perfumesList);
                alert(isAdminMode ? "تم تفعيل وضع الإدارة بنجاح!" : "تم خروج وضع الإدارة.");
            } else if (pass !== null) {
                alert("كلمة المرور غير صحيحة!");
            }
        }

        const defaultPerfumes = [
            { id: 1, name: "Baccarat Rouge 540", price: 0, category: "نيش", desc: "أيقونة النيش الفاخرة بنوتات الزعفران والياسمين الثابتة.", notes: "زعفران | لوز مر | ياسمين", img: "" },
            { id: 2, name: "Parfums de Marly Layton", price: 0, category: "نيش", desc: "توليفة ملكية دافئة تجمع التفاح واللافندر والفانيليا.", notes: "تفاح | لافندر | فانيليا", img: "" },
            { id: 3, name: "Parfums de Marly Herod", price: 0, category: "نيش", desc: "عطر التبغ الفاخر الممزوج بالقرفة والفانيليا الشرقية.", notes: "تبغ | قرفة | فانيليا", img: "" },
            { id: 4, name: "Parfums de Marly Pegasus", price: 0, category: "نيش", desc: "نفحات اللوز البودري والفانيليا لإطلالة نيش راقية.", notes: "لوز مر | فانيليا | خشب صندل", img: "" },
            { id: 5, name: "Parfums de Marly Sedley", price: 0, category: "نيش", desc: "انتعاش الحمضيات والنعناع الأخضر لأيام الصيف.", notes: "نعناع | حمضيات | خشب أرز", img: "" },
            { id: 6, name: "Kilian Angel's Share", price: 0, category: "نيش", desc: "رائحة الكونياك الفاخرة الممزوجة بالقرفة والبلوط.", notes: "كونياك | قرفة | بلوط", img: "" },
            { id: 7, name: "Kilian Good Girl Gone Bad", price: 0, category: "نيش", desc: "عاصفة زهرية بيضاء مغرية من الياسمين ومسك الروم.", notes: "ياسمين | مسك رومي | ورد", img: "" },
            { id: 8, name: "Tom Ford Lost Cherry", price: 0, category: "نيش", desc: "عبق الكرز الأسود الشهواني مع اللوز المر واللوز.", notes: "كرز أسود | لوز مر | حبوب تونس", img: "" },
            { id: 9, name: "Tom Ford Tobacco Vanille", price: 0, category: "نيش", desc: "دفء أوراق التبغ العتيقة مع فانيليا بوربون.", notes: "تبغ فاخر | فانيليا | أخشاب", img: "" },
            { id: 10, name: "Tom Ford Oud Wood", price: 0, category: "نيش", desc: "أفخم أخشاب العود المدخنة بلمسات الهيل والأرز.", notes: "عود | هيل | خشب أرز", img: "" },
            { id: 11, name: "Tom Ford Bitter Peach", price: 0, category: "نيش", desc: "خوخ غني وناضج بلمسات دافئة من الروم والباتشولي.", notes: "خوخ | برتقال دموي | باتشولي", img: "" },
            { id: 12, name: "Xerjoff Erba Pura", price: 0, category: "نيش", desc: "قنبلة الفواكه الاستوائية المنعشة مع المسك الأبيض.", notes: "فواكه استوائية | مسك أبيض", img: "" },
            { id: 13, name: "Xerjoff Naxos", price: 0, category: "نيش", desc: "لوحة فنية تجمع العسل الفاخر والتبغ واللافندر.", notes: "عسل | تبغ | لافندر | قرفة", img: "" },
            { id: 14, name: "Xerjoff Accento", price: 0, category: "نيش", desc: "أناقة الأناناس والصفير والمسك الثابت بالحيوية.", notes: "أناناس | صفير | مسك | فانيليا", img: "" },
            { id: 15, name: "MFK Grand Soir", price: 0, category: "نيش", desc: "عنبر ملكي دافئ وفخم يناسب السهرات الباردة.", notes: "عنبر | فانيليا | لاباندا", img: "" },
            { id: 16, name: "MFK Aqua Universalis", price: 0, category: "نيش", desc: "رائحة النظافة المطلقة والمنعشة كالقميص الأبيض.", notes: "حمضيات | زنابق الوادي | زهور", img: "" },
            { id: 17, name: "Creed Silver Mountain", price: 0, category: "نيش", desc: "انتعاش الجبال الثلجية والشاي الأخضر والكشمش.", notes: "شاي أخضر | كشمش | مسك", img: "" },
            { id: 18, name: "Creed Millesime Imperial", price: 0, category: "نيش", desc: "فخامة الفواكه البحرية المالحة والأخشاب المنعشة.", notes: "ملح بحري | فواكه | خشب صندل", img: "" },
            { id: 19, name: "Creed Green Irish Tweed", price: 0, category: "نيش", desc: "كلاسيكية الريف الأخضر بنوتات الفريزيا والسوسن.", notes: "إريش | لويزة | خشب ساج", img: "" },
            { id: 20, name: "Initio Oud for Greatness", price: 0, category: "نيش", desc: "قوة العود الطبيعي الممزوج بالزعفران وجوزة الطيب.", notes: "عود طبيعي | زعفران | جوزة الطيب", img: "" },
            { id: 21, name: "Initio Side Effect", price: 0, category: "نيش", desc: "مزيج مسكر ومدمن من الروم والفانيليا والتبغ.", notes: "روم | فانيليا | تبغ | قرفة", img: "" },
            { id: 22, name: "Byredo Gypsy Water", price: 0, category: "نيش", desc: "روح الطبيعة الحرة بنوتات الصنوبر والفانيليا.", notes: "صنوبر | برغموت | فانيليا خشبية", img: "" },
            { id: 23, name: "Byredo Bal d'Afrique", price: 0, category: "نيش", desc: "لوحة عطرية دافئة تمزج زهر البرتقال بالأرز.", notes: "زهر برتقال | ليمون | عنبر", img: "" },
            { id: 24, name: "Mancera Cedrat Boise", price: 0, category: "نيش", desc: "انتعاش الليمون والحمضيات مع قاعدة خشبية.", notes: "ليمون | كشمش أسود | أخشاب", img: "" },
            { id: 25, name: "Mancera Red Tobacco", price: 0, category: "نيش", desc: "تبغ أحمر ناري قوي وثابت جداً مع التوابل.", notes: "تبغ | قرفة | العود الأبيض", img: "" },
            { id: 26, name: "Montale Intense Cafe", price: 0, category: "نيش", desc: "قهوة عربية دافئة ممزوجة بعبق الورد التركي.", notes: "قهوة | ورد تركي | فانيليا مسك", img: "" },
            { id: 27, name: "Orto Parisi Megamare", price: 0, category: "نيش", desc: "عطر بحري عميق ومالح ذو ثبات وفوحان خارق.", notes: "نوتات بحرية | طحالب | أعشاب", img: "" },
            { id: 28, name: "Nasomatto Black Afgano", price: 0, category: "نيش", desc: "الغموض الداكن بنوتات التبغ والأخشاب المدخنة.", notes: "تبغ فاخر | أخشاب العود", img: "" },
            { id: 29, name: "Tiziana Terenzi Kirke", price: 0, category: "نيش", desc: "فاكهة العاطفة الاستوائية الساحرة مع المسك.", notes: "فاكهة العاطفة | خوخ | مسك", img: "" },
            { id: 30, name: "Amouage Interlude Man", price: 0, category: "نيش", desc: "عطر الأساطير والدخان والبخور والأخشاب الشرقية.", notes: "بخور | عود | جلد", img: "" },
            { id: 31, name: "Creed Aventus", price: 0, category: "رجالي", desc: "ملك العطور الرجالية بنوتات الأناناس والأخشاب.", notes: "أناناس | أخشاب الأرز | مسك", img: "" },
            { id: 32, name: "Bleu de Chanel EDP", price: 0, category: "رجالي", desc: "أناقة الحمضيات والبخور والأخشاب العطرية.", notes: "حمضيات | بخور | أخشاب صندل", img: "" },
            { id: 33, name: "Dior Sauvage Elixir", price: 0, category: "رجالي", desc: "تركيز مكثف وتوابل حارة فاخرة مع الخزامى.", notes: "قرفة | جوزة الطيب | خزامى", img: "" },
            { id: 34, name: "Dior Sauvage EDT", price: 0, category: "رجالي", desc: "البرغموت المنعش والأمبروكسان الجذاب لكل الأوقات.", notes: "برغموت | فلفل أسود | أمبروكسان", img: "" },
            { id: 35, name: "Acqua Di Gio Parfum", price: 0, category: "رجالي", desc: "انتعاش أمواج البحر العميقة مع البخور والأخشاب.", notes: "نوتات بحرية | إكليل الجبل | بخور", img: "" },
            { id: 36, name: "Armani Code Parfum", price: 0, category: "رجالي", desc: "فول التونكا الدافئ مع السوسن وأخشاب الأرز.", notes: "سوسن | فول تونكا | أخشاب أرز", img: "" },
            { id: 37, name: "Versace Eros EDP", price: 0, category: "رجالي", desc: "نعناع منعش مع التفاح الفانيليا وحبوب التونكا.", notes: "نعناع | تفاح حامض | فانيليا", img: "" },
            { id: 38, name: "Versace Dylan Blue", price: 0, category: "رجالي", desc: "حمضيات متوسطية منعشة مع البخور والمسك.", notes: "برغموت | جريب فروت | بخور", img: "" },
            { id: 39, name: "1 Million Elixir", price: 0, category: "رجالي", desc: "مزيج غني من الفانيليا والورد التركي والتونكا.", notes: "فانيليا | ورد تركي | تونكا", img: "" },
            { id: 40, name: "Invictus Victory", price: 0, category: "رجالي", desc: "انتعاش الليمون الحامض مع قوة الفانيليا والعنبر.", notes: "ليمون | فلفل وردي | فانيليا", img: "" },
            { id: 41, name: "Le Male Le Parfum", price: 0, category: "رجالي", desc: "هال وهيل وزهور السوسن مع الفانيليا الشرقية.", notes: "هيل | لافندر | فانيليا شرقية", img: "" },
            { id: 42, name: "Scandal Pour Homme", price: 0, category: "رجالي", desc: "كراميل حلو مع الميرمية والماندرين لإطلالة جريئة.", notes: "كراميل | ميرمية | نجيل الهند", img: "" },
            { id: 43, name: "Tom Ford Ombre Leather", price: 0, category: "رجالي", desc: "عبير الجلود الفاخرة النقية مع الهيل والياسمين.", notes: "جلد أسود | هيل | ياسمين", img: "" },
            { id: 44, name: "Tom Ford Noir Extreme", price: 0, category: "رجالي", desc: "توابل هندية وفانيليا غنية مع كولفي الحليب.", notes: "كولفي | توابل | فانيليا خشبية", img: "" },
            { id: 45, name: "Terre d'Hermes", price: 0, category: "رجالي", desc: "رائحة الأرض والمعادن وأشجار البرتقال والفلفل.", notes: "برتقال | فلفل | أخشاب الأرز", img: "" },
            { id: 46, name: "Bleu de Chanel Parfum", price: 0, category: "رجالي", desc: "أعلى درجات الفخامة الخشبية العطرية الناعمة.", notes: "قشر ليمون | خشب صندل | أرز", img: "" },
            { id: 47, name: "YSL Y EDP", price: 0, category: "رجالي", desc: "تفاح مقرمش مع الميرمية والزنجبيل لإطلالة شبابية.", notes: "تفاح | زنجبيل | ميرمية", img: "" },
            { id: 48, name: "YSL La Nuit de L'Homme", price: 0, category: "رجالي", desc: "عطر السهرات الرومانسي بالهيل واللافندر والأخشاب.", notes: "هيل | لافندر | خشب الأرز", img: "" },
            { id: 49, name: "D&G The One EDP", price: 0, category: "رجالي", desc: "دفء التبغ والعنبر والجريب فروت لإطلالة أنيقة.", notes: "جريب فروت | كزبرة | تبغ وعنبر", img: "" },
            { id: 50, name: "D&G Light Blue Intense", price: 0, category: "رجالي", desc: "انتعاش مياه البحر المتوسط الحامضة والمنعشة.", notes: "جريب فروت | مياه بحر | مسك", img: "" },
            { id: 51, name: "Prada Luna Rossa Carbon", price: 0, category: "رجالي", desc: "معادن باردة ومعدنية مع اللافندر والخزامى.", notes: "لافندر | فلفل معدني | باتشولي", img: "" },
            { id: 52, name: "Bvlgari Man In Black", price: 0, category: "رجالي", desc: "توابل داكنة وجلود فاخرة مع الروم والعنبر.", notes: "روم | توابل | جلد وعنبر", img: "" },
            { id: 53, name: "Montblanc Explorer", price: 0, category: "رجالي", desc: "برغموت إيطالي منعش مع نجيل الهند والأخشاب.", notes: "برغموت | نجيل الهند | جلد", img: "" },
            { id: 54, name: "Azzaro Most Wanted", price: 0, category: "رجالي", desc: "زنجبيل حار مع الشوكولاتة وفانيليا البوربون.", notes: "زنجبيل | روائح خشبية | فانيليا", img: "" },
            { id: 55, name: "Bad Boy Le Parfum", price: 0, category: "رجالي", desc: "القنب والمريمية والجلود في توليفة عصرية.", notes: "قنب | مريمية | جلود سوداء", img: "" },
            { id: 56, name: "Lalique Encre Noire", price: 0, category: "رجالي", desc: "سيد النوتات الخشبية والنجيل الهند الداكن.", notes: "نجيل هندي | سرو | مسك", img: "" },
            { id: 57, name: "Davidoff Cool Water", price: 0, category: "رجالي", desc: "الكلاسيكية المنعشة بنوتات النعناع ومياه البحر.", notes: "نعناع | ماء البحر | لافندر", img: "" },
            { id: 58, name: "L'Eau d'Issey Pour Homme", price: 0, category: "رجالي", desc: "يوسوكي ياباني وحمضيات خفيفة مع نوتات خشبية.", notes: "يوسو | ليمون | توابل مائية", img: "" },
            { id: 59, name: "Burberry Hero EDP", price: 0, category: "رجالي", desc: "أرز أطلسي دافئ مع إبرة الصقنوبر والجاوي.", notes: "أرز الأطلس | صنوبر | جاوي", img: "" },
            { id: 60, name: "Polo Blue Parfum", price: 0, category: "رجالي", desc: "يوسفي ونوتات أكسجين بحرية مع نجيل الهند.", notes: "يوسفي | مريمية | نجيل الهند", img: "" },
            { id: 61, name: "Dior J'adore EDP", price: 0, category: "نسائي", desc: "باقة زهرية أنثوية خالدة من الياسمين والورد.", notes: "ياسمين | ورد جوري | كمثرى", img: "" },
            { id: 62, name: "YSL Libre Intense", price: 0, category: "نسائي", desc: "لافندر فرنسي ناعم مع أوركيد الفانيليا الدافئة.", notes: "لافندر | أوركيد | فانيليا", img: "" },
            { id: 63, name: "Chanel Coco Mademoiselle", price: 0, category: "نسائي", desc: "أناقة البرتقال المنعش مع الورد والباتشولي.", notes: "برتقال | ورد | باتشولي", img: "" },
            { id: 64, name: "Chanel No. 5", price: 0, category: "نسائي", desc: "عطر الأساطير الألدهيدي الزهري الخالد.", notes: "ألدهيدات | ياسمين | ورد | مسك", img: "" },
            { id: 65, name: "Good Girl EDP", price: 0, category: "نسائي", desc: "توليفة اللوز والقهوة ومسك الروم الأيقونية.", notes: "لوز | قهوة | مسك رومي | كاكاو", img: "" },
            { id: 66, name: "Lancome La Vie Est Belle", price: 0, category: "نسائي", desc: "سعادة السوسن والياسمين مع حلاوة الفانيليا.", notes: "سوسن | ياسمين | فانيليا", img: "" },
            { id: 67, name: "Lancome Idole", price: 0, category: "نسائي", desc: "ورد نقي مع الياسمين والكمثرى لإطلالة مشرقة.", notes: "ورد أخضر | ياسمين | كمثرى", img: "" },
            { id: 68, name: "Armani My Way", price: 0, category: "نسائي", desc: "زهر البرتقال ومسك الروم الهندي مع الفانيليا.", notes: "زهر برتقال | مسك رومي | فانيليا", img: "" },
            { id: 69, name: "Armani Si EDP", price: 0, category: "نسائي", desc: "رحيق الكشمش الأسود مع الورد وخشب الأرز.", notes: "كشمش أسود | ورد فريزيا | باتشولي", img: "" },
            { id: 70, name: "Donna Born In Roma", price: 0, category: "نسائي", desc: "ياسمين فاخر مع فانيليا دافئة ولمسات خشبية.", notes: "ياسمين | فانيليا | أخشاب", img: "" },
            { id: 71, name: "Marc Jacobs Daisy", price: 0, category: "نسائي", desc: "فراولة برية وفريزيا وبنفسج لعطر مرح ومنعش.", notes: "فراولة | بنفسج | ياسمين", img: "" },
            { id: 72, name: "Gucci Bloom", price: 0, category: "نسائي", desc: "حديقة أزهار بيضاء غنية بعبق مسك الروم والياسمين.", notes: "مسك رومي | ياسمين", img: "" },
            { id: 73, name: "Gucci Flora Gardenia", price: 0, category: "نسائي", desc: "زهرة الغاردينيا البيضاء مع زهر الكمثرى والسكر.", notes: "غاردينيا | زهر كمثرى | سكر بني", img: "" },
            { id: 74, name: "Olympéa EDP", price: 0, category: "نسائي", desc: "فانيليا مالحة فريدة مع زهر الياسمين واليوسفي.", notes: "فانيليا مالحة | ياسمين مائي", img: "" },
            { id: 75, name: "Flowerbomb EDP", price: 0, category: "نسائي", desc: "قنبلة أزهار مذهلة من الشاي والياسمين والورد.", notes: "شاي | ياسمين | ورد | باتشولي", img: "" },
            { id: 76, name: "Tom Ford Black Orchid", price: 0, category: "نسائي", desc: "أوركيد سوداء داكنة مع الشوكولاتة والتوابل.", notes: "أوركيد سوداء | شوكولاتة | كمأة", img: "" },
            { id: 77, name: "Tom Ford Velvet Orchid", price: 0, category: "نسائي", desc: "زهور أوركيد مخملية مع العسل والروم والفانيليا.", notes: "عسل | روم | أوركيد مخملي", img: "" },
            { id: 78, name: "Burberry Her EDP", price: 0, category: "نسائي", desc: "توت بري وفراولة مقرمشة مع قاعدة مسكية.", notes: "توت بري | فراولة | مسك وعنبر", img: "" },
            { id: 79, name: "Versace Bright Crystal", price: 0, category: "نسائي", desc: "رمان منعش مع زهر الياسمين والفاوانيا الصيفية.", notes: "رمان | فاوانيا | مسك وعنبر", img: "" },
            { id: 80, name: "La Belle EDP", price: 0, category: "نسائي", desc: "كمثرى ناضجة وحسية مع فانيليا ونوتات دافئة.", notes: "كمثرى | نجيل الهند | فانيليا", img: "" },
            { id: 81, name: "Prada Paradoxe", price: 0, category: "نسائي", desc: "زهر البرتقال والعنبر الأبيض في زجاجة عصرية.", notes: "زهر برتقال | عنبر أبيض | مسك", img: "" },
            { id: 82, name: "Twilly d'Hermes", price: 0, category: "نسائي", desc: "زنجبيل منعش مع مسك الروم وخشب الصندل.", notes: "زنجبيل | مسك رومي | خشب صندل", img: "" },
            { id: 83, name: "Narciso Rodriguez For Her", price: 0, category: "نسائي", desc: "مسك مصري ساحر مع زهر البرتقال الناعم.", notes: "مسك | زهر برتقال | أوسمانثوس", img: "" },
            { id: 84, name: "CK Euphoria", price: 0, category: "نسائي", desc: "رمان وأوركيد أسود مع الماهوجني لإطلالة غامضة.", notes: "رمان | أوركيد أسود | ماهوجني", img: "" },
            { id: 85, name: "Jo Malone English Pear", price: 0, category: "نسائي", desc: "كمثرى إنجليزية ناضجة مع فريزيا بيضاء والأخشاب.", notes: "كمثرى | فريزيا | باتشولي", img: "" },
            { id: 86, name: "Chloe EDP", price: 0, category: "نسائي", desc: "ورد بلغاري فاخر وبودرة ناعمة مع الفاوانيا.", notes: "ورد بلغاري | فاوانيا | عسل", img: "" },
            { id: 87, name: "DKNY Be Delicious", price: 0, category: "نسائي", desc: "تفاح أخضر مقرمش ومنعش للغاية لأجواء الصيف.", notes: "تفاح أخضر | خيار | ماغنوليا", img: "" },
            { id: 88, name: "Alien Mugler", price: 0, category: "نسائي", desc: "ياسمين غامض وعميق مع أخشاب الكشمير والعنبر.", notes: "ياسمين | أخشاب كشمير | عنبر", img: "" },
            { id: 89, name: "Angel Mugler", price: 0, category: "نسائي", desc: "شوكولاتة داكنة وباتشولي وفواكه حمراء.", notes: "باتشولي | شوكولاتة | توت بري", img: "" },
            { id: 90, name: "Signorina EDP", price: 0, category: "نسائي", desc: "توت وفلفل وردي مع الباناكوتا والمسك الناعم.", notes: "فلفل وردي | باناكوتا | باتشولي", img: "" },
            { id: 91, name: "دهن العود المعتق الملكي", price: 0, category: "شرقي", desc: "أصالة العود الكمبودي المعتق بثبات وفوحان عالي.", notes: "عود كمبودي | عنبر | خشب صندل", img: "" },
            { id: 92, name: "مسك الختام الأبيض", price: 0, category: "شرقي", desc: "مسك نقي وبودري مخملي يمنح شعور النظافة.", notes: "مسك أبيض | بودرة | ورد طائفي", img: "" },
            { id: 93, name: "عنبر الملوك الخالص", price: 0, category: "شرقي", desc: "دفء العنبر الشرقي الأصيل الممزوج بالتوابل.", notes: "عنبر دافئ | زعفران | هيل", img: "" },
            { id: 94, name: "ورد طائفي معتق", price: 0, category: "شرقي", desc: "عبير الورد الطائفي الفاخر المقطر بعناية.", notes: "ورد طائفي | دهن عود | مسك", img: "" },
            { id: 95, name: "خلاصة العود الهندي", price: 0, category: "شرقي", desc: "عبق أخشاب العود الهندي القديم للمجالس.", notes: "عود هندي معتق | بخور | جلد", img: "" },
            { id: 96, name: "مسك العروس الفاخر", price: 0, category: "شرقي", desc: "مزيج كريمي أنثوي من المسك والفانيليا.", notes: "مسك أبيض | فانيليا كريمية", img: "" },
            { id: 97, name: "لبان الدكور العماني", price: 0, category: "شرقي", desc: "بخور لبان الدكور الملكي المنقى لأجواء المنازل.", notes: "لبان عماني | صمغ | بخور", img: "" },
            { id: 98, name: "مخلط الملك الفاخر", price: 0, category: "شرقي", desc: "توليفة تجمع الورد والزعفران والعود والعنبر.", notes: "زعفران | ورد | عود | عنبر", img: "" },
            { id: 99, name: "مسك الرمان السحري", price: 0, category: "شرقي", desc: "انتعاش الرمان الحلو الممزوج بعبق المسك.", notes: "رمان أحمر | مسك أبيض | توت", img: "" },
            { id: 100, name: "توليفة فيلقيت الخاصة", price: 0, category: "شرقي", desc: "العطر الحصري والخاص بمتجرنا في طرابلس.", notes: "توليفة سرية | عود وخشب صندل", img: "" }
        ];

        let perfumesList = JSON.parse(localStorage.getItem('velvet_perfumes_db')) || defaultPerfumes;
        let currentFilter = 'الكل';
        let selectedCart = [];

        function saveStateToLocalStorage() {
            localStorage.setItem('velvet_perfumes_db', JSON.stringify(perfumesList));
        }

        function exportData() {
            const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(perfumesList));
            const downloadAnchor = document.createElement('a');
            downloadAnchor.setAttribute("href", dataStr);
            downloadAnchor.setAttribute("download", "velvet_perfumes_backup.json");
            document.body.appendChild(downloadAnchor);
            downloadAnchor.click();
            downloadAnchor.remove();
        }

        function importData(element) {
            const file = element.files[0];
            if (file) {
                const reader = new FileReader();
                reader.readAsText(file, "UTF-8");
                reader.onload = function (evt) {
                    try {
                        const importedList = JSON.parse(evt.target.result);
                        if (Array.isArray(importedList)) {
                            perfumesList = importedList;
                            saveStateToLocalStorage();
                            displayPerfumes(perfumesList);
                            alert("تم استعادة وتحديث جميع الأسعار والصور بنجاح!");
                        } else {
                            alert("الملف غير صالح.");
                        }
                    } catch (e) {
                        alert("حدث خطأ أثناء قراءة الملف.");
                    }
                }
            }
        }

        function displayPerfumes(items) {
            const container = document.getElementById('products-container');
            container.innerHTML = '';

            let filteredItems = items;
            if (currentFilter !== 'الكل') {
                filteredItems = items.filter(p => p.category === currentFilter);
            }

            if (filteredItems.length === 0) {
                container.innerHTML = `<div class="empty-state"><p>لا توجد عطور مضافة هنا.</p></div>`;
                return;
            }

            filteredItems.forEach(item => {
                const card = document.createElement('div');
                card.className = 'product-card';
                
                const imgSrc = item.img ? item.img : 'https://images.unsplash.com/photo-1588405748880-12d1d2a59f75?auto=format&fit=crop&q=80&w=400';

                card.innerHTML = `
                    <div class="product-badge">${item.category}</div>
                    <img src="${imgSrc}" class="product-img" alt="${item.name}">
                    
                    <div class="img-update-box" style="display: ${isAdminMode ? 'block' : 'none'};">
                        <label style="font-size: 10px; color: var(--accent-gold-dark); cursor: pointer; font-weight: bold;">
                            📷 تغيير الصورة
                            <input type="file" accept="image/*" style="display: none;" onchange="updatePerfumeImage(${item.id}, this)">
                        </label>
                    </div>

                    <div class="product-info">
                        <div class="product-title">${item.name}</div>
                        <div class="product-desc">${item.desc}</div>
                        <div class="product-notes">${item.notes}</div>
                        
                        <div style="margin-bottom: 8px; display: ${isAdminMode ? 'flex' : 'none'}; align-items: center; gap: 4px;">
                            <span style="font-size: 10px; color: var(--text-muted);">التصنيف:</span>
                            <select onchange="changePerfumeCategory(${item.id}, this.value)" style="font-size: 10px; padding: 2px; border: 1px solid var(--border-color); border-radius: 4px; background: var(--bg-color); outline: none;">
                                <option value="شرقي" ${item.category === 'شرقي' ? 'selected' : ''}>شرقي</option>
                                <option value="رجالي" ${item.category === 'رجالي' ? 'selected' : ''}>رجالي</option>
                                <option value="نسائي" ${item.category === 'نسائي' ? 'selected' : ''}>نسائي</option>
                                <option value="نيش" ${item.category === 'نيش' ? 'selected' : ''}>نيش</option>
                            </select>
                        </div>

                        <div class="product-footer">
                            <div>
                                <span class="product-price-display" style="display: ${isAdminMode ? 'none' : 'inline'};">${item.price} د.ل</span>
                                <input type="number" class="product-price-input" style="display: ${isAdminMode ? 'inline-block' : 'none'};" value="${item.price}" onchange="updatePerfumePrice(${item.id}, this.value)">
                                <span style="font-size: 10px; font-weight: bold; color: var(--accent-gold-dark); display: ${isAdminMode ? 'inline' : 'none'};">د.ل</span>
                            </div>
                            <div class="actions-group">
                                <button class="btn-order" onclick="addToCart(${item.id})">+ طلب</button>
                                <button class="btn-delete" style="display: ${isAdminMode ? 'block' : 'none'};" onclick="deletePerfume(${item.id})">حذف</button>
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
                    const MAX_WIDTH = 350;
                    const scaleFactor = MAX_WIDTH / img.width;
                    canvas.width = MAX_WIDTH;
                    canvas.height = img.height * scaleFactor;

                    const ctx = canvas.getContext('2d');
                    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
                    
                    const compressedDataUrl = canvas.toDataURL('image/jpeg', 0.5);
                    callback(compressedDataUrl);
                }
            }
        }

        function updatePerfumeImage(id, inputElement) {
            if (inputElement.files && inputElement.files[0]) {
                compressAndProcessImage(inputElement.files[0], function(compressedImg) {
                    const item = perfumesList.find(p => p.id === id);
                    if (item) {
                        item.img = compressedImg;
                        saveStateToLocalStorage();
                        displayPerfumes(perfumesList);
                    }
                });
            }
        }

        function addNewPerfume() {
            const name = document.getElementById('new-name').value.trim();
            const price = document.getElementById('new-price').value.trim() || 0;
            const cat = document.getElementById('new-cat').value;
            const notes = document.getElementById('new-notes').value.trim() || "تركيبة مميزة";
            const desc = document.getElementById('new-desc').value.trim() || "عطر فاخر ومميز.";
            const fileInput = document.getElementById('new-img-file');

            if(!name) {
                alert('ادخل اسم العطر أولاً.');
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
            saveStateToLocalStorage();
            displayPerfumes(perfumesList);
            
            document.getElementById('new-name').value = '';
            document.getElementById('new-price').value = '';
            document.getElementById('new-notes').value = '';
            document.getElementById('new-desc').value = '';
            document.getElementById('new-img-file').value = '';
            document.getElementById('admin-panel').style.display = 'none';
            isAdminMode = false;
            displayPerfumes(perfumesList);

            alert(`تم إضافة ${name}!`);
        }

        function updatePerfumePrice(id, newPrice) {
            const item = perfumesList.find(p => p.id === id);
            if(item) {
                item.price = parseFloat(newPrice) || 0;
                saveStateToLocalStorage();
            }
        }

        function deletePerfume(id) {
            if (confirm('تأكيد حذف هذا العطر؟')) {
                perfumesList = perfumesList.filter(p => p.id !== id);
                saveStateToLocalStorage();
                displayPerfumes(perfumesList);
            }
        }

        function changePerfumeCategory(id, newCat) {
            const perfume = perfumesList.find(p => p.id === id);
            if (perfume) {
                perfume.category = newCat;
                saveStateToLocalStorage();
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
            const item = perfumesList.find(p => p.id === Number(id));
            if(item) {
                selectedCart.push({ name: item.name, price: item.price });
                document.getElementById('cart-count').innerText = selectedCart.length;
                alert(`تمت إضافة "${item.name}" إلى السلة.`);
            }
        }

        function openCheckoutModal() {
            if(selectedCart.length === 0) {
                alert('السلة فارغة! الرجاء اختيار عطر واحد على الأقل للطلب.');
                return;
            }
            document.getElementById('checkout-modal').style.display = 'flex';
        }

        function closeCheckoutModal() {
            document.getElementById('checkout-modal').style.display = 'none';
        }

        function submitOrderToMessenger() {
            const name = document.getElementById('cust-name').value.trim();
            const phone = document.getElementById('cust-phone').value.trim();
            const address = document.getElementById('cust-address').value.trim();

            if(!name || !phone || !address) {
                alert('الرجاء إدخال (الاسم، رقم الهاتف، وعنوان التوصيل) لتأكيد الطلب.');
                return;
            }

            let totalPrice = 0;
            let summaryText = `أهلاً VELVET PARFUMS 👋 ، أرغب في طلب العطور التالية مع التوصيل:\n\n`;
            summaryText += `👤 اسم الزبون: ${name}\n`;
            summaryText += `📞 رقم الهاتف: ${phone}\n`;
            summaryText += `📍 عنوان التوصيل: ${address}\n\n--- العطور المطلوبة ---\n`;

            selectedCart.forEach((item, index) => {
                summaryText += `${index + 1}. ${item.name} - ${item.price} د.ل\n`;
                totalPrice += item.price;
            });

            summaryText += `\nإجمالي المبلغ مع التوصيل: ${totalPrice} د.ل`;
            
            const messengerUrl = `https://m.me/${FB_PAGE_ID}?text=${encodeURIComponent(summaryText)}`;
            window.open(messengerUrl, '_blank');
            closeCheckoutModal();
        }

        displayPerfumes(perfumesList);
    </script>
</body>
</html>
