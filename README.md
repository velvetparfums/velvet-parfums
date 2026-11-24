<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>VELVET PARFUMS | عطور فيلقيت في طرابلس</title>
    <meta name="description" content="متجر فيلقيت للعطور في طرابلس، ليبيا. وفرنا لك أرقى العطور العالمية، عطور النيش، والشرقية الأصلية 100% مع توصيل مجاني سريع داخل طرابلس.">
    <meta name="keywords" content="عطور طرابلس, شراء عطور في ليبيا, عطور أصلية طرابلس, متجر عطور نيش ليبيا, Velvet Parfums">
    <meta name="geo.region" content="LY-TB">
    <meta name="geo.placename" content="Tripoli">
    
    <!-- وسوم فيسبوك وفتح الروابط (Open Graph) -->
    <meta property="og:title" content="VELVET PARFUMS | أفخم العطور الأصلية في طرابلس وليبيا">
    <meta property="og:description" content="تنسيقات عطور نيش وعالمية أصلية 100% مع توصيل مجاني داخل طرابلس. اطلب الآن عبر المتجر أو الماسنجر.">
    <meta property="og:image" content="https://images.unsplash.com/photo-1588405748880-12d1d2a59f75?auto=format&fit=crop&q=80&w=400">
    <meta property="og:type" content="website">
    <meta property="og:locale" content="ar_LY">

    <!-- بيانات الموقع الجغرافي ونشاط المتجر (Schema.org) -->
    <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "PerfumeShop",
      "name": "VELVET PARFUMS",
      "description": "متجر متخصص في بيع العطور الأصلية والنيش والعطور الشرقية في طرابلس ليبيا",
      "address": {
        "@type": "PostalAddress",
        "addressLocality": "Tripoli",
        "addressRegion": "Tripoli",
        "addressCountry": "LY"
      },
      "currenciesAccepted": "LYD",
      "priceRange": "$$"
    }
    </script>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;700&family=Tajawal:wght@300;400;500;700&display=swap" rel="stylesheet">
    
    <!-- Firebase SDKs -->
    <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.22.0/firebase-database-compat.js"></script>

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

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Tajawal', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background-color: var(--bg-color); color: var(--text-dark); line-height: 1.5; padding-bottom: 100px; }

        header {
            background-color: var(--card-bg);
            padding: 15px 12px;
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 100;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .header-title-container { text-align: center; cursor: pointer; user-select: none; }
        .logo-svg { width: 48px; height: 48px; margin: 0 auto; display: block; }
        .brand-title { font-family: 'Cinzel', serif; font-size: 16px; font-weight: 700; color: var(--accent-gold-dark); margin-top: 2px; }
        .brand-subtitle { font-family: 'Cinzel', serif; font-size: 8px; letter-spacing: 1.5px; color: var(--text-muted); text-transform: uppercase; }

        /* شريط المميزات والأيقونات */
        .features-bar {
            background-color: #f2eee9;
            border-bottom: 1px solid var(--border-color);
            padding: 10px 15px;
            display: flex;
            justify-content: space-around;
            align-items: center;
            gap: 10px;
        }
        .feature-item {
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 11px;
            font-weight: 700;
            color: var(--accent-gold-dark);
            text-align: center;
        }
        .feature-item span { font-size: 16px; }

        .container { width: 100%; max-width: 1100px; margin: 0 auto; padding: 12px; }

        /* شريط البحث وفلتر الشركات وزر الطلب الخاص */
        .search-filter-row {
            display: flex;
            gap: 8px;
            margin-bottom: 12px;
            flex-wrap: wrap;
        }
        .search-box { flex: 1; min-width: 170px; }
        .search-input {
            width: 100%;
            padding: 11px 16px;
            border: 1px solid var(--border-color);
            border-radius: 25px;
            font-size: 13px;
            background: var(--card-bg);
            outline: none;
            box-shadow: 0 2px 8px rgba(0,0,0,0.02);
            transition: border-color 0.2s;
        }
        .search-input:focus { border-color: var(--accent-gold); }

        .brand-select-box { min-width: 135px; }
        .brand-select {
            width: 100%;
            padding: 11px 14px;
            border: 1px solid var(--accent-gold);
            border-radius: 25px;
            font-size: 13px;
            font-weight: bold;
            color: var(--accent-gold-dark);
            background: var(--card-bg);
            outline: none;
            cursor: pointer;
        }

        .btn-custom-perfume-top {
            background: linear-gradient(135deg, var(--accent-gold), var(--accent-gold-dark));
            color: white;
            border: none;
            padding: 11px 16px;
            border-radius: 25px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
            white-space: nowrap;
            box-shadow: 0 3px 10px rgba(179, 147, 89, 0.3);
        }

        .admin-banner {
            display: none;
            background: #ffffff;
            border: 2px solid var(--accent-gold);
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .admin-banner h3 { color: var(--accent-gold-dark); font-size: 15px; margin-bottom: 12px; text-align: center; }

        /* بطاقة إحصائيات الزوار السرية */
        .stats-dashboard {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
            margin-bottom: 15px;
            background: #f9f7f2;
            padding: 12px;
            border-radius: 10px;
            border: 1px solid var(--accent-gold);
        }
        .stat-card {
            background: #ffffff;
            padding: 10px;
            border-radius: 8px;
            text-align: center;
            border: 1px solid var(--border-color);
        }
        .stat-label {
            font-size: 11px;
            color: var(--text-muted);
            font-weight: bold;
            display: block;
            margin-bottom: 4px;
        }
        .stat-number {
            font-size: 22px;
            font-weight: 800;
            color: var(--accent-gold-dark);
        }
        .stat-date-note {
            grid-column: 1 / -1;
            text-align: center;
            font-size: 10px;
            color: var(--text-muted);
        }

        .admin-form-grid { display: flex; flex-direction: column; gap: 10px; margin-bottom: 12px; }
        .admin-row-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
        .admin-form-grid input, .admin-form-grid select, .admin-form-grid textarea {
            width: 100%; padding: 10px; border: 1px solid var(--border-color); border-radius: 8px; font-size: 13px; outline: none; background: var(--bg-color);
        }

        .file-input-wrapper { background: #f2eee9; padding: 12px; border-radius: 8px; text-align: center; border: 1px dashed var(--accent-gold); }

        .btn-update-live {
            background-color: var(--success-color);
            color: white;
            border: none;
            padding: 14px;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            width: 100%;
            font-size: 15px;
            margin-top: 5px;
            box-shadow: 0 4px 10px rgba(39, 174, 96, 0.3);
        }

        .filter-section-label {
            font-size: 11px;
            font-weight: bold;
            color: var(--text-muted);
            margin-bottom: 5px;
            display: block;
        }

        .categories-nav, .brands-nav { display: flex; gap: 7px; margin-bottom: 12px; overflow-x: auto; padding-bottom: 4px; }
        .categories-nav::-webkit-scrollbar, .brands-nav::-webkit-scrollbar { display: none; }
        
        .cat-btn { background-color: var(--card-bg); border: 1px solid var(--border-color); padding: 6px 15px; border-radius: 20px; cursor: pointer; font-size: 12px; color: var(--text-dark); white-space: nowrap; flex-shrink: 0; }
        .cat-btn.active { background-color: var(--accent-gold); color: white; border-color: var(--accent-gold); font-weight: bold; }

        .brand-btn { background-color: #f2eee9; border: 1px solid var(--border-color); padding: 5px 13px; border-radius: 16px; cursor: pointer; font-size: 11px; font-weight: 600; color: var(--text-dark); white-space: nowrap; flex-shrink: 0; transition: all 0.2s; }
        .brand-btn.active { background-color: var(--text-dark); color: #f9f7f2; border-color: var(--text-dark); }

        .products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(155px, 1fr)); gap: 12px; margin-top: 8px; }
        @media (min-width: 600px) { .products-grid { grid-template-columns: repeat(auto-fill, minmax(240px, 1fr)); gap: 20px; } }

        .product-card { background-color: var(--card-bg); border-radius: 12px; overflow: hidden; border: 1px solid var(--border-color); box-shadow: var(--shadow); display: flex; flex-direction: column; position: relative; }
        .product-img { width: 100%; height: 150px; object-fit: cover; background-color: #f7f5f0; }
        @media (min-width: 600px) { .product-img { height: 220px; } }

        .img-update-box { display: none; padding: 5px; background: #f2eee9; text-align: center; border-bottom: 1px solid var(--border-color); }
        .product-info { padding: 10px; display: flex; flex-direction: column; flex-grow: 1; }
        
        .product-badge { position: absolute; top: 8px; right: 8px; background: rgba(139, 112, 59, 0.92); color: white; padding: 2px 8px; border-radius: 12px; font-size: 10px; font-weight: bold; z-index: 5; }
        .product-size-badge { position: absolute; top: 8px; left: 8px; background: rgba(44, 42, 41, 0.88); color: #f9f7f2; padding: 2px 8px; border-radius: 12px; font-size: 10px; font-weight: bold; z-index: 5; direction: ltr; }
        
        .product-brand-tag { font-size: 10px; font-weight: 700; color: var(--accent-gold); text-transform: uppercase; letter-spacing: 0.5px; margin-bottom: 2px; }
        .product-title { font-size: 13px; font-weight: 700; color: var(--text-dark); margin-bottom: 4px; }
        .product-desc { font-size: 11px; color: var(--text-muted); margin-bottom: 6px; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
        .product-notes { background: var(--bg-color); padding: 4px 6px; border-radius: 4px; font-size: 10px; color: var(--accent-gold-dark); margin-bottom: 8px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }

        .admin-edit-fields { display: flex; flex-direction: column; gap: 4px; margin-bottom: 6px; background: #faf8f5; padding: 6px; border-radius: 6px; border: 1px dashed var(--border-color); }
        .admin-edit-fields input, .admin-edit-fields select { font-size: 11px; padding: 3px 5px; border: 1px solid var(--border-color); border-radius: 4px; width: 100%; }

        .product-footer { display: flex; align-items: center; justify-content: space-between; margin-top: auto; padding-top: 6px; border-top: 1px solid var(--border-color); }
        .product-price-display { font-size: 14px; font-weight: bold; color: var(--accent-gold-dark); }
        .product-price-input { display: none; width: 60px; padding: 3px; border: 1px solid var(--border-color); border-radius: 4px; font-size: 12px; font-weight: bold; color: var(--accent-gold-dark); text-align: center; background: var(--bg-color); outline: none; }
        
        .btn-order { background-color: var(--accent-gold); color: white; border: none; padding: 6px 12px; border-radius: 6px; font-size: 11px; font-weight: bold; cursor: pointer; }
        .btn-delete { display: none; background-color: #fae1dd; color: var(--danger-color); border: 1px solid var(--danger-color); padding: 6px; border-radius: 6px; font-size: 10px; cursor: pointer; font-weight: bold; }

        /* صندوق عندما لا يجد الزبون عطره */
        .not-found-box {
            grid-column: 1 / -1;
            background: #ffffff;
            border: 2px dashed var(--accent-gold);
            border-radius: 14px;
            padding: 25px 15px;
            text-align: center;
            box-shadow: var(--shadow);
        }
        .not-found-box h4 {
            color: var(--accent-gold-dark);
            font-size: 16px;
            margin-bottom: 8px;
        }
        .not-found-box p {
            color: var(--text-muted);
            font-size: 13px;
            margin-bottom: 15px;
        }

        .cart-bar { position: fixed; bottom: 12px; left: 5%; width: 90%; background: var(--accent-gold-dark); color: white; padding: 12px 18px; border-radius: 30px; box-shadow: 0 8px 20px rgba(0,0,0,0.2); display: flex; align-items: center; justify-content: space-between; z-index: 99; cursor: pointer; font-weight: bold; font-size: 13px; }
        .cart-count { background: white; color: var(--accent-gold-dark); width: 22px; height: 22px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 12px; }

        .cart-modal, .checkout-modal, .custom-req-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.5); z-index: 1000; justify-content: center; align-items: center; padding: 15px; }
        .modal-content { background: white; padding: 20px; border-radius: 12px; width: 100%; max-width: 420px; box-shadow: 0 10px 30px rgba(0,0,0,0.2); max-height: 90vh; display: flex; flex-direction: column; overflow-y: auto; }
        .modal-content h3 { color: var(--accent-gold-dark); margin-bottom: 12px; font-size: 16px; text-align: center; }
        .cart-items-list { overflow-y: auto; max-height: 200px; margin-bottom: 12px; border-top: 1px solid var(--border-color); border-bottom: 1px solid var(--border-color); padding: 8px 0; }
        .cart-item-row { display: flex; justify-content: space-between; align-items: center; padding: 8px 4px; border-bottom: 1px dashed var(--border-color); font-size: 13px; }
        .btn-remove-item { background: #fae1dd; color: var(--danger-color); border: none; padding: 3px 8px; border-radius: 4px; font-size: 11px; cursor: pointer; font-weight: bold; }
        .cart-summary-box { font-size: 13px; font-weight: bold; margin-bottom: 15px; text-align: right; color: var(--accent-gold-dark); background: var(--bg-color); padding: 10px; border-radius: 8px; line-height: 1.6; }
        .checkout-form-group { margin-bottom: 10px; }
        .checkout-form-group label { display: block; font-size: 12px; margin-bottom: 4px; font-weight: bold; }
        .checkout-form-group input, .checkout-form-group select, .checkout-form-group textarea { width: 100%; padding: 9px; border: 1px solid var(--border-color); border-radius: 6px; font-size: 13px; outline: none; background: var(--bg-color); }

        .preview-custom-img {
            max-width: 120px;
            max-height: 120px;
            border-radius: 8px;
            margin: 8px auto 0;
            display: none;
            border: 1px solid var(--accent-gold);
        }

        footer { text-align: center; margin-top: 30px; padding: 15px; color: var(--text-muted); font-size: 11px; border-top: 1px solid var(--border-color); }
    </style>
</head>
<body>

    <header>
        <div class="header-title-container" id="logo-trigger">
            <svg class="logo-svg" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M 28 30 L 48 76 C 49 78 51 78 52 76 L 72 30 Q 74 25 68 25 C 65 25 62 27 60 32 L 50 58 L 40 32 C 38 27 35 25 32 25 Q 26 25 28 30 Z" fill="#B39359"/>
                <path d="M 50 32 C 58 32 68 37 68 46 C 68 55 58 60 50 60 L 50 53 C 56 53 62 49 62 46 C 62 42 56 38 50 38 Z" fill="#B39359"/>
            </svg>
            <div class="brand-title">VELVET PARFUMS</div>
            <div class="brand-subtitle">PREMIUM FRAGRANCES</div>
        </div>
    </header>

    <!-- شريط الأيقونات والمميزات -->
    <div class="features-bar">
        <div class="feature-item">
            <span>🚚</span> توصيل مجاني داخل طرابلس
        </div>
        <div class="feature-item">
            <span>✨</span> عطور أصلية 100%
        </div>
    </div>

    <div class="container">

        <!-- لوحة الإدارة -->
        <div class="admin-banner" id="admin-panel">
            <h3>✨ لوحة الإدارة السريعة</h3>

            <!-- قسم إحصائيات الزوار (سري للمشرف فقط) -->
            <div class="stats-dashboard">
                <div class="stat-card">
                    <span class="stat-label">👥 زوار اليوم</span>
                    <span class="stat-number" id="today-visitors-count">0</span>
                </div>
                <div class="stat-card">
                    <span class="stat-label">🌍 إجمالي الزيارات الكلي</span>
                    <span class="stat-number" id="total-visitors-count">0</span>
                </div>
                <div class="stat-date-note" id="stats-today-date">تاريخ اليوم: --</div>
            </div>

            <div class="admin-form-grid">
                <input type="text" id="new-name" placeholder="اسم العطر الجديد (مثال: Sauvage Elixir)">
                
                <div class="admin-row-2">
                    <input type="text" id="new-brand" list="brands-datalist" placeholder="الشركة (مثال: Dior)">
                    <datalist id="brands-datalist"></datalist>
                    <input type="text" id="new-size" placeholder="الحجم بالملي (مثال: 100 مل)">
                </div>

                <div class="admin-row-2">
                    <input type="number" id="new-price" placeholder="السعر (د.ل)">
                    <select id="new-cat">
                        <option value="شرقي">شرقي</option>
                        <option value="رجالي">رجالي</option>
                        <option value="نسائي">نسائي</option>
                        <option value="نيش">نيش</option>
                    </select>
                </div>

                <input type="text" id="new-notes" placeholder="النوتات (برغموت، عود)">
                <textarea id="new-desc" placeholder="الوصف..."></textarea>
                
                <div class="file-input-wrapper">
                    <label style="display: block; font-weight: bold; color: var(--accent-gold-dark); font-size: 12px;">📷 اختر صورة العطر</label>
                    <input type="file" id="new-img-file" accept="image/*" style="margin-top: 5px;">
                </div>
            </div>
            
            <button class="btn-update-live" onclick="addNewPerfumeCloud()">🚀 نشر مباشر في المتجر</button>
        </div>

        <!-- شريط البحث السريع + قائمة الشركات + زر طلب عطر خاص -->
        <div class="search-filter-row">
            <div class="search-box">
                <input type="text" id="search-input" class="search-input" placeholder="🔍 ابحث بالاسم، الشركة، الحجم، أو النوتات..." oninput="filterPerfumes()">
            </div>
            <div class="brand-select-box">
                <select id="brand-select-dropdown" class="brand-select" onchange="setBrandFromDropdown(this.value)">
                    <option value="الكل">🏢 كل الشركات</option>
                </select>
            </div>
            <button class="btn-custom-perfume-top" onclick="openCustomPerfumeModal()">✨ طلب عطر خاص</button>
        </div>

        <!-- تصنيف حسب النوع -->
        <span class="filter-section-label">التصنيف:</span>
        <div class="categories-nav">
            <button class="cat-btn active" onclick="setCategory('الكل', this)">الكل</button>
            <button class="cat-btn" onclick="setCategory('شرقي', this)">شرقي</button>
            <button class="cat-btn" onclick="setCategory('رجالي', this)">رجالي</button>
            <button class="cat-btn" onclick="setCategory('نسائي', this)">نسائي</button>
            <button class="cat-btn" onclick="setCategory('نيش', this)">نيش</button>
        </div>

        <!-- تصنيف سريع حسب الشركات (يتحدث تلقائياً) -->
        <span class="filter-section-label">تصفح حسب الشركة (الماركة):</span>
        <div class="brands-nav" id="brands-nav-container"></div>

        <div class="products-grid" id="products-container"></div>

    </div>

    <!-- نافذة طلب عطر خاص غير متوفر -->
    <div class="custom-req-modal" id="custom-req-modal">
        <div class="modal-content">
            <h3>✨ طلب توفير عطر خاص</h3>
            <p style="font-size: 12px; color: var(--text-muted); text-align: center; margin-bottom: 12px;">
                أرسل لنا بيانات وصورة العطر الذي تبحث عنه وسنوفره لك بأفضل سعر في طرابلس.
            </p>

            <div class="checkout-form-group">
                <label>اسم العطر المطلوب: *</label>
                <input type="text" id="req-perfume-name" placeholder="مثال: Dior Homme Intense">
            </div>

            <div class="checkout-form-group">
                <label>الحجم بالملي (ml): *</label>
                <input type="text" id="req-perfume-size" placeholder="مثال: 100 مل أو 50 مل">
            </div>

            <div class="checkout-form-group">
                <label>📷 صورة العطر (اختياري - تسهل علينا المطابقة):</label>
                <div class="file-input-wrapper" style="padding: 8px;">
                    <input type="file" id="req-perfume-img" accept="image/*" onchange="previewCustomImage(this)">
                    <img id="custom-img-preview" class="preview-custom-img" alt="معاينة العطر">
                </div>
            </div>

            <div class="checkout-form-group">
                <label>اسمك ورقم هاتفك (للتواصل معك عند التوفير): *</label>
                <input type="text" id="req-cust-contact" placeholder="الاسم - 091XXXXXXX">
            </div>

            <div style="display: flex; gap: 8px; margin-top: 10px;">
                <button class="btn-update-live" id="btn-submit-custom" style="margin-top:0; background: var(--success-color);" onclick="submitCustomPerfumeRequest()">📤 إرسال الطلب عبر الماسنجر</button>
                <button class="btn-update-live" style="margin-top:0; background: #95a5a6;" onclick="closeCustomPerfumeModal()">إلغاء</button>
            </div>
        </div>
    </div>

    <div class="cart-bar" onclick="openCartModal()">
        <span>🛒 سلة الطلبات</span>
        <div class="cart-count" id="cart-count">0</div>
    </div>

    <div class="cart-modal" id="cart-modal">
        <div class="modal-content">
            <h3>🛍️ مراجعة سلة العطور</h3>
            <div class="cart-items-list" id="cart-items-list"></div>
            <div class="cart-summary-box" id="cart-summary-box">الإجمالي: 0 د.ل</div>
            <div style="display: flex; gap: 8px;">
                <button class="btn-update-live" style="margin-top:0; background: var(--success-color);" onclick="proceedToCheckout()">إتمام الطلب</button>
                <button class="btn-update-live" style="margin-top:0; background: #95a5a6;" onclick="closeCartModal()">إغلاق</button>
            </div>
        </div>
    </div>

    <div class="checkout-modal" id="checkout-modal">
        <div class="modal-content">
            <h3>📍 بيانات التوصيل والدفع</h3>
            <div class="checkout-form-group">
                <label>الاسم:</label>
                <input type="text" id="cust-name" placeholder="اسمك الكريم">
            </div>
            <div class="checkout-form-group">
                <label>رقم الهاتف:</label>
                <input type="tel" id="cust-phone" placeholder="091XXXXXXX">
            </div>
            <div class="checkout-form-group">
                <label>العنوان:</label>
                <textarea id="cust-address" placeholder="المنطقة والشارع..." style="height: 45px;"></textarea>
            </div>
            <div class="checkout-form-group">
                <label>طريقة الدفع:</label>
                <select id="payment-method">
                    <option value="كاش عند الاستلام">💵 كاش عند الاستلام</option>
                    <option value="حوالة مصرفية">🏦 حوالة مصرفية</option>
                </select>
            </div>
            <div style="display: flex; gap: 8px; margin-top: 10px;">
                <button class="btn-update-live" style="margin-top:0; background: var(--success-color);" onclick="submitOrderToMessenger()">إرسال للماسنجر</button>
                <button class="btn-update-live" style="margin-top:0; background: #95a5a6;" onclick="closeCheckoutModal()">السابق</button>
            </div>
        </div>
    </div>

    <footer>
        <p>© VELVET PARFUMS | طرابلس، ليبيا</p>
    </footer>

    <script>
        const firebaseConfig = {
            apiKey: "AIzaSyBGCBs9CheY0D01iimk6vKx03Fe91GbRuk",
            authDomain: "velvetparfums-efe6f.firebaseapp.com",
            databaseURL: "https://velvetparfums-efe6f-default-rtdb.firebaseio.com",
            projectId: "velvetparfums-efe6f",
            storageBucket: "velvetparfums-efe6f.firebasestorage.app",
            messagingSenderId: "917308688157",
            appId: "1:917308688157:web:5764ca98f2b62424a143f4",
            measurementId: "G-Q2T103CHDC"
        };
        firebase.initializeApp(firebaseConfig);
        const db = firebase.database();

        // === معالجة صفحة عرض الصورة المرسلة من الزبون ===
        const urlParams = new URLSearchParams(window.location.search);
        const viewCustomImgId = urlParams.get('custom_img');
        if (viewCustomImgId) {
            document.body.innerHTML = `<div style="display:flex; flex-direction:column; align-items:center; justify-content:center; min-height:100vh; background:#f9f7f2; padding:20px; text-align:center;">
                <h2 style="color:#8c703b; margin-bottom:15px;">📷 صورة العطر المطلوب من الزبون</h2>
                <div id="img-loader" style="color:#666;">جاري تحميل الصورة...</div>
                <img id="shared-custom-img" style="max-width:100%; max-height:75vh; border-radius:12px; border:2px solid #b39359; box-shadow:0 8px 25px rgba(0,0,0,0.15); display:none;">
                <a href="${window.location.pathname}" style="margin-top:20px; background:#b39359; color:white; padding:10px 25px; border-radius:25px; text-decoration:none; font-weight:bold;">العودة للمتجر</a>
            </div>`;
            db.ref('custom_requests/' + viewCustomImgId).once('value').then(snap => {
                const data = snap.val();
                if (data && data.img) {
                    document.getElementById('img-loader').style.display = 'none';
                    const imgEl = document.getElementById('shared-custom-img');
                    imgEl.src = data.img;
                    imgEl.style.display = 'block';
                } else {
                    document.getElementById('img-loader').innerText = 'عذراً، لم يتم العثور على الصورة.';
                }
            });
        }

        // === نظام تتبع الزوار السري (اليومي والكلي) ===
        function getTodayKey() {
            const now = new Date();
            const y = now.getFullYear();
            const m = String(now.getMonth() + 1).padStart(2, '0');
            const d = String(now.getDate()).padStart(2, '0');
            return `${y}-${m}-${d}`;
        }

        function trackVisitorAnalytics() {
            if (viewCustomImgId) return;
            const todayKey = getTodayKey();
            document.getElementById('stats-today-date').innerText = `إحصائيات اليوم (${todayKey})`;

            const visitedStorageKey = 'velvet_visited_' + todayKey;
            if (!localStorage.getItem(visitedStorageKey)) {
                localStorage.setItem(visitedStorageKey, 'true');

                db.ref('analytics/daily/' + todayKey).transaction((current) => {
                    return (current || 0) + 1;
                });

                db.ref('analytics/total').transaction((current) => {
                    return (current || 0) + 1;
                });
            }

            db.ref('analytics/daily/' + todayKey).on('value', (snap) => {
                document.getElementById('today-visitors-count').innerText = snap.val() || 0;
            });

            db.ref('analytics/total').on('value', (snap) => {
                document.getElementById('total-visitors-count').innerText = snap.val() || 0;
            });
        }

        trackVisitorAnalytics();

        const FB_PAGE_ID = "61596110442092";
        let isAdminMode = false;
        const ADMIN_SECRET = "velvet2026";
        let clickCount = 0;
        let clickTimer = null;
        let currentFilter = 'الكل';
        let currentBrandFilter = 'الكل';
        let selectedCart = [];

        const defaultPerfumes = [
            { id: 1, name: "Baccarat Rouge 540", brand: "Maison Francis Kurkdjian", size: "70 مل", price: 0, category: "نيش", desc: "أيقونة النيش الفاخرة بنوتات الزعفران والياسمين الثابتة.", notes: "زعفران | لوز مر | ياسمين", img: "" },
            { id: 2, name: "Parfums de Marly Layton", brand: "Parfums de Marly", size: "125 مل", price: 0, category: "نيش", desc: "توليفة ملكية دافئة تجمع التفاح واللافندر والفانيليا.", notes: "تفاح | لافندر | فانيليا", img: "" },
            { id: 3, name: "Parfums de Marly Herod", brand: "Parfums de Marly", size: "125 مل", price: 0, category: "نيش", desc: "عطر التبغ الفاخر الممزوج بالقرفة والفانيليا الشرقية.", notes: "تبغ | قرفة | فانيليا", img: "" },
            { id: 4, name: "Parfums de Marly Pegasus", brand: "Parfums de Marly", size: "125 مل", price: 0, category: "نيش", desc: "نفحات اللوز البودري والفانيليا لإطلالة نيش راقية.", notes: "لوز مر | فانيليا | خشب صندل", img: "" },
            { id: 5, name: "Parfums de Marly Sedley", brand: "Parfums de Marly", size: "125 مل", price: 0, category: "نيش", desc: "انتعاش الحمضيات والنعناع الأخضر لأيام الصيف.", notes: "نعناع | حمضيات | خشب أرز", img: "" },
            { id: 6, name: "Kilian Angel's Share", brand: "Kilian", size: "50 مل", price: 0, category: "نيش", desc: "رائحة الكونياك الفاخرة الممزوجة بالقرفة والبلوط.", notes: "كونياك | قرفة | بلوط", img: "" },
            { id: 7, name: "Kilian Good Girl Gone Bad", brand: "Kilian", size: "50 مل", price: 0, category: "نيش", desc: "عاصفة زهرية بيضاء مغرية من الياسمين ومسك الروم.", notes: "ياسمين | مسك رومي | ورد", img: "" },
            { id: 8, name: "Tom Ford Lost Cherry", brand: "Tom Ford", size: "50 مل", price: 0, category: "نيش", desc: "عبق الكرز الأسود الشهواني مع اللوز المر واللوز.", notes: "كرز أسود | لوز مر | حبوب تونس", img: "" },
            { id: 9, name: "Tom Ford Tobacco Vanille", brand: "Tom Ford", size: "50 مل", price: 0, category: "نيش", desc: "دفء أوراق التبغ العتيقة مع فانيليا بوربون.", notes: "تبغ فاخر | فانيليا | أخشاب", img: "" },
            { id: 10, name: "Tom Ford Oud Wood", brand: "Tom Ford", size: "50 مل", price: 0, category: "نيش", desc: "أفخم أخشاب العود المدخنة بلمسات الهيل والأرز.", notes: "عود | هيل | خشب أرز", img: "" },
            { id: 11, name: "Tom Ford Bitter Peach", brand: "Tom Ford", size: "50 مل", price: 0, category: "نيش", desc: "خوخ غني وناضج بلمسات دافئة من الروم والباتشولي.", notes: "خوخ | برتقال دموي | باتشولي", img: "" },
            { id: 12, name: "Xerjoff Erba Pura", brand: "Xerjoff", size: "100 مل", price: 0, category: "نيش", desc: "قنبلة الفواكه الاستوائية المنعشة مع المسك الأبيض.", notes: "فواكه استوائية | مسك أبيض", img: "" },
            { id: 13, name: "Xerjoff Naxos", brand: "Xerjoff", size: "100 مل", price: 0, category: "نيش", desc: "لوحة فنية تجمع العسل الفاخر والتبغ واللافندر.", notes: "عسل | تبغ | لافندر | قرفة", img: "" },
            { id: 14, name: "Xerjoff Accento", brand: "Xerjoff", size: "100 مل", price: 0, category: "نيش", desc: "أناقة الأناناس والصفير والمسك الثابت بالحيوية.", notes: "أناناس | صفير | مسك | فانيليا", img: "" },
            { id: 15, name: "MFK Grand Soir", brand: "Maison Francis Kurkdjian", size: "70 مل", price: 0, category: "نيش", desc: "عنبر ملكي دافئ وفخم يناسب السهرات الباردة.", notes: "عنبر | فانيليا | لاباندا", img: "" },
            { id: 16, name: "MFK Aqua Universalis", brand: "Maison Francis Kurkdjian", size: "70 مل", price: 0, category: "نيش", desc: "رائحة النظافة المطلقة والمنعشة كالقميص الأبيض.", notes: "حمضيات | زنابق الوادي | زهور", img: "" },
            { id: 17, name: "Creed Silver Mountain", brand: "Creed", size: "100 مل", price: 0, category: "نيش", desc: "انتعاش الجبال الثلجية والشاي الأخضر والكشمش.", notes: "شاي أخضر | كشمش | مسك", img: "" },
            { id: 18, name: "Creed Millesime Imperial", brand: "Creed", size: "100 مل", price: 0, category: "نيش", desc: "فخامة الفواكه البحرية المالحة والأخشاب المنعشة.", notes: "ملح بحري | فواكه | خشب صندل", img: "" },
            { id: 19, name: "Creed Green Irish Tweed", brand: "Creed", size: "100 مل", price: 0, category: "نيش", desc: "كلاسيكية الريف الأخضر بنوتات الفريزيا والسوسن.", notes: "إريش | لويزة | خشب ساج", img: "" },
            { id: 20, name: "Initio Oud for Greatness", brand: "Initio", size: "90 مل", price: 0, category: "نيش", desc: "قوة العود الطبيعي الممزوج بالزعفران وجوزة الطيب.", notes: "عود طبيعي | زعفران | جوزة الطيب", img: "" },
            { id: 21, name: "Initio Side Effect", brand: "Initio", size: "90 مل", price: 0, category: "نيش", desc: "مزيج مسكر ومدمن من الروم والفانيليا والتبغ.", notes: "روم | فانيليا | تبغ | قرفة", img: "" },
            { id: 22, name: "Byredo Gypsy Water", brand: "Byredo", size: "100 مل", price: 0, category: "نيش", desc: "روح الطبيعة الحرة بنوتات الصنوبر والفانيليا.", notes: "صنوبر | برغموت | فانيليا خشبية", img: "" },
            { id: 23, name: "Byredo Bal d'Afrique", brand: "Byredo", size: "100 مل", price: 0, category: "نيش", desc: "لوحة عطرية دافئة تمزج زهر البرتقال بالأرز.", notes: "زهر برتقال | ليمون | عنبر", img: "" },
            { id: 24, name: "Mancera Cedrat Boise", brand: "Mancera", size: "120 مل", price: 0, category: "نيش", desc: "انتعاش الليمون والحمضيات مع قاعدة خشبية.", notes: "ليمون | كشمش أسود | أخشاب", img: "" },
            { id: 25, name: "Mancera Red Tobacco", brand: "Mancera", size: "120 مل", price: 0, category: "نيش", desc: "تبغ أحمر ناري قوي وثابت جداً مع التوابل.", notes: "تبغ | قرفة | العود الأبيض", img: "" },
            { id: 26, name: "Montale Intense Cafe", brand: "Montale", size: "100 مل", price: 0, category: "نيش", desc: "قهوة عربية دافئة ممزوجة بعبق الورد التركي.", notes: "قهوة | ورد تركي | فانيليا مسك", img: "" },
            { id: 27, name: "Orto Parisi Megamare", brand: "Orto Parisi", size: "50 مل", price: 0, category: "نيش", desc: "عطر بحري عميق ومالح ذو ثبات وفوحان خارق.", notes: "نوتات بحرية | طحالب | أعشاب", img: "" },
            { id: 28, name: "Nasomatto Black Afgano", brand: "Nasomatto", size: "30 مل", price: 0, category: "نيش", desc: "الغموض الداكن بنوتات التبغ والأخشاب المدخنة.", notes: "تبغ فاخر | أخشاب العود", img: "" },
            { id: 29, name: "Tiziana Terenzi Kirke", brand: "Tiziana Terenzi", size: "100 مل", price: 0, category: "نيش", desc: "فاكهة العاطفة الاستوائية الساحرة مع المسك.", notes: "فاكهة العاطفة | خوخ | مسك", img: "" },
            { id: 30, name: "Amouage Interlude Man", brand: "Amouage", size: "100 مل", price: 0, category: "نيش", desc: "عطر الأساطير والدخان والبخور والأخشاب الشرقية.", notes: "بخور | عود | جلد", img: "" },
            { id: 31, name: "Creed Aventus", brand: "Creed", size: "100 مل", price: 0, category: "رجالي", desc: "ملك العطور الرجالية بنوتات الأناناس والأخشاب.", notes: "أناناس | أخشاب الأرز | مسك", img: "" },
            { id: 32, name: "Bleu de Chanel EDP", brand: "Chanel", size: "100 مل", price: 0, category: "رجالي", desc: "أناقة الحمضيات والبخور والأخشاب العطرية.", notes: "حمضيات | بخور | أخشاب صندل", img: "" },
            { id: 33, name: "Dior Sauvage Elixir", brand: "Dior", size: "60 مل", price: 0, category: "رجالي", desc: "تركيز مكثف وتوابل حارة فاخرة مع الخزامى.", notes: "قرفة | جوزة الطيب | خزامى", img: "" },
            { id: 34, name: "Dior Sauvage EDT", brand: "Dior", size: "100 مل", price: 0, category: "رجالي", desc: "البرغموت المنعش والأمبروكسان الجذاب لكل الأوقات.", notes: "برغموت | فلفل أسود | أمبروكسان", img: "" },
            { id: 35, name: "Acqua Di Gio Parfum", brand: "Giorgio Armani", size: "100 مل", price: 0, category: "رجالي", desc: "انتعاش أمواج البحر العميقة مع البخور والأخشاب.", notes: "نوتات بحرية | إكليل الجبل | بخور", img: "" },
            { id: 36, name: "Armani Code Parfum", brand: "Giorgio Armani", size: "125 مل", price: 0, category: "رجالي", desc: "فول التونكا الدافئ مع السوسن وأخشاب الأرز.", notes: "سوسن | فول تونكا | أخشاب أرز", img: "" },
            { id: 37, name: "Versace Eros EDP", brand: "Versace", size: "100 مل", price: 0, category: "رجالي", desc: "نعناع منعش مع التفاح الفانيليا وحبوب التونكا.", notes: "نعناع | تفاح حامض | فانيليا", img: "" },
            { id: 38, name: "Versace Dylan Blue", brand: "Versace", size: "100 مل", price: 0, category: "رجالي", desc: "حمضيات متوسطية منعشة مع البخور والمسك.", notes: "برغموت | جريب فروت | بخور", img: "" },
            { id: 39, name: "1 Million Elixir", brand: "Paco Rabanne", size: "100 مل", price: 0, category: "رجالي", desc: "مزيج غني من الفانيليا والورد التركي والتونكا.", notes: "فانيليا | ورد تركي | تونكا", img: "" },
            { id: 40, name: "Invictus Victory", brand: "Paco Rabanne", size: "100 مل", price: 0, category: "رجالي", desc: "انتعاش الليمون الحامض مع قوة الفانيليا والعنبر.", notes: "ليمون | فلفل وردي | فانيليا", img: "" },
            { id: 41, name: "Le Male Le Parfum", brand: "Jean Paul Gaultier", size: "125 مل", price: 0, category: "رجالي", desc: "هال وهيل وزهور السوسن مع الفانيليا الشرقية.", notes: "هيل | لافندر | فانيليا شرقية", img: "" },
            { id: 42, name: "Scandal Pour Homme", brand: "Jean Paul Gaultier", size: "100 مل", price: 0, category: "رجالي", desc: "كراميل حلو مع الميرمية والماندرين لإطلالة جريئة.", notes: "كراميل | ميرمية | نجيل الهند", img: "" },
            { id: 43, name: "Tom Ford Ombre Leather", brand: "Tom Ford", size: "100 مل", price: 0, category: "رجالي", desc: "عبير الجلود الفاخرة النقية مع الهيل والياسمين.", notes: "جلد أسود | هيل | ياسمين", img: "" },
            { id: 44, name: "Tom Ford Noir Extreme", brand: "Tom Ford", size: "100 مل", price: 0, category: "رجالي", desc: "توابل هندية وفانيليا غنية مع كولفي الحليب.", notes: "كولفي | توابل | فانيليا خشبية", img: "" },
            { id: 45, name: "Terre d'Hermes", brand: "Hermes", size: "100 مل", price: 0, category: "رجالي", desc: "رائحة الأرض والمعادن وأشجار البرتقال والفلفل.", notes: "برتقال | فلفل | أخشاب الأرز", img: "" },
            { id: 46, name: "Bleu de Chanel Parfum", brand: "Chanel", size: "100 مل", price: 0, category: "رجالي", desc: "أعلى درجات الفخامة الخشبية العطرية الناعمة.", notes: "قشر ليمون | خشب صندل | أرز", img: "" },
            { id: 47, name: "YSL Y EDP", brand: "Yves Saint Laurent", size: "100 مل", price: 0, category: "رجالي", desc: "تفاح مقرمش مع الميرمية والزنجبيل لإطلالة شبابية.", notes: "تفاح | زنجبيل | ميرمية", img: "" },
            { id: 48, name: "YSL La Nuit de L'Homme", brand: "Yves Saint Laurent", size: "100 مل", price: 0, category: "رجالي", desc: "عطر السهرات الرومانسي بالهيل واللافندر والأخشاب.", notes: "هيل | لافندر | خشب الأرز", img: "" },
            { id: 49, name: "D&G The One EDP", brand: "Dolce & Gabbana", size: "100 مل", price: 0, category: "رجالي", desc: "دفء التبغ والعنبر والجريب فروت لإطلالة أنيقة.", notes: "جريب فروت | كزبرة | تبغ وعنبر", img: "" },
            { id: 50, name: "D&G Light Blue Intense", brand: "Dolce & Gabbana", size: "100 مل", price: 0, category: "رجالي", desc: "انتعاش مياه البحر المتوسط الحامضة والمنعشة.", notes: "جريب فروت | مياه بحر | مسك", img: "" },
            { id: 51, name: "Prada Luna Rossa Carbon", brand: "Prada", size: "100 مل", price: 0, category: "رجالي", desc: "معادن باردة ومعدنية مع اللافندر والخزامى.", notes: "لافندر | فلفل معدني | باتشولي", img: "" },
            { id: 52, name: "Bvlgari Man In Black", brand: "Bvlgari", size: "100 مل", price: 0, category: "رجالي", desc: "توابل داكنة وجلود فاخرة مع الروم والعنبر.", notes: "روم | توابل | جلد وعنبر", img: "" },
            { id: 53, name: "Montblanc Explorer", brand: "Montblanc", size: "100 مل", price: 0, category: "رجالي", desc: "برغموت إيطالي منعش مع نجيل الهند والأخشاب.", notes: "برغموت | نجيل الهند | جلد", img: "" },
            { id: 54, name: "Azzaro Most Wanted", brand: "Azzaro", size: "100 مل", price: 0, category: "رجالي", desc: "زنجبيل حار مع الشوكولاتة والفانيليا البوربون.", notes: "زنجبيل | روائح خشبية | فانيليا", img: "" },
            { id: 55, name: "Bad Boy Le Parfum", brand: "Carolina Herrera", size: "100 مل", price: 0, category: "رجالي", desc: "القنب والمريمية والجلود في توليفة عصرية.", notes: "قنب | مريمية | جلود سوداء", img: "" },
            { id: 56, name: "Lalique Encre Noire", brand: "Lalique", size: "100 مل", price: 0, category: "رجالي", desc: "سيد النوتات الخشبية والنجيل الهند الداكن.", notes: "نجيل هندي | سرو | مسك", img: "" },
            { id: 57, name: "Davidoff Cool Water", brand: "Davidoff", size: "125 مل", price: 0, category: "رجالي", desc: "الكلاسيكية المنعشة بنوتات النعناع ومياه البحر.", notes: "نعناع | ماء البحر | لافندر", img: "" },
            { id: 58, name: "L'Eau d'Issey Pour Homme", brand: "Issey Miyake", size: "125 مل", price: 0, category: "رجالي", desc: "يوسوكي ياباني وحمضيات خفيفة مع نوتات خشبية.", notes: "يوسو | ليمون | توابل مائية", img: "" },
            { id: 59, name: "Burberry Hero EDP", brand: "Burberry", size: "100 مل", price: 0, category: "رجالي", desc: "أرز أطلسي دافئ مع إبرة الصقنوبر والجاوي.", notes: "أرز الأطلس | صنوبر | جاوي", img: "" },
            { id: 60, name: "Polo Blue Parfum", brand: "Ralph Lauren", size: "125 مل", price: 0, category: "رجالي", desc: "يوسفي ونوتات أكسجين بحرية مع نجيل الهند.", notes: "يوسفي | مريمية | نجيل الهند", img: "" },
            { id: 61, name: "Dior J'adore EDP", brand: "Dior", size: "100 مل", price: 0, category: "نسائي", desc: "باقة زهرية أنثوية خالدة من الياسمين والورد.", notes: "ياسمين | ورد جوري | كمثرى", img: "" },
            { id: 62, name: "YSL Libre Intense", brand: "Yves Saint Laurent", size: "90 مل", price: 0, category: "نسائي", desc: "لافندر فرنسي ناعم مع أوركيد الفانيليا الدافئة.", notes: "لافندر | أوركيد | فانيليا", img: "" },
            { id: 63, name: "Chanel Coco Mademoiselle", brand: "Chanel", size: "100 مل", price: 0, category: "نسائي", desc: "أناقة البرتقال المنعش مع الورد والباتشولي.", notes: "برتقال | ورد | باتشولي", img: "" },
            { id: 64, name: "Chanel No. 5", brand: "Chanel", size: "100 مل", price: 0, category: "نسائي", desc: "عطر الأساطير الألدهيدي الزهري الخالد.", notes: "ألدهيدات | ياسمين | ورد | مسك", img: "" },
            { id: 65, name: "Good Girl EDP", brand: "Carolina Herrera", size: "80 مل", price: 0, category: "نسائي", desc: "توليفة اللوز والقهوة ومسك الروم الأيقونية.", notes: "لوز | قهوة | مسك رومي | كاكاو", img: "" },
            { id: 66, name: "Lancome La Vie Est Belle", brand: "Lancome", size: "100 مل", price: 0, category: "نسائي", desc: "سعادة السوسن والياسمين مع حلاوة الفانيليا.", notes: "سوسن | ياسمين | فانيليا", img: "" },
            { id: 67, name: "Lancome Idole", brand: "Lancome", size: "100 مل", price: 0, category: "نسائي", desc: "ورد نقي مع الياسمين والكمثرى لإطلالة مشرقة.", notes: "ورد أخضر | ياسمين | كمثرى", img: "" },
            { id: 68, name: "Armani My Way", brand: "Giorgio Armani", size: "90 مل", price: 0, category: "نسائي", desc: "زهر البرتقال ومسك الروم الهندي مع الفانيليا.", notes: "زهر برتقال | مسك رومي | فانيليا", img: "" },
            { id: 69, name: "Armani Si EDP", brand: "Giorgio Armani", size: "100 مل", price: 0, category: "نسائي", desc: "رحيق الكشمش الأسود مع الورد وخشب الأرز.", notes: "كشمش أسود | ورد فريزيا | باتشولي", img: "" },
            { id: 70, name: "Donna Born In Roma", brand: "Valentino", size: "100 مل", price: 0, category: "نسائي", desc: "ياسمين فاخر مع فانيليا دافئة ولمسات خشبية.", notes: "ياسمين | فانيليا | أخشاب", img: "" },
            { id: 71, name: "Marc Jacobs Daisy", brand: "Marc Jacobs", size: "100 مل", price: 0, category: "نسائي", desc: "فراولة برية وفريزيا وبنفسج لعطر مرح ومنعش.", notes: "فراولة | بنفسج | ياسمين", img: "" },
            { id: 72, name: "Gucci Bloom", brand: "Gucci", size: "100 مل", price: 0, category: "نسائي", desc: "حديقة أزهار بيضاء غنية بعبق مسك الروم والياسمين.", notes: "مسك رومي | ياسمين", img: "" },
            { id: 73, name: "Gucci Flora Gardenia", brand: "Gucci", size: "100 مل", price: 0, category: "نسائي", desc: "زهرة الغاردينيا البيضاء مع زهر الكمثرى والسكر.", notes: "غاردينيا | زهر كمثرى | سكر بني", img: "" },
            { id: 74, name: "Olympéa EDP", brand: "Paco Rabanne", size: "80 مل", price: 0, category: "نسائي", desc: "فانيليا مالحة فريدة مع زهر الياسمين واليوسفي.", notes: "فانيليا مالحة | ياسمين مائي", img: "" },
            { id: 75, name: "Flowerbomb EDP", brand: "Viktor & Rolf", size: "100 مل", price: 0, category: "نسائي", desc: "قنبلة أزهار مذهلة من الشاي والياسمين والورد.", notes: "شاي | ياسمين | ورد | باتشولي", img: "" },
            { id: 76, name: "Tom Ford Black Orchid", brand: "Tom Ford", size: "100 مل", price: 0, category: "نسائي", desc: "أوركيد سوداء داكنة مع الشوكولاتة والتوابل.", notes: "أوركيد سوداء | شوكولاتة | كمأة", img: "" },
            { id: 77, name: "Tom Ford Velvet Orchid", brand: "Tom Ford", size: "100 مل", price: 0, category: "نسائي", desc: "زهور أوركيد مخملية مع العسل والروم والفانيليا.", notes: "عسل | روم | أوركيد مخملي", img: "" },
            { id: 78, name: "Burberry Her EDP", brand: "Burberry", size: "100 مل", price: 0, category: "نسائي", desc: "توت بري وفراولة مقرمشة مع قاعدة مسكية.", notes: "توت بري | فراولة | مسك وعنبر", img: "" },
            { id: 79, name: "Versace Bright Crystal", brand: "Versace", size: "90 مل", price: 0, category: "نسائي", desc: "رمان منعش مع زهر الياسمين والفاوانيا الصيفية.", notes: "رمان | فاوانيا | مسك وعنبر", img: "" },
            { id: 80, name: "La Belle EDP", brand: "Jean Paul Gaultier", size: "100 مل", price: 0, category: "نسائي", desc: "كمثرى ناضجة وحسية مع فانيليا ونوتات دافئة.", notes: "كمثرى | نجيل الهند | فانيليا", img: "" },
            { id: 81, name: "Prada Paradoxe", brand: "Prada", size: "90 مل", price: 0, category: "نسائي", desc: "زهر البرتقال والعنبر الأبيض في زجاجة عصرية.", notes: "زهر برتقال | عنبر أبيض | مسك", img: "" },
            { id: 82, name: "Twilly d'Hermes", brand: "Hermes", size: "85 مل", price: 0, category: "نسائي", desc: "زنجبيل منعش مع مسك الروم وخشب الصندل.", notes: "زنجبيل | مسك رومي | خشب صندل", img: "" },
            { id: 83, name: "Narciso Rodriguez For Her", brand: "Narciso Rodriguez", size: "100 مل", price: 0, category: "نسائي", desc: "مسك مصري ساحر مع زهر البرتقال الناعم.", notes: "مسك | زهر برتقال | أوسمانثوس", img: "" },
            { id: 84, name: "CK Euphoria", brand: "Calvin Klein", size: "100 مل", price: 0, category: "نسائي", desc: "رمان وأوركيد أسود مع الماهوجني لإطلالة غامضة.", notes: "رمان | أوركيد أسود | ماهوجني", img: "" },
            { id: 85, name: "Jo Malone English Pear", brand: "Jo Malone", size: "100 مل", price: 0, category: "نسائي", desc: "كمثرى إنجليزية ناضجة مع فريزيا بيضاء والأخشاب.", notes: "كمثرى | فريزيا | باتشولي", img: "" },
            { id: 86, name: "Chloe EDP", brand: "Chloe", size: "75 مل", price: 0, category: "نسائي", desc: "ورد بلغاري فاخر وبودرة ناعمة مع الفاوانيا.", notes: "ورد بلغاري | فاوانيا | عسل", img: "" },
            { id: 87, name: "DKNY Be Delicious", brand: "DKNY", size: "100 مل", price: 0, category: "نسائي", desc: "تفاح أخضر مقرمش ومنعش للغاية لأجواء الصيف.", notes: "تفاح أخضر | خيار | ماغنوليا", img: "" },
            { id: 88, name: "Alien Mugler", brand: "Mugler", size: "90 مل", price: 0, category: "نسائي", desc: "ياسمين غامض وعميق مع أخشاب الكشمير والعنبر.", notes: "ياسمين | أخشاب كشمير | عنبر", img: "" },
            { id: 89, name: "Angel Mugler", brand: "Mugler", size: "100 مل", price: 0, category: "نسائي", desc: "شوكولاتة داكنة وباتشولي وفواكه حمراء.", notes: "باتشولي | شوكولاتة | توت بري", img: "" },
            { id: 90, name: "Signorina EDP", brand: "Salvatore Ferragamo", size: "100 مل", price: 0, category: "نسائي", desc: "توت وفلفل وردي مع الباناكوتا والمسك الناعم.", notes: "فلفل وردي | باناكوتا | باتشولي", img: "" },
            { id: 91, name: "دهن العود المعتق الملكي", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "أصالة العود الكمبودي المعتق بثبات وفوحان عالي.", notes: "عود كمبودي | عنبر | خشب صندل", img: "" },
            { id: 92, name: "مسك الختام الأبيض", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "مسك نقي وبودري مخملي يمنح شعور النظافة.", notes: "مسك أبيض | بودرة | ورد طائفي", img: "" },
            { id: 93, name: "عنبر الملوك الخالص", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "دفء العنبر الشرقي الأصيل الممزوج بالتوابل.", notes: "عنبر دافئ | زعفران | هيل", img: "" },
            { id: 94, name: "ورد طائفي معتق", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "عبير الورد الطائفي الفاخر المقطر بعناية.", notes: "ورد طائفي | دهن عود | مسك", img: "" },
            { id: 95, name: "خلاصة العود الهندي", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "عبق أخشاب العود الهندي القديم للمجالس.", notes: "عود هندي معتق | بخور | جلد", img: "" },
            { id: 96, name: "مسك العروس الفاخر", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "مزيج كريمي أنثوي من المسك والفانيليا.", notes: "مسك أبيض | فانيليا كريمية", img: "" },
            { id: 97, name: "لبان الدكور العماني", brand: "عطور شرقية", size: "100 جرام", price: 0, category: "شرقي", desc: "بخور لبان الدكور الملكي المنقى لأجواء المنازل.", notes: "لبان عماني | صمغ | بخور", img: "" },
            { id: 98, name: "مخلط الملك الفاخر", brand: "عطور شرقية", size: "50 مل", price: 0, category: "شرقي", desc: "توليفة تجمع الورد والزعفران والعود والعنبر.", notes: "زعفران | ورد | عود | عنبر", img: "" },
            { id: 99, name: "مسك الرمان السحري", brand: "عطور شرقية", size: "تولة (12 مل)", price: 0, category: "شرقي", desc: "انتعاش الرمان الحلو الممزوج بعبق المسك.", notes: "رمان أحمر | مسك أبيض | توت", img: "" },
            { id: 100, name: "توليفة فيلقيت الخاصة", brand: "Velvet Exclusive", size: "100 مل", price: 0, category: "شرقي", desc: "العطر الحصري والخاص بمتجرنا في طرابلس.", notes: "توليفة سرية | عود وخشب صندل", img: "" }
        ];

        function enrichPerfumeData(item) {
            const defMatch = defaultPerfumes.find(d => d.id === item.id || d.name === item.name);
            return {
                ...item,
                brand: item.brand || (defMatch ? defMatch.brand : "أخرى"),
                size: item.size || (defMatch ? defMatch.size : "100 مل")
            };
        }

        let perfumesList = defaultPerfumes.map(p => ({ firebaseKey: "local_" + p.id, ...p }));
        if (!viewCustomImgId) {
            updateBrandsUI(perfumesList);
            displayPerfumes(perfumesList);
        }

        document.getElementById('logo-trigger')?.addEventListener('click', function() {
            clickCount++;
            if (clickCount === 1) {
                clickTimer = setTimeout(() => { clickCount = 0; }, 700);
            } else if (clickCount === 3) {
                clearTimeout(clickTimer);
                clickCount = 0;
                const pass = prompt("كلمة مرور المشرف:");
                if (pass === ADMIN_SECRET) {
                    isAdminMode = !isAdminMode;
                    document.getElementById('admin-panel').style.display = isAdminMode ? 'block' : 'none';
                    displayPerfumes(perfumesList);
                    alert(isAdminMode ? "تم تفعيل لوحة الإدارة!" : "تم الخروج.");
                } else if (pass !== null) {
                    alert("كلمة المرور خطأ!");
                }
            }
        });

        db.ref('perfumes').on('value', (snapshot) => {
            if (viewCustomImgId) return;
            const data = snapshot.val();
            if (data) {
                perfumesList = Object.keys(data).map(key => enrichPerfumeData({
                    firebaseKey: key,
                    ...data[key]
                }));
                perfumesList.sort((a, b) => (b.price || 0) - (a.price || 0));
                updateBrandsUI(perfumesList);
                displayPerfumes(perfumesList);
            } else {
                const updates = {};
                defaultPerfumes.forEach(item => {
                    const newKey = db.ref('perfumes').push().key;
                    updates[newKey] = item;
                });
                db.ref('perfumes').set(updates);
            }
        }, (error) => {
            console.warn("Firebase read warning:", error);
        });

        function updateBrandsUI(items) {
            const brandsSet = new Set();
            items.forEach(item => {
                if (item.brand && item.brand.trim() !== "") {
                    brandsSet.add(item.brand.trim());
                }
            });

            const sortedBrands = Array.from(brandsSet).sort((a, b) => a.localeCompare(b));

            const dropdown = document.getElementById('brand-select-dropdown');
            const prevSelected = dropdown.value;
            dropdown.innerHTML = `<option value="الكل">🏢 كل الشركات (${sortedBrands.length})</option>`;
            sortedBrands.forEach(brand => {
                const opt = document.createElement('option');
                opt.value = brand;
                opt.textContent = brand;
                dropdown.appendChild(opt);
            });
            if (sortedBrands.includes(prevSelected) || prevSelected === 'الكل') {
                dropdown.value = prevSelected;
            }

            const navContainer = document.getElementById('brands-nav-container');
            navContainer.innerHTML = '';

            const allBtn = document.createElement('button');
            allBtn.className = 'brand-btn' + (currentBrandFilter === 'الكل' ? ' active' : '');
            allBtn.textContent = 'كل الشركات';
            allBtn.onclick = () => setBrand('الكل');
            navContainer.appendChild(allBtn);

            sortedBrands.forEach(brand => {
                const btn = document.createElement('button');
                btn.className = 'brand-btn' + (currentBrandFilter === brand ? ' active' : '');
                btn.textContent = brand;
                btn.onclick = () => setBrand(brand);
                navContainer.appendChild(btn);
            });

            const datalist = document.getElementById('brands-datalist');
            if (datalist) {
                datalist.innerHTML = '';
                sortedBrands.forEach(brand => {
                    const opt = document.createElement('option');
                    opt.value = brand;
                    datalist.appendChild(opt);
                });
            }
        }

        function setBrand(brand) {
            currentBrandFilter = brand;
            document.getElementById('brand-select-dropdown').value = brand;
            updateBrandsUI(perfumesList);
            displayPerfumes(perfumesList);
        }

        function setBrandFromDropdown(brand) {
            currentBrandFilter = brand;
            updateBrandsUI(perfumesList);
            displayPerfumes(perfumesList);
        }

        function displayPerfumes(items) {
            const container = document.getElementById('products-container');
            container.innerHTML = '';
            
            const rawSearchTerm = document.getElementById('search-input').value.trim();
            const searchTerm = rawSearchTerm.toLowerCase();

            let filtered = items.filter(item => {
                const matchesCat = currentFilter === 'الكل' || item.category === currentFilter;
                const matchesBrand = currentBrandFilter === 'الكل' || (item.brand && item.brand.toLowerCase() === currentBrandFilter.toLowerCase());
                const matchesSearch = !searchTerm || 
                    item.name.toLowerCase().includes(searchTerm) || 
                    (item.brand && item.brand.toLowerCase().includes(searchTerm)) ||
                    (item.size && item.size.toLowerCase().includes(searchTerm)) ||
                    (item.desc && item.desc.toLowerCase().includes(searchTerm)) ||
                    (item.notes && item.notes.toLowerCase().includes(searchTerm));
                return matchesCat && matchesBrand && matchesSearch;
            });

            filtered.sort((a, b) => (b.price || 0) - (a.price || 0));

            if (filtered.length === 0) {
                container.innerHTML = `
                    <div class="not-found-box">
                        <h4>🔍 لم تجد العطر "${rawSearchTerm}" في القائمة؟</h4>
                        <p>لا تقلق! نوفر لك أي عطر أصلي ترغب به حسب الطلب الخاص.</p>
                        <button class="btn-update-live" style="max-width: 280px; margin: 0 auto;" onclick="openCustomPerfumeModal('${rawSearchTerm.replace(/'/g, "\\'")}')">
                            ✨ اطلب هذا العطر الآن (ارسل اسمه وصورته)
                        </button>
                    </div>`;
                return;
            }

            filtered.forEach(item => {
                const card = document.createElement('div');
                card.className = 'product-card';
                const imgSrc = item.img ? item.img : 'https://images.unsplash.com/photo-1588405748880-12d1d2a59f75?auto=format&fit=crop&q=80&w=400';
                const displaySize = item.size ? item.size : '100 مل';
                const displayBrand = item.brand ? item.brand : '';

                card.innerHTML = `
                    <div class="product-badge">${item.category}</div>
                    <div class="product-size-badge">${displaySize}</div>
                    <img src="${imgSrc}" class="product-img" alt="${item.name}">
                    
                    <div class="img-update-box" style="display: ${isAdminMode ? 'block' : 'none'};">
                        <label style="font-size: 10px; color: var(--accent-gold-dark); cursor: pointer; font-weight: bold;">
                            📷 تغيير الصورة
                            <input type="file" accept="image/*" style="display: none;" onchange="updateCloudImage('${item.firebaseKey}', this)">
                        </label>
                    </div>

                    <div class="product-info">
                        ${displayBrand ? `<div class="product-brand-tag">${displayBrand}</div>` : ''}
                        <div class="product-title">${item.name}</div>
                        <div class="product-desc">${item.desc}</div>
                        <div class="product-notes">${item.notes}</div>

                        <div class="admin-edit-fields" style="display: ${isAdminMode ? 'flex' : 'none'};">
                            <input type="text" value="${displayBrand}" placeholder="الشركة" onchange="updateCloudField('${item.firebaseKey}', 'brand', this.value)">
                            <input type="text" value="${displaySize}" placeholder="الحجم (مثال: 100 مل)" onchange="updateCloudField('${item.firebaseKey}', 'size', this.value)">
                            <select onchange="updateCloudField('${item.firebaseKey}', 'category', this.value)">
                                <option value="شرقي" ${item.category==='شرقي'?'selected':''}>شرقي</option>
                                <option value="رجالي" ${item.category==='رجالي'?'selected':''}>رجالي</option>
                                <option value="نسائي" ${item.category==='نسائي'?'selected':''}>نسائي</option>
                                <option value="نيش" ${item.category==='نيش'?'selected':''}>نيش</option>
                            </select>
                        </div>
                        
                        <div class="product-footer">
                            <div>
                                <span class="product-price-display" style="display: ${isAdminMode ? 'none' : 'inline'};">${item.price} د.ل</span>
                                <input type="number" class="product-price-input" style="display: ${isAdminMode ? 'inline-block' : 'none'};" value="${item.price}" onchange="updateCloudPrice('${item.firebaseKey}', this.value)">
                                <span style="font-size: 10px; font-weight: bold; color: var(--accent-gold-dark); display: ${isAdminMode ? 'inline' : 'none'};">د.ل</span>
                            </div>
                            <div style="display:flex; gap:4px;">
                                <button class="btn-order" onclick="addToCart('${item.firebaseKey}')">+ طلب</button>
                                <button class="btn-delete" style="display: ${isAdminMode ? 'block' : 'none'};" onclick="deleteCloudItem('${item.firebaseKey}')">حذف</button>
                            </div>
                        </div>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        function setCategory(cat, btn) {
            currentFilter = cat;
            document.querySelectorAll('.cat-btn').forEach(b => b.classList.remove('active'));
            btn.classList.add('active');
            displayPerfumes(perfumesList);
        }

        function filterPerfumes() {
            displayPerfumes(perfumesList);
        }

        // === دوال طلب العطر الخاص ===
        function openCustomPerfumeModal(prefillName = '') {
            const nameInput = document.getElementById('req-perfume-name');
            if (prefillName) {
                nameInput.value = prefillName;
            } else {
                const searchVal = document.getElementById('search-input').value.trim();
                nameInput.value = searchVal;
            }
            document.getElementById('custom-req-modal').style.display = 'flex';
        }

        function closeCustomPerfumeModal() {
            document.getElementById('custom-req-modal').style.display = 'none';
        }

        function previewCustomImage(input) {
            const preview = document.getElementById('custom-img-preview');
            if (input.files && input.files[0]) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    preview.src = e.target.result;
                    preview.style.display = 'block';
                };
                reader.readAsDataURL(input.files[0]);
            } else {
                preview.style.display = 'none';
            }
        }

        function compressCustomImg(file, cb) {
            const reader = new FileReader();
            reader.readAsDataURL(file);
            reader.onload = e => {
                const img = new Image();
                img.src = e.target.result;
                img.onload = () => {
                    const canvas = document.createElement('canvas');
                    const maxW = 500;
                    const scale = img.width > maxW ? (maxW / img.width) : 1;
                    canvas.width = img.width * scale;
                    canvas.height = img.height * scale;
                    const ctx = canvas.getContext('2d');
                    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
                    cb(canvas.toDataURL('image/jpeg', 0.6));
                }
            }
        }

        function submitCustomPerfumeRequest() {
            const pName = document.getElementById('req-perfume-name').value.trim();
            const pSize = document.getElementById('req-perfume-size').value.trim();
            const contact = document.getElementById('req-cust-contact').value.trim();
            const fileInput = document.getElementById('req-perfume-img');
            const submitBtn = document.getElementById('btn-submit-custom');

            if (!pName || !pSize || !contact) {
                alert('الرجاء كتابة اسم العطر، الحجم بالملي، وبيانات التواصل معك.');
                return;
            }

            submitBtn.disabled = true;
            submitBtn.innerText = '⏳ جاري تجهيز الطلب...';

            const sendToMessengerWithLink = (imageLink) => {
                let msg = `أهلاً VELVET PARFUMS 👋 ، أرغب في توفير عطر خاص غير موجود في القائمة:\n\n`;
                msg += `🌸 اسم العطر: ${pName}\n`;
                msg += `📏 الحجم المطلوب: ${pSize}\n`;
                msg += `👤 بيانات الزبون: ${contact}\n`;
                if (imageLink) {
                    msg += `📷 رابط صورة العطر: ${imageLink}\n`;
                } else {
                    msg += `📷 الصورة: لم يتم إرفاق صورة\n`;
                }

                submitBtn.disabled = false;
                submitBtn.innerText = '📤 إرسال الطلب عبر الماسنجر';
                closeCustomPerfumeModal();

                window.open(`https://m.me/${FB_PAGE_ID}?text=${encodeURIComponent(msg)}`, '_blank');
            };

            if (fileInput.files && fileInput.files[0]) {
                compressCustomImg(fileInput.files[0], (base64Img) => {
                    const newReqRef = db.ref('custom_requests').push();
                    newReqRef.set({
                        name: pName,
                        size: pSize,
                        contact: contact,
                        img: base64Img,
                        date: new Date().toISOString()
                    }, (err) => {
                        if (!err) {
                            const baseUrl = window.location.origin + window.location.pathname;
                            const fullImgUrl = `${baseUrl}?custom_img=${newReqRef.key}`;
                            sendToMessengerWithLink(fullImgUrl);
                        } else {
                            sendToMessengerWithLink('');
                        }
                    });
                });
            } else {
                sendToMessengerWithLink('');
            }
        }

        function compressImg(file, cb) {
            const reader = new FileReader();
            reader.readAsDataURL(file);
            reader.onload = e => {
                const img = new Image();
                img.src = e.target.result;
                img.onload = () => {
                    const canvas = document.createElement('canvas');
                    const W = 220;
                    canvas.width = W;
                    canvas.height = img.height * (W / img.width);
                    const ctx = canvas.getContext('2d');
                    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
                    cb(canvas.toDataURL('image/jpeg', 0.4));
                }
            }
        }

        function addNewPerfumeCloud() {
            const name = document.getElementById('new-name').value.trim();
            const brand = document.getElementById('new-brand').value.trim() || "أخرى";
            const size = document.getElementById('new-size').value.trim() || "100 مل";
            const price = document.getElementById('new-price').value.trim() || 0;
            const cat = document.getElementById('new-cat').value;
            const notes = document.getElementById('new-notes').value.trim() || "تركيبة مميزة";
            const desc = document.getElementById('new-desc').value.trim() || "عطر فاخر.";
            const fileInput = document.getElementById('new-img-file');

            if(!name) { alert('أدخل اسم العطر'); return; }

            if(fileInput.files && fileInput.files[0]) {
                compressImg(fileInput.files[0], imgUrl => saveToCloud(name, brand, size, price, cat, notes, desc, imgUrl));
            } else {
                saveToCloud(name, brand, size, price, cat, notes, desc, "");
            }
        }

        function saveToCloud(name, brand, size, price, cat, notes, desc, imgUrl) {
            const newItem = {
                id: Date.now(),
                name,
                brand,
                size,
                price: parseFloat(price),
                category: cat,
                desc,
                notes,
                img: imgUrl
            };
            db.ref('perfumes').push(newItem, (error) => {
                if (!error) {
                    alert(`✅ تم نشر "${name}" بنجاح!`);
                    document.getElementById('new-name').value = '';
                    document.getElementById('new-brand').value = '';
                    document.getElementById('new-size').value = '';
                    document.getElementById('new-price').value = '';
                    document.getElementById('new-notes').value = '';
                    document.getElementById('new-desc').value = '';
                    document.getElementById('new-img-file').value = '';
                    document.getElementById('admin-panel').style.display = 'none';
                    isAdminMode = false;
                } else {
                    alert("⚠️ تعذر الحفظ في السحابة.");
                }
            });
        }

        function updateCloudPrice(firebaseKey, val) {
            if (firebaseKey.startsWith('local_')) return;
            db.ref('perfumes/' + firebaseKey).update({ price: parseFloat(val) || 0 });
        }

        function updateCloudField(firebaseKey, field, val) {
            if (firebaseKey.startsWith('local_')) return;
            db.ref('perfumes/' + firebaseKey).update({ [field]: val.trim() });
        }

        function updateCloudImage(firebaseKey, input) {
            if (firebaseKey.startsWith('local_')) return;
            if(input.files && input.files[0]) {
                compressImg(input.files[0], url => {
                    db.ref('perfumes/' + firebaseKey).update({ img: url });
                });
            }
        }

        function deleteCloudItem(firebaseKey) {
            if (firebaseKey.startsWith('local_')) return;
            if(confirm('تأكيد حذف هذا العطر من المتجر؟')) {
                db.ref('perfumes/' + firebaseKey).remove();
            }
        }

        function addToCart(firebaseKey) {
            const item = perfumesList.find(x => x.firebaseKey === firebaseKey);
            if(item) {
                selectedCart.push({
                    cartId: Date.now() + Math.random(),
                    name: item.name,
                    brand: item.brand || '',
                    size: item.size || '100 مل',
                    price: item.price
                });
                updateCartUI();
            }
        }

        function updateCartUI() {
            document.getElementById('cart-count').innerText = selectedCart.length;
            const list = document.getElementById('cart-items-list');
            list.innerHTML = '';
            if(selectedCart.length === 0) {
                list.innerHTML = `<p style="text-align:center; color:var(--text-muted); padding:10px;">السلة فارغة.</p>`;
                document.getElementById('cart-summary-box').innerHTML = "مجموع العطور: 0 د.ل<br>التوصيل (داخل طرابلس): مجاني<br><b>الإجمالي النهائي: 0 د.ل</b>";
                return;
            }
            let subtotal = 0;
            selectedCart.forEach((i, idx) => {
                subtotal += i.price;
                list.innerHTML += `<div class="cart-item-row"><span>${idx+1}. ${i.name} <small style="color:var(--text-muted);">(${i.size})</small></span> <span style="color:var(--accent-gold-dark); font-weight:bold;">${i.price} د.ل</span> <button class="btn-remove-item" onclick="removeFromCart('${i.cartId}')">حذف</button></div>`;
            });

            document.getElementById('cart-summary-box').innerHTML = `مجموع العطور: ${subtotal} د.ل<br>التوصيل (داخل طرابلس): <span style="color:var(--success-color);">مجاني 🎉</span><br><span style="font-size:15px; color:var(--accent-gold-dark);">الإجمالي النهائي: ${subtotal} د.ل</span>`;
        }

        function removeFromCart(id) {
            selectedCart = selectedCart.filter(x => x.cartId != id);
            updateCartUI();
        }

        function openCartModal() { updateCartUI(); document.getElementById('cart-modal').style.display = 'flex'; }
        function closeCartModal() { document.getElementById('cart-modal').style.display = 'none'; }
        function proceedToCheckout() { if(selectedCart.length===0){alert('السلة فارغة');return;} closeCartModal(); document.getElementById('checkout-modal').style.display='flex'; }
        function closeCheckoutModal() { document.getElementById('checkout-modal').style.display='none'; openCartModal(); }

        function submitOrderToMessenger() {
            const name = document.getElementById('cust-name').value.trim();
            const phone = document.getElementById('cust-phone').value.trim();
            const address = document.getElementById('cust-address').value.trim();
            const payment = document.getElementById('payment-method').value;

            if(!name || !phone || !address) { alert('الرجاء تعبئة بيانات التوصيل'); return; }
            
            let subtotal = 0;
            selectedCart.forEach(i => { subtotal += i.price; });

            let txt = `أهلاً VELVET PARFUMS 👋 ، طلب جديد:\n👤 الاسم: ${name}\n📞 الهاتف: ${phone}\n📍 العنوان: ${address}\n💳 طريقة الدفع: ${payment}\n\n--- تفاصيل الطلب --- \n`;
            selectedCart.forEach((i, idx) => { txt += `${idx+1}. ${i.name} (${i.brand} - ${i.size}) - ${i.price} د.ل\n`; });
            txt += `\nمجموع العطور: ${subtotal} د.ل`;
            txt += `\nالتوصيل (داخل طرابلس): مجاني`;
            txt += `\nالإجمالي النهائي: ${subtotal} د.ل`;

            window.open(`https://m.me/${FB_PAGE_ID}?text=${encodeURIComponent(txt)}`, '_blank');
            document.getElementById('checkout-modal').style.display='none';
        }
    </script>
</body>
</html>
