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
            height: 240px;
            object-fit: cover;
            background-color: #f2eee9;
        }

        .product-info {
            padding: 18px;
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
        }

        .product-title {
            font-size: 17px;
            font-weight: 700;
            color: var(--text-dark);
            margin-bottom: 5px;
        }

        .product-desc {
            font-size: 13px;
            color: var(--text-muted);
            margin-bottom: 10px;
        }

        .product-notes {
            background: var(--bg-color);
            padding: 6px 10px;
            border-radius: 6px;
            font-size: 12px;
            color: var(--accent-gold);
            margin-bottom: 15px;
        }

        .product-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-top: auto;
            padding-top: 10px;
            border-top: 1px solid var(--border-color);
            gap: 8px;
        }

        .product-price {
            font-size: 18px;
            font-weight: 700;
            color: var(--accent-gold);
        }

        .actions-group {
            display: flex;
            gap: 5px;
        }

        .btn-order {
            background-color: var(--accent-gold);
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 6px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
        }

        .btn-delete {
            background-color: #fae1dd;
            color: var(--danger-color);
            border: 1px solid var(--danger-color);
            padding: 8px 10px;
            border-radius: 6px;
            font-size: 12px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn-delete:hover {
            background-color: var(--danger-color);
            color: white;
        }

        /* شريط السلة الدائم في الأسفل */
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
        <!-- زر فتح لوحة الإدارة -->
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
                    <label style="display: block; margin-bottom: 5px; font-weight: bold; color: var(--accent-gold);">📷 اختر صورة العطر من هاتفك (سيتم ضغطها أوتوماتيكياً):</label>
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

    <!-- شريط السلة الدائم في الأسفل (يظهر دائماً بوضوح) -->
    <div class="cart-bar" onclick="sendCartToMessenger()">
        <span>🛒 إرسال الطلب عبر Facebook Messenger</span>
        <div class="cart-count" id="cart-count">0</div>
    </div>

    <footer>
        <p>© VELVET PARFUMS | جميع الحقوق محفوظة وتطوير VELVET PARFUMS</p>
    </footer>

    <script>
        const FB_PAGE_ID = "61596110442092";

        let perfumesList = [];
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
                        <p style="margin-top: 8px; font-size: 13px;">اضغط على زر <b>🔒 الإدارة</b> أعلى الصفحة لإضافة أول عطر!</p>
                    </div>
                `;
                return;
            }

            filteredItems.forEach(item => {
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <div class="product-badge">${item.category}</div>
                    <img src="${item.img}" class="product-img" alt="${item.name}">
                    <div class="product-info">
                        <div class="product-title">${item.name}</div>
                        <div class="product-desc">${item.desc}</div>
                        <div class="product-notes">${item.notes}</div>
                        
                        <!-- تغيير التصنيف مباشرة من بطاقة العطر -->
                        <div style="margin-bottom: 12px; display: flex; align-items: center; gap: 6px;">
                            <span style="font-size: 11px; color: var(--text-muted);">التصنيف:</span>
                            <select onchange="changePerfumeCategory(${item.id}, this.value)" style="font-size: 12px; padding: 3px 6px; border: 1px solid var(--border-color); border-radius: 4px; background: var(--bg-color); outline: none; cursor: pointer;">
                                <option value="شرقي" ${item.category === 'شرقي' ? 'selected' : ''}>شرقي</option>
                                <option value="رجالي" ${item.category === 'رجالي' ? 'selected' : ''}>رجالي</option>
                                <option value="نسائي" ${item.category === 'نسائي' ? 'selected' : ''}>نسائي</option>
                                <option value="نيش" ${item.category === 'نيش' ? 'selected' : ''}>نيش</option>
                            </select>
                        </div>

                        <div class="product-footer">
                            <div class="product-price">${item.price} د.ل</div>
                            <div class="actions-group">
                                <button class="btn-order" onclick="addToCart('${item.name}', ${item.price})">+ طلب</button>
                                <button class="btn-delete" onclick="deletePerfume(${item.id})" title="حذف العطر">حذف</button>
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
                    const MAX_WIDTH = 600;
                    const scaleFactor = MAX_WIDTH / img.width;
                    canvas.width = MAX_WIDTH;
                    canvas.height = img.height * scaleFactor;

                    const ctx = canvas.getContext('2d');
                    ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
                    
                    const compressedDataUrl = canvas.toDataURL('image/jpeg', 0.7);
                    callback(compressedDataUrl);
                }
            }
        }

        function addNewPerfume() {
            const name = document.getElementById('new-name').value.trim();
            const price = document.getElementById('new-price').value.trim();
            const cat = document.getElementById('new-cat').value;
            const notes = document.getElementById('new-notes').value.trim() || "تركيبة عطرة مميزة";
            const desc = document.getElementById('new-desc').value.trim() || "عطر فاخر ومميز من تشكيلة فيلقيت.";
            const fileInput = document.getElementById('new-img-file');

            if(!name || !price) {
                alert('الرجاء كتابة اسم العطر والسعر على الأقل.');
                return;
            }

            const defaultImg = "https://images.unsplash.com/photo-1588405748880-12d1d2a59f75?auto=format&fit=crop&q=80&w=600";

            if (fileInput.files && fileInput.files[0]) {
                compressAndProcessImage(fileInput.files[0], function(compressedImg) {
                    savePerfumeItem(name, price, cat, notes, desc, compressedImg);
                });
            } else {
                savePerfumeItem(name, price, cat, notes, desc, defaultImg);
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

        function addToCart(name, price) {
            selectedCart.push({ name, price });
            document.getElementById('cart-count').innerText = selectedCart.length;
        }

        function sendCartToMessenger() {
            if(selectedCart.length === 0) {
                alert('اختر عطراً أولاً لإرسال الطلب عبر الماسنجر.');
                return;
            }

            let totalPrice = 0;
            let summaryText = "أهلاً VELVET PARFUMS 👋 ، أرغب في طلب العطور التالية:\n\n";

            selectedCart.forEach((item, index) => {
                summaryText += `${index + 1}. ${item.name} - ${item.price} د.ل\n`;
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
