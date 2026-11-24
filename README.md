<!DOCTYPE html>
<html lang="ar" dir="rtl" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VelvetParfums | فيلفيت للعطور الفاخرة</title>
    <!-- استدعاء مكتبة Tailwind CSS للتصميم المتجاوب -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- استدعاء خطوط عربية فاخرة من Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Cairo:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <!-- استدعاء أيقونات FontAwesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- إعدادات مخصصة لـ Tailwind لدعم الخطوط والألوان الفاخرة -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Cairo', 'sans-serif'],
                        serif: ['Amiri', 'serif'],
                    },
                    colors: {
                        velvet: {
                            950: '#0a090c',
                            900: '#141218',
                            800: '#1f1c26',
                            700: '#2d2838',
                        },
                        gold: {
                            300: '#f3e5ab',
                            400: '#e5c158',
                            500: '#d4af37',
                            600: '#b59224',
                        }
                    }
                }
            }
        }
    </script>
</head>
<body class="bg-velvet-950 text-gray-100 font-sans antialiased selection:bg-gold-500 selection:text-velvet-950 overflow-x-hidden">

    <!-- ==================== الشريط العلوي (Navbar) ==================== -->
    <header class="fixed top-0 inset-x-0 z-40 bg-velvet-950/90 backdrop-blur-md border-b border-gold-500/20 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                
                <!-- الشعار المخصص لـ VelvetParfums (نقر مزدوج يفتح لوحة الإدارة السرية) -->
                <a href="#" ondblclick="requestAdminAccess()" class="flex items-center gap-3 group focus:outline-none" title="VelvetParfums">
                    <!-- تصميم الشعار بصيغة SVG (زجاجة عطر ملكية مع حرف V) -->
                    <div class="w-12 h-12 rounded-xl bg-gradient-to-br from-velvet-800 to-velvet-950 border border-gold-500/40 flex items-center justify-center shadow-lg shadow-gold-500/10 group-hover:border-gold-400 transition-all duration-300">
                        <svg class="w-8 h-8 text-gold-400 transform group-hover:scale-105 transition-transform" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <!-- غطاء الزجاجة -->
                            <rect x="25" y="6" width="14" height="8" rx="2" stroke="currentColor" stroke-width="2.5"/>
                            <path d="M28 14V19H36V14" stroke="currentColor" stroke-width="2"/>
                            <!-- جسم الزجاجة الماسي -->
                            <path d="M18 24C18 21.2386 20.2386 19 23 19H41C43.7614 19 46 21.2386 46 24V48C46 53.5228 41.5228 58 36 58H28C22.4772 58 18 53.5228 18 48V24Z" stroke="currentColor" stroke-width="2.5" fill="url(#goldGrad)" fill-opacity="0.15"/>
                            <!-- حرف V في المنتصف -->
                            <path d="M26 31L32 45L38 31" stroke="currentColor" stroke-width="2.8" stroke-linecap="round" stroke-linejoin="round"/>
                            <!-- لمعة -->
                            <circle cx="32" cy="25" r="1.5" fill="currentColor"/>
                            <defs>
                                <linearGradient id="goldGrad" x1="18" y1="19" x2="46" y2="58" gradientUnits="userSpaceOnUse">
                                    <stop stop-color="#D4AF37"/>
                                    <stop offset="1" stop-color="#141218" stop-opacity="0"/>
                                </linearGradient>
                            </defs>
                        </svg>
                    </div>
                    <div class="flex flex-col">
                        <span class="text-xl sm:text-2xl font-serif font-bold tracking-wider bg-gradient-to-l from-gold-300 via-gold-500 to-gold-300 bg-clip-text text-transparent">
                            VelvetParfums
                        </span>
                        <span class="text-[11px] text-gray-400 tracking-widest">فخامة العطور الشرقية والفرنسية</span>
                    </div>
                </a>

                <!-- روابط التنقل للشاشات الكبيرة -->
                <nav class="hidden md:flex items-center gap-8 text-sm font-semibold">
                    <a href="#home" class="text-gold-400 hover:text-gold-300 transition-colors">الرئيسية</a>
                    <a href="#collection" class="text-gray-300 hover:text-gold-400 transition-colors">تشكيلة العطور</a>
                    <a href="#scent-finder" class="text-gray-300 hover:text-gold-400 transition-colors">اكتشف عطرك</a>
                    <a href="#about" class="text-gray-300 hover:text-gold-400 transition-colors">قصتنا</a>
                </nav>

                <!-- أزرار التفاعل (السلة والقائمة) -->
                <div class="flex items-center gap-3">
                    <!-- زر السلة -->
                    <button type="button" onclick="toggleCart()" class="relative p-3 rounded-xl bg-velvet-800/80 hover:bg-velvet-700 border border-gold-500/30 text-gold-400 transition-all flex items-center gap-2">
                        <i class="fa-solid fa-bag-shopping text-lg"></i>
                        <span class="hidden sm:inline text-xs font-bold text-gray-200">السلة</span>
                        <span id="cart-badge" class="absolute -top-2 -left-2 bg-gold-500 text-velvet-950 text-xs font-extrabold w-5 h-5 rounded-full flex items-center justify-center shadow-md">
                            0
                        </span>
                    </button>

                    <!-- زر القائمة للهواتف -->
                    <button type="button" onclick="toggleMobileMenu()" class="md:hidden p-3 rounded-xl bg-velvet-800/80 border border-gold-500/30 text-gold-400">
                        <i class="fa-solid fa-bars text-lg"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- القائمة المنسدلة للهواتف -->
        <div id="mobile-menu" class="hidden md:hidden bg-velvet-900 border-b border-gold-500/20 px-4 pt-2 pb-6 space-y-2">
            <a href="#home" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl bg-velvet-800/50 text-gold-400 font-semibold">الرئيسية</a>
            <a href="#collection" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-velvet-800/50 text-gray-200">تشكيلة العطور</a>
            <a href="#scent-finder" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-velvet-800/50 text-gray-200">اكتشف عطرك</a>
            <a href="#about" onclick="toggleMobileMenu()" class="block px-4 py-3 rounded-xl hover:bg-velvet-800/50 text-gray-200">قصتنا</a>
        </div>
    </header>

    <!-- ==================== القسم الترحيبي (Hero Section) ==================== -->
    <section id="home" class="relative pt-28 pb-20 lg:pt-36 lg:pb-28 overflow-hidden">
        <!-- خلفيات جمالية متوهجة -->
        <div class="absolute top-20 right-10 w-72 h-72 bg-gold-500/10 rounded-full blur-3xl pointer-events-none"></div>
        <div class="absolute bottom-10 left-10 w-96 h-96 bg-purple-900/20 rounded-full blur-3xl pointer-events-none"></div>

        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
                
                <!-- النص التعريفي -->
                <div class="lg:col-span-7 text-center lg:text-right space-y-6">
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-velvet-800/80 border border-gold-500/30 text-gold-400 text-xs sm:text-sm font-semibold">
                        <i class="fa-solid fa-sparkles"></i>
                        <span>الإصدار الملكي الجديد لعام 2026</span>
                    </div>
                    
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-serif font-bold leading-tight text-white">
                        حيث يلتقي سحر <span class="text-gold-400">المخمل</span> بأرقى نفحات العطور
                    </h1>
                    
                    <p class="text-gray-300 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 leading-relaxed">
                        في <strong class="text-gold-400">VelvetParfums</strong>، نصنع لك أكثر من مجرد عطر؛ نصمم لك بصمة عطرية لا تُنسى تمزج بين عراقة العود الشرقي وأناقة الزهور الفرنسية النادرة.
                    </p>
                    
                    <div class="flex flex-col sm:flex-row items-center justify-center lg:justify-start gap-4 pt-4">
                        <a href="#collection" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-gradient-to-l from-gold-500 to-gold-400 text-velvet-950 font-bold text-base shadow-lg shadow-gold-500/25 hover:shadow-gold-500/40 transform hover:-translate-y-0.5 transition-all text-center">
                            تسوق المجموعة الآن
                        </a>
                        <a href="#scent-finder" class="w-full sm:w-auto px-8 py-4 rounded-xl bg-velvet-800/80 hover:bg-velvet-700 border border-gold-500/30 text-gold-300 font-semibold text-base transition-all text-center">
                            اكتشف عطرك المثالي
                        </a>
                    </div>

                    <!-- إحصائيات سريعة كما في التصميم الأول -->
                    <div class="grid grid-cols-3 gap-4 pt-8 border-t border-velvet-800 max-w-lg mx-auto lg:mx-0">
                        <div>
                            <div class="text-2xl font-bold text-gold-400">+100%</div>
                            <div class="text-xs text-gray-400">زيوت عطرية نقية</div>
                        </div>
                        <div>
                            <div class="text-2xl font-bold text-gold-400">48 ساعة</div>
                            <div class="text-xs text-gray-400">ثبات وفوحان عالي</div>
                        </div>
                        <div>
                            <div class="text-2xl font-bold text-gold-400">+25</div>
                            <div class="text-xs text-gray-400">توليفة حصرية</div>
                        </div>
                    </div>
                </div>

                <!-- بطاقة العرض البصري الفاخرة -->
                <div class="lg:col-span-5 relative">
                    <div class="relative rounded-3xl overflow-hidden border border-gold-500/30 bg-gradient-to-b from-velvet-800 to-velvet-900 p-4 shadow-2xl">
                        <img src="https://images.unsplash.com/photo-1594035910387-fea47794261f?auto=format&fit=crop&w=800&q=80" 
                             onerror="this.src='https://placehold.co/600x750/1f1c26/d4af37?text=Velvet+Royal+Oud'"
                             alt="عطر فيلفيت الملكي" 
                             class="w-full h-[420px] sm:h-[480px] object-cover rounded-2xl">
                        
                        <!-- بطاقة عائمة فوق الصورة -->
                        <div class="absolute bottom-8 inset-x-8 bg-velvet-950/90 backdrop-blur-md border border-gold-500/30 p-4 rounded-2xl flex items-center justify-between">
                            <div>
                                <span class="text-xs text-gold-400 font-semibold">الأكثر مبيعاً</span>
                                <h3 class="text-lg font-bold text-white">عطر فيلفيت رويال عود</h3>
                                <p class="text-xs text-gray-400">عود كمبودي • عنبر • زعفران</p>
                            </div>
                            <button type="button" onclick="addToCart(1)" class="px-4 py-2.5 rounded-xl bg-gold-500 text-velvet-950 font-bold text-sm hover:bg-gold-400 transition-colors">
                                450 د.ل
                            </button>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- ==================== قسم المميزات (Features) ==================== -->
    <section class="py-12 bg-velvet-900/50 border-y border-velvet-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                <div class="p-6 rounded-2xl bg-velvet-800/40 border border-velvet-700/50 flex items-start gap-4">
                    <div class="w-12 h-12 rounded-xl bg-gold-500/10 text-gold-400 flex items-center justify-center shrink-0 text-xl">
                        <i class="fa-solid fa-gem"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-white mb-1">مكونات نادرة</h4>
                        <p class="text-xs text-gray-400 leading-relaxed">نستخلص عطورنا من أندر الزهور والأخشاب العطرية حول العالم.</p>
                    </div>
                </div>
                <div class="p-6 rounded-2xl bg-velvet-800/40 border border-velvet-700/50 flex items-start gap-4">
                    <div class="w-12 h-12 rounded-xl bg-gold-500/10 text-gold-400 flex items-center justify-center shrink-0 text-xl">
                        <i class="fa-solid fa-truck-fast"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-white mb-1">توصيل سريع وآمن</h4>
                        <p class="text-xs text-gray-400 leading-relaxed">تغليف مخملي فاخر يحفظ العطر ويصلك لباب منزلك بأسرع وقت.</p>
                    </div>
                </div>
                <div class="p-6 rounded-2xl bg-velvet-800/40 border border-velvet-700/50 flex items-start gap-4">
                    <div class="w-12 h-12 rounded-xl bg-gold-500/10 text-gold-400 flex items-center justify-center shrink-0 text-xl">
                        <i class="fa-solid fa-certificate"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-white mb-1">ضمان الأصالة والثبات</h4>
                        <p class="text-xs text-gray-400 leading-relaxed">تركيز Extrait de Parfum يضمن لك ثباتاً يدوم لأكثر من 48 ساعة.</p>
                    </div>
                </div>
                <div class="p-6 rounded-2xl bg-velvet-800/40 border border-velvet-700/50 flex items-start gap-4">
                    <div class="w-12 h-12 rounded-xl bg-gold-500/10 text-gold-400 flex items-center justify-center shrink-0 text-xl">
                        <i class="fa-solid fa-gift"></i>
                    </div>
                    <div>
                        <h4 class="font-bold text-white mb-1">عينات مجانية</h4>
                        <p class="text-xs text-gray-400 leading-relaxed">احصل على عينتين مجانيتين من إصداراتنا الجديدة مع كل طلب.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== قسم تشكيلة العطور (Products Catalog) ==================== -->
    <section id="collection" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            
            <!-- عنوان القسم -->
            <div class="text-center max-w-2xl mx-auto mb-12 space-y-3">
                <span class="text-gold-400 text-sm font-bold tracking-wider">مجموعتنا الحصرية</span>
                <h2 class="text-3xl sm:text-4xl font-serif font-bold text-white">تشكيلة عطور VelvetParfums</h2>
                <p class="text-gray-400 text-sm sm:text-base">اختر من بين أرقى التركيبات العطرية المصممة بعناية لتناسب ذوقك الرفيع</p>
            </div>

            <!-- أزرار الفلترة والبحث -->
            <div class="flex flex-col md:flex-row justify-between items-center gap-4 mb-10">
                <!-- أزرار التصنيف -->
                <div class="flex flex-wrap justify-center gap-2" id="category-filters">
                    <button type="button" onclick="filterProducts('all')" class="filter-btn active px-5 py-2.5 rounded-xl text-sm font-bold bg-gold-500 text-velvet-950 transition-all">الكل</button>
                    <button type="button" onclick="filterProducts('men')" class="filter-btn px-5 py-2.5 rounded-xl text-sm font-semibold bg-velvet-800 text-gray-300 hover:bg-velvet-700 transition-all">رجالي</button>
                    <button type="button" onclick="filterProducts('women')" class="filter-btn px-5 py-2.5 rounded-xl text-sm font-semibold bg-velvet-800 text-gray-300 hover:bg-velvet-700 transition-all">نسائي</button>
                    <button type="button" onclick="filterProducts('unisex')" class="filter-btn px-5 py-2.5 rounded-xl text-sm font-semibold bg-velvet-800 text-gray-300 hover:bg-velvet-700 transition-all"> للجنسين (Unisex)</button>
                    <button type="button" onclick="filterProducts('oud')" class="filter-btn px-5 py-2.5 rounded-xl text-sm font-semibold bg-velvet-800 text-gray-300 hover:bg-velvet-700 transition-all">عود وبخور</button>
                </div>

                <!-- حقل البحث -->
                <div class="relative w-full md:w-72">
                    <input type="text" id="search-input" onkeyup="searchProducts()" placeholder="ابحث عن عطر أو مكون..." 
                           class="w-full bg-velvet-800/80 border border-velvet-700 focus:border-gold-500 rounded-xl py-2.5 pr-10 pl-4 text-sm text-white placeholder-gray-400 focus:outline-none">
                    <i class="fa-solid fa-magnifying-glass absolute right-3.5 top-3 text-gray-400 text-sm"></i>
                </div>
            </div>

            <!-- شبكة عرض المنتجات -->
            <div id="products-grid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- سيتم حقن المنتجات هنا عبر JavaScript -->
            </div>
        </div>
    </section>

    <!-- ==================== قسم مكتشف العطور التفاعلي (Scent Finder) ==================== -->
    <section id="scent-finder" class="py-20 bg-gradient-to-b from-velvet-900 to-velvet-950 border-t border-gold-500/20">
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="rounded-3xl bg-velvet-800/60 border border-gold-500/30 p-6 sm:p-10 text-center space-y-6 shadow-2xl">
                <div class="w-16 h-16 rounded-2xl bg-gold-500/10 text-gold-400 flex items-center justify-center mx-auto text-2xl border border-gold-500/30">
                    <i class="fa-solid fa-wand-magic-sparkles"></i>
                </div>
                <h2 class="text-2xl sm:text-3xl font-serif font-bold text-white">محتار في اختيار عطرك؟</h2>
                <p class="text-gray-300 text-sm sm:text-base max-w-xl mx-auto">
                    اختر الأجواء التي تفضلها وسيرشح لك خبير <span class="text-gold-400 font-bold">VelvetParfums</span> العطر المثالي لشخصيتك فوراً!
                </p>

                <!-- خيارات التفضيل -->
                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 pt-4">
                    <button type="button" onclick="recommendScent('woody')" class="p-4 rounded-2xl bg-velvet-900/90 hover:bg-velvet-700 border border-velvet-700 hover:border-gold-500 transition-all text-center group">
                        <i class="fa-solid fa-fire text-2xl text-gold-400 mb-2 group-hover:scale-110 transition-transform"></i>
                        <div class="font-bold text-white text-sm">دافئ وشرقي</div>
                        <div class="text-xs text-gray-400 mt-1">عود، عنبر، فانيليا</div>
                    </button>
                    <button type="button" onclick="recommendScent('floral')" class="p-4 rounded-2xl bg-velvet-900/90 hover:bg-velvet-700 border border-velvet-700 hover:border-gold-500 transition-all text-center group">
                        <i class="fa-solid fa-spa text-2xl text-gold-400 mb-2 group-hover:scale-110 transition-transform"></i>
                        <div class="font-bold text-white text-sm">ناعم وزهري</div>
                        <div class="text-xs text-gray-400 mt-1">ياسمين، ورد طائفي، مسك</div>
                    </button>
                    <button type="button" onclick="recommendScent('fresh')" class="p-4 rounded-2xl bg-velvet-900/90 hover:bg-velvet-700 border border-velvet-700 hover:border-gold-500 transition-all text-center group">
                        <i class="fa-solid fa-wind text-2xl text-gold-400 mb-2 group-hover:scale-110 transition-transform"></i>
                        <div class="font-bold text-white text-sm">منعش وحيوي</div>
                        <div class="text-xs text-gray-400 mt-1">برغموت، حمضيات، أخشاب</div>
                    </button>
                </div>

                <!-- نتيجة الترشيح -->
                <div id="scent-result" class="hidden mt-6 p-6 rounded-2xl bg-velvet-950/80 border border-gold-500/40 text-right">
                    <!-- يملأ ديناميكياً -->
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== قسم قصتنا (About) ==================== -->
    <section id="about" class="py-20 border-t border-velvet-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                <div class="space-y-6">
                    <span class="text-gold-400 text-sm font-bold">عن علامتنا التجارية</span>
                    <h2 class="text-3xl sm:text-4xl font-serif font-bold text-white">قصة شغف اسمها VelvetParfums</h2>
                    <p class="text-gray-300 leading-relaxed">
                        انطلقت <span class="text-gold-400 font-semibold">VelvetParfums</span> من رؤية واضحة: تقديم تجربة عطرية تلامس الحواس بنعومة المخمل وقوة الحضور. نؤمن بأن العطر هو توقيعك غير المرئي، لذا نحرص على تعتيق زيوتنا العطرية لفترات طويلة لضمان نقاء الرائحة وثباتها الاستثنائي.
                    </p>
                    <div class="flex items-center gap-4 pt-2">
                        <div class="p-4 rounded-2xl bg-velvet-800 border border-velvet-700">
                            <div class="text-gold-400 font-bold text-lg">صناعة حرفية</div>
                            <div class="text-xs text-gray-400">تعبئة وتغليف يدوي فائق الدقة</div>
                        </div>
                        <div class="p-4 rounded-2xl bg-velvet-800 border border-velvet-700">
                            <div class="text-gold-400 font-bold text-lg">مكونات آمنة</div>
                            <div class="text-xs text-gray-400">مطابقة لأعلى معايير الجودة العالمية</div>
                        </div>
                    </div>
                </div>
                <div class="grid grid-cols-2 gap-4">
                    <img src="https://images.unsplash.com/photo-1615634260167-c8cdede054de?auto=format&fit=crop&w=500&q=80" 
                         onerror="this.src='https://placehold.co/400x500/1f1c26/d4af37?text=Velvet+Essence'"
                         alt="صناعة العطور" class="rounded-2xl h-64 w-full object-cover border border-gold-500/20">
                    <img src="https://images.unsplash.com/photo-1541643600914-78b084683601?auto=format&fit=crop&w=500&q=80" 
                         onerror="this.src='https://placehold.co/400x500/1f1c26/d4af37?text=Luxury+Bottle'"
                         alt="زجاجات عطور فاخرة" class="rounded-2xl h-64 w-full object-cover mt-8 border border-gold-500/20">
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== التذييل (Footer) ==================== -->
    <footer class="bg-velvet-900 border-t border-gold-500/20 pt-16 pb-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-10 pb-12 border-b border-velvet-800">
                <!-- معلومات المتجر والشعار -->
                <div class="space-y-4">
                    <div class="flex items-center gap-3">
                        <div class="w-10 h-10 rounded-xl bg-velvet-950 border border-gold-500/40 flex items-center justify-center text-gold-400 font-serif font-bold text-xl">
                            V
                        </div>
                        <span class="text-2xl font-serif font-bold text-gold-400">VelvetParfums</span>
                    </div>
                    <p class="text-gray-400 text-sm leading-relaxed">
                        وجهتك الأولى لعالم العطور النيش والفاخرة. نجمع لك بين أصالة الشرق وسحر الغرب في زجاجة واحدة.
                    </p>
                    <div class="flex gap-3 pt-2">
                        <a href="#" class="w-10 h-10 rounded-xl bg-velvet-800 hover:bg-gold-500 hover:text-velvet-950 text-gold-400 flex items-center justify-center transition-colors"><i class="fa-brands fa-instagram"></i></a>
                        <a href="#" class="w-10 h-10 rounded-xl bg-velvet-800 hover:bg-gold-500 hover:text-velvet-950 text-gold-400 flex items-center justify-center transition-colors"><i class="fa-brands fa-facebook-f"></i></a>
                        <a href="#" class="w-10 h-10 rounded-xl bg-velvet-800 hover:bg-gold-500 hover:text-velvet-950 text-gold-400 flex items-center justify-center transition-colors"><i class="fa-brands fa-whatsapp"></i></a>
                    </div>
                </div>

                <!-- روابط سريعة -->
                <div>
                    <h4 class="text-white font-bold mb-4">روابط سريعة</h4>
                    <ul class="space-y-2 text-sm text-gray-400">
                        <li><a href="#home" class="hover:text-gold-400 transition-colors">الرئيسية</a></li>
                        <li><a href="#collection" class="hover:text-gold-400 transition-colors">جميع العطور</a></li>
                        <li><a href="#scent-finder" class="hover:text-gold-400 transition-colors">اختبار اختيار العطر</a></li>
                        <li><a href="#about" class="hover:text-gold-400 transition-colors">من نحن</a></li>
                    </ul>
                </div>

                <!-- النشرة البريدية -->
                <div>
                    <h4 class="text-white font-bold mb-4">انضم لنادي كبار الشخصيات</h4>
                    <p class="text-gray-400 text-sm mb-4">اشترك للحصول على خصم 15% على طلبك الأول وأحدث الإصدارات الحصرية.</p>
                    <form onsubmit="subscribeNewsletter(event)" class="flex gap-2">
                        <input type="email" required placeholder="بريدك الإلكتروني..." class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-4 py-2.5 text-sm text-white focus:outline-none focus:border-gold-500">
                        <button type="submit" class="px-5 py-2.5 rounded-xl bg-gold-500 text-velvet-950 font-bold text-sm hover:bg-gold-400 transition-colors shrink-0">
                            اشتراك
                        </button>
                    </form>
                </div>
            </div>

            <div class="pt-8 text-center text-xs text-gray-500">
                <span>&copy; 2026 جميع الحقوق محفوظة لمتجر <span class="text-gold-400 font-semibold">VelvetParfums</span>.</span>
            </div>
        </div>
    </footer>

    <!-- زر الإدارة العائم في الزاوية السفلية اليسرى لسهولة الوصول السريع لصاحب المتجر -->
    <button type="button" onclick="requestAdminAccess()" 
            class="fixed bottom-5 left-5 z-40 w-11 h-11 rounded-2xl bg-velvet-900/90 hover:bg-velvet-800 border border-gold-500/30 hover:border-gold-400 text-gold-400 shadow-xl backdrop-blur-md flex items-center justify-center transition-all group"
            title="إدارة المتجر (للمالك فقط)">
        <i class="fa-solid fa-key text-sm group-hover:rotate-12 transition-transform"></i>
    </button>

    <!-- ==================== نافذة تفاصيل العطر (Product Modal) ==================== -->
    <div id="product-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-velvet-900 border border-gold-500/30 rounded-3xl max-w-2xl w-full overflow-hidden shadow-2xl relative">
            <button type="button" onclick="closeProductModal()" class="absolute top-4 left-4 w-10 h-10 rounded-full bg-velvet-800 text-gray-300 hover:text-white flex items-center justify-center z-10">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <div id="modal-content" class="grid grid-cols-1 md:grid-cols-2">
                <!-- يملأ ديناميكياً -->
            </div>
        </div>
    </div>

    <!-- ==================== سلة التسوق الجانبية (Cart Drawer) ==================== -->
    <div id="cart-drawer" class="fixed inset-0 z-50 hidden">
        <!-- خلفية معتمة -->
        <div onclick="toggleCart()" class="absolute inset-0 bg-black/70 backdrop-blur-sm"></div>
        
        <!-- محتوى السلة -->
        <div class="absolute top-0 left-0 bottom-0 w-full max-w-md bg-velvet-900 border-r border-gold-500/30 flex flex-col shadow-2xl">
            <div class="p-6 border-b border-velvet-800 flex justify-between items-center">
                <div class="flex items-center gap-2">
                    <i class="fa-solid fa-bag-shopping text-gold-400 text-xl"></i>
                    <h3 class="text-lg font-bold text-white">سلة مشترياتك</h3>
                </div>
                <button type="button" onclick="toggleCart()" class="p-2 rounded-xl bg-velvet-800 text-gray-400 hover:text-white">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <!-- قائمة المنتجات في السلة -->
            <div id="cart-items" class="flex-1 overflow-y-auto p-6 space-y-4">
                <!-- يملأ ديناميكياً -->
            </div>

            <!-- ملخص الدفع وإتمام الطلب -->
            <div class="p-6 border-t border-velvet-800 bg-velvet-950/60 space-y-4">
                <!-- اختيار طريقة الدفع داخل السلة -->
                <div class="space-y-2">
                    <span class="block text-xs text-gray-400">طريقة الدفع المفضلة:</span>
                    <div class="grid grid-cols-2 gap-2">
                        <label class="cursor-pointer">
                            <input type="radio" name="cart-payment" value="cash" checked onchange="syncPaymentMethod('cash')" class="peer sr-only">
                            <div class="p-2.5 rounded-xl bg-velvet-900 border border-velvet-700 peer-checked:border-gold-500 peer-checked:bg-gold-500/10 text-center transition-all flex items-center justify-center gap-2 text-xs font-bold text-gray-300 peer-checked:text-gold-400">
                                <i class="fa-solid fa-money-bill-wave"></i>
                                <span>كاش</span>
                            </div>
                        </label>
                        <label class="cursor-pointer">
                            <input type="radio" name="cart-payment" value="transfer" onchange="syncPaymentMethod('transfer')" class="peer sr-only">
                            <div class="p-2.5 rounded-xl bg-velvet-900 border border-velvet-700 peer-checked:border-gold-500 peer-checked:bg-gold-500/10 text-center transition-all flex items-center justify-center gap-2 text-xs font-bold text-gray-300 peer-checked:text-gold-400">
                                <i class="fa-solid fa-building-columns"></i>
                                <span>حوالة مصرفية</span>
                            </div>
                        </label>
                    </div>
                </div>

                <div class="flex justify-between items-center text-sm pt-1 border-t border-velvet-800/80">
                    <span class="text-gray-400">المجموع الفرعي:</span>
                    <span id="cart-total" class="text-xl font-bold text-gold-400">0 د.ل</span>
                </div>
                <button type="button" onclick="checkout()" id="checkout-btn" class="w-full py-3.5 rounded-xl bg-gradient-to-l from-gold-500 to-gold-400 text-velvet-950 font-bold text-base shadow-lg hover:opacity-95 transition-all disabled:opacity-50">
                    إتمام الطلب الآن
                </button>
            </div>
        </div>
    </div>

    <!-- ==================== نافذة إتمام الطلب (Checkout Modal) ==================== -->
    <div id="checkout-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-velvet-900 border border-gold-500/30 rounded-3xl max-w-md w-full p-6 sm:p-8 shadow-2xl relative my-8">
            <button type="button" onclick="closeCheckoutModal()" class="absolute top-4 left-4 w-9 h-9 rounded-full bg-velvet-800 text-gray-400 hover:text-white flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <h3 class="text-2xl font-serif font-bold text-gold-400 mb-2">إتمام الطلب</h3>
            <p class="text-xs text-gray-400 mb-6">أدخل بيانات التوصيل وسنقوم بتجهيز عطرك وتغليفه فوراً.</p>
            
            <form onsubmit="submitOrder(event)" class="space-y-4">
                <div>
                    <label class="block text-xs text-gray-300 mb-1">الاسم الكامل</label>
                    <input type="text" required placeholder="مثال: أحمد محمد" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-4 py-3 text-sm text-white focus:border-gold-500 focus:outline-none">
                </div>
                <div>
                    <label class="block text-xs text-gray-300 mb-1">رقم الهاتف</label>
                    <input type="tel" required placeholder="09X XXXXXXX" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-4 py-3 text-sm text-white focus:border-gold-500 focus:outline-none">
                </div>
                <div>
                    <label class="block text-xs text-gray-300 mb-1">المدينة والعنوان</label>
                    <input type="text" required placeholder="طرابلس - حي الأندلس" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-4 py-3 text-sm text-white focus:border-gold-500 focus:outline-none">
                </div>

                <!-- تأكيد طريقة الدفع في نافذة الطلب -->
                <div>
                    <label class="block text-xs text-gray-300 mb-1.5">طريقة الدفع</label>
                    <div class="grid grid-cols-2 gap-2.5">
                        <label class="cursor-pointer">
                            <input type="radio" name="modal-payment" value="cash" checked onchange="syncPaymentMethod('cash')" class="peer sr-only">
                            <div class="p-3 rounded-xl bg-velvet-950 border border-velvet-700 peer-checked:border-gold-500 peer-checked:bg-gold-500/10 text-center transition-all flex items-center justify-center gap-2 text-xs font-bold text-gray-300 peer-checked:text-gold-400">
                                <i class="fa-solid fa-money-bill-wave"></i>
                                <span>كاش عند الاستلام</span>
                            </div>
                        </label>
                        <label class="cursor-pointer">
                            <input type="radio" name="modal-payment" value="transfer" onchange="syncPaymentMethod('transfer')" class="peer sr-only">
                            <div class="p-3 rounded-xl bg-velvet-950 border border-velvet-700 peer-checked:border-gold-500 peer-checked:bg-gold-500/10 text-center transition-all flex items-center justify-center gap-2 text-xs font-bold text-gray-300 peer-checked:text-gold-400">
                                <i class="fa-solid fa-building-columns"></i>
                                <span>حوالة مصرفية</span>
                            </div>
                        </label>
                    </div>
                </div>

                <button type="submit" id="submit-order-btn" class="w-full py-3.5 rounded-xl bg-gradient-to-l from-gold-500 to-gold-400 text-velvet-950 font-bold text-base shadow-lg hover:opacity-95 transition-all mt-2">
                    تأكيد الطلب (دفع كاش عند الاستلام)
                </button>
            </form>
        </div>
    </div>

    <!-- ==================== نافذة كلمة مرور المدير (Admin Login Modal) ==================== -->
    <div id="admin-login-modal" class="fixed inset-0 z-50 hidden bg-black/85 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-velvet-900 border border-gold-500/40 rounded-3xl max-w-sm w-full p-6 shadow-2xl relative text-center">
            <button type="button" onclick="closeAdminLoginModal()" class="absolute top-4 left-4 w-8 h-8 rounded-full bg-velvet-800 text-gray-400 hover:text-white flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>
            <div class="w-12 h-12 rounded-2xl bg-gold-500/10 text-gold-400 flex items-center justify-center mx-auto mb-3 border border-gold-500/30 text-xl">
                <i class="fa-solid fa-shield-halved"></i>
            </div>
            <h3 class="text-lg font-serif font-bold text-gold-400 mb-1">منطقة صاحب المتجر</h3>
            <p class="text-xs text-gray-400 mb-4">أدخل الرمز السري لإضافة أو حذف العطور</p>
            <form onsubmit="verifyAdminPin(event)" class="space-y-3">
                <input type="password" id="admin-pin-input" required placeholder="أدخل الرمز السري..." class="w-full text-center tracking-widest bg-velvet-950 border border-velvet-700 rounded-xl px-4 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                <button type="submit" class="w-full py-2.5 rounded-xl bg-gold-500 text-velvet-950 font-bold text-sm hover:bg-gold-400 transition-colors">
                    دخول
                </button>
            </form>
        </div>
    </div>

    <!-- ==================== نافذة إضافة وحذف العطور (Admin Modal) ==================== -->
    <div id="admin-modal" class="fixed inset-0 z-50 hidden bg-black/80 backdrop-blur-sm flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-velvet-900 border border-gold-500/40 rounded-3xl max-w-lg w-full p-6 sm:p-8 shadow-2xl relative my-8">
            <button type="button" onclick="closeAdminModal()" class="absolute top-4 left-4 w-9 h-9 rounded-full bg-velvet-800 text-gray-400 hover:text-white flex items-center justify-center">
                <i class="fa-solid fa-xmark"></i>
            </button>
            
            <div class="flex items-center gap-3 mb-2">
                <div class="w-10 h-10 rounded-xl bg-gold-500/10 text-gold-400 flex items-center justify-center border border-gold-500/30">
                    <i class="fa-solid fa-spray-can-sparkles"></i>
                </div>
                <div>
                    <h3 class="text-xl font-serif font-bold text-gold-400">لوحة إدارة صاحب المتجر</h3>
                    <p class="text-xs text-gray-400">إحصائيات الزوار الخاصة بك وإدارة العطور</p>
                </div>
            </div>

            <!-- ملخص إحصائيات الزوار الخاصة بصاحب المتجر فقط -->
            <div class="grid grid-cols-2 gap-3 my-4 p-3.5 rounded-2xl bg-velvet-950/90 border border-gold-500/30">
                <div class="text-center border-l border-velvet-800">
                    <span class="text-[11px] text-gray-400 flex items-center justify-center gap-1.5 mb-1">
                        <span class="w-2 h-2 rounded-full bg-green-500 animate-pulse"></span>
                        <span>زوار المتجر اليوم</span>
                    </span>
                    <span id="admin-today-visitors" class="text-xl font-extrabold text-green-400">124</span>
                </div>
                <div class="text-center">
                    <span class="text-[11px] text-gray-400 block mb-1">العدد الإجمالي للزوار</span>
                    <span id="admin-total-visitors" class="text-xl font-extrabold text-gold-400">5,480</span>
                </div>
            </div>
            
            <form onsubmit="addNewPerfume(event)" class="space-y-4 mt-4">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-xs text-gray-300 mb-1">اسم العطر (بالعربي) *</label>
                        <input type="text" id="new-name" required placeholder="مثال: مسك الليل" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                    </div>
                    <div>
                        <label class="block text-xs text-gray-300 mb-1">الاسم الإنجليزي *</label>
                        <input type="text" id="new-subtitle" required placeholder="مثال: Night Musk" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                    </div>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-3 gap-4">
                    <div>
                        <label class="block text-xs text-gray-300 mb-1">السعر (د.ل) *</label>
                        <input type="number" id="new-price" required min="1" placeholder="350" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                    </div>
                    <div>
                        <label class="block text-xs text-gray-300 mb-1">الحجم *</label>
                        <input type="text" id="new-size" required value="100 مل" placeholder="100 مل" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                    </div>
                    <div>
                        <label class="block text-xs text-gray-300 mb-1">التصنيف *</label>
                        <select id="new-category" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                            <option value="men">رجالي</option>
                            <option value="women">نسائي</option>
                            <option value="unisex">للجنسين</option>
                            <option value="oud">عود وبخور</option>
                        </select>
                    </div>
                </div>

                <div>
                    <label class="block text-xs text-gray-300 mb-1">رابط صورة العطر (اختياري)</label>
                    <input type="url" id="new-image" placeholder="https://example.com/perfume.jpg" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                    <span class="text-[11px] text-gray-500">إذا تركته فارغاً سيتم وضع صورة زجاجة عطر فاخرة تلقائياً.</span>
                </div>

                <div>
                    <label class="block text-xs text-gray-300 mb-1">مكونات العطر (النوتات العطرية) *</label>
                    <input type="text" id="new-notes" required placeholder="مثال: زعفران، ورد طائفي، عود كمبودي، مسك" class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none">
                </div>

                <div>
                    <label class="block text-xs text-gray-300 mb-1">وصف قصير للعطر *</label>
                    <textarea id="new-desc" required rows="2" placeholder="اكتب وصفاً جذاباً يوضح فخامة العطر وثباته..." class="w-full bg-velvet-950 border border-velvet-700 rounded-xl px-3.5 py-2.5 text-sm text-white focus:border-gold-500 focus:outline-none"></textarea>
                </div>

                <div class="flex gap-3 pt-2">
                    <button type="submit" class="flex-1 py-3 rounded-xl bg-gradient-to-l from-gold-500 to-gold-400 text-velvet-950 font-bold text-sm hover:opacity-95 transition-all">
                        <i class="fa-solid fa-check ml-1"></i> نشر العطر في المتجر
                    </button>
                    <button type="button" onclick="logoutAdmin()" class="px-4 py-3 rounded-xl bg-velvet-800 hover:bg-red-900/50 text-gray-300 hover:text-red-300 text-xs font-semibold transition-colors" title="قفل وضع الإدارة">
                        <i class="fa-solid fa-lock"></i> قفل
                    </button>
                </div>
            </form>

            <!-- قائمة العطور الحالية في المتجر للحذف السريع -->
            <div class="mt-6 pt-5 border-t border-velvet-800">
                <h4 class="text-xs font-bold text-gray-300 mb-3 flex items-center justify-between">
                    <span>العطور الموجودة حالياً في المتجر (اضغط مسح لإزالة أي عطر):</span>
                    <span id="admin-perfumes-count" class="text-gold-400">0</span>
                </h4>
                <div id="admin-perfumes-list" class="max-h-48 overflow-y-auto space-y-2 pr-1">
                    <!-- يتم تعبئتها ديناميكياً -->
                </div>
            </div>
        </div>
    </div>

    <!-- ==================== إشعار منبثق (Toast Notification) ==================== -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-24 opacity-0 transition-all duration-300 bg-velvet-800 border border-gold-500 text-white px-5 py-3.5 rounded-2xl shadow-2xl flex items-center gap-3">
        <i class="fa-solid fa-circle-check text-gold-400 text-lg"></i>
        <span id="toast-msg" class="text-sm font-semibold">تمت الإضافة للسلة بنجاح</span>
    </div>

    <!-- ==================== كود JavaScript الكامل للتفاعلية وإدارة المتجر ==================== -->
    <script>
        // قاعدة بيانات العطور الافتراضية الخاصة بمتجر VelvetParfums
        const defaultPerfumes = [
            {
                id: 1,
                name: "فيلفيت رويال عود",
                subtitle: "Velvet Royal Oud",
                category: "oud",
                categoryLabel: "عود فاخر",
                scentType: "woody",
                price: 450,
                size: "100 مل",
                image: "https://images.unsplash.com/photo-1594035910387-fea47794261f?auto=format&fit=crop&w=600&q=80",
                notes: {
                    top: "الزعفران، جوزة الطيب",
                    heart: "العود الكمبودي المعتق، الورد الدمشقي",
                    base: "العنبر الملكي، المسك الأسود، خشب الصندل"
                },
                description: "عطر ملكي يجسد الفخامة الشرقية الأصيلة بلمسة مخملية ناعمة تدوم لساعات طويلة وتترك أثراً لا يُقاوم."
            },
            {
                id: 2,
                name: "نوار دي فيلفيت",
                subtitle: "Noir de Velvet",
                category: "men",
                categoryLabel: "رجالي",
                scentType: "woody",
                price: 380,
                size: "100 مل",
                image: "https://images.unsplash.com/photo-1523293182086-7651a899d37f?auto=format&fit=crop&w=600&q=80",
                notes: {
                    top: "البرغموت الإيطالي، الفلفل الأسود",
                    heart: "الجلود الفاخرة، الباتشولي، البخور",
                    base: "نجيل الهند، التونكا، الفانيليا الداكنة"
                },
                description: "عطر رجالي غامض وجريء مصمم للرجل الواثق في الأمسيات الخاصة والمناسبات الرسمية."
            },
            {
                id: 3,
                name: "فيلفيت روز إمبريال",
                subtitle: "Velvet Rose Impériale",
                category: "women",
                categoryLabel: "نسائي",
                scentType: "floral",
                price: 410,
                size: "100 مل",
                image: "https://images.unsplash.com/photo-1592945403244-b3fbafd7f539?auto=format&fit=crop&w=600&q=80",
                notes: {
                    top: "الليتشي، الكمثرى، الفلفل الوردي",
                    heart: "الورد الطائفي، الفاوانيا، الياسمين",
                    base: "المسك الأبيض، الكشمير، الفانيليا"
                },
                description: "باقة زهرية ساحرة تفيض بالأنوثة والرقي، تمنحك إحساساً بالنعومة والجاذبية في كل لحظة."
            },
            {
                id: 4,
                name: "عنبر سيلك",
                subtitle: "Amber Silk",
                category: "unisex",
                categoryLabel: "للجنسين",
                scentType: "woody",
                price: 430,
                size: "100 مل",
                image: "https://images.unsplash.com/photo-1587017539504-67cfbddac569?auto=format&fit=crop&w=600&q=80",
                notes: {
                    top: "الماندرين، الهيل",
                    heart: "العنبر الذهبي، السوسن",
                    base: "خشب الأرز، البنزوين، المسك"
                },
                description: "توازن مثالي بين دفء العنبر ونعومة الحرير، يناسب الرجال والنساء الباحثين عن التميز."
            },
            {
                id: 5,
                name: "بريز دي فيلفيت",
                subtitle: "Brise de Velvet",
                category: "unisex",
                categoryLabel: "للجنسين",
                scentType: "fresh",
                price: 340,
                size: "100 مل",
                image: "https://images.unsplash.com/photo-1595425970377-c9703cf48b6d?auto=format&fit=crop&w=600&q=80",
                notes: {
                    top: "الليمون الصقلي، الجريب فروت، النعناع",
                    heart: "زهر البرتقال، الشاي الأخضر",
                    base: "المسك النظيف، خشب الأرز الأبيض"
                },
                description: "انتعاش صباحي نقي يمنحك طاقة وحيوية طوال اليوم، مثالي للأجواء الدافئة والعمل."
            },
            {
                id: 6,
                name: "سلطان المسك",
                subtitle: "Sultan Al Musk",
                category: "oud",
                categoryLabel: "عود وبخور",
                scentType: "floral",
                price: 470,
                size: "100 مل",
                image: "https://images.unsplash.com/photo-1585386959984-a4155224a1ad?auto=format&fit=crop&w=600&q=80",
                notes: {
                    top: "المسك الغزالي النقي، الزعفران",
                    heart: "دهن العود الهندي، الورد",
                    base: "خشب الصندل، البخور الملكي"
                },
                description: "توليفة شرقية فاخرة لعشاق المسك والعود الأصيل بتركيز عالٍ وثبات يدوم لأيام."
            }
        ];

        // تحميل العطور المحفوظة أو استخدام الافتراضية
        let perfumes = JSON.parse(localStorage.getItem('velvet_perfumes')) || [...defaultPerfumes];

        // حالة السلة والتصفية وصلاحية المدير وطريقة الدفع
        let cart = [];
        let currentCategory = 'all';
        let isAdminAuthenticated = false;
        let selectedPaymentMethod = 'cash';
        const ADMIN_SECRET_PIN = "2026"; // الرمز السري لصاحب المتجر

        // نظام حساب عدد زوار اليوم والعدد الإجمالي (خاص بالمدير فقط)
        function initVisitorStats() {
            try {
                const todayDate = new Date().toISOString().split('T')[0];
                let stats = JSON.parse(localStorage.getItem('velvet_visitor_stats'));

                if (!stats) {
                    stats = {
                        date: todayDate,
                        today: 124,
                        total: 5480
                    };
                } else if (stats.date !== todayDate) {
                    stats.date = todayDate;
                    stats.today = 1;
                    stats.total += 1;
                } else {
                    stats.today += 1;
                    stats.total += 1;
                }

                localStorage.setItem('velvet_visitor_stats', JSON.stringify(stats));

                const todayEl = document.getElementById('admin-today-visitors');
                const totalEl = document.getElementById('admin-total-visitors');
                if (todayEl) todayEl.textContent = stats.today.toLocaleString();
                if (totalEl) totalEl.textContent = stats.total.toLocaleString();
            } catch (e) {
                console.error("Error updating visitor stats:", e);
            }
        }

        // طلب الدخول للوحة الإدارة
        function requestAdminAccess() {
            if (isAdminAuthenticated) {
                openAdminModal();
            } else {
                document.getElementById('admin-login-modal').classList.remove('hidden');
                setTimeout(() => {
                    const pinInput = document.getElementById('admin-pin-input');
                    if (pinInput) pinInput.focus();
                }, 100);
            }
        }

        function closeAdminLoginModal() {
            document.getElementById('admin-login-modal').classList.add('hidden');
            document.getElementById('admin-pin-input').value = '';
        }

        function verifyAdminPin(e) {
            e.preventDefault();
            const enteredPin = document.getElementById('admin-pin-input').value;
            if (enteredPin === ADMIN_SECRET_PIN) {
                isAdminAuthenticated = true;
                closeAdminLoginModal();
                renderProducts(perfumes);
                openAdminModal();
                showToast("مرحباً بك في وضع إدارة المتجر!");
            } else {
                showToast("الرمز السري غير صحيح!");
                document.getElementById('admin-pin-input').value = '';
            }
        }

        function logoutAdmin() {
            isAdminAuthenticated = false;
            closeAdminModal();
            renderProducts(perfumes);
            showToast("تم قفل وضع الإدارة.");
        }

        // مزامنة اختيار طريقة الدفع (كاش أم حوالة) بين السلة ونافذة إتمام الطلب
        function syncPaymentMethod(method) {
            selectedPaymentMethod = method;
            
            document.querySelectorAll(`input[name="cart-payment"][value="${method}"]`).forEach(el => el.checked = true);
            document.querySelectorAll(`input[name="modal-payment"][value="${method}"]`).forEach(el => el.checked = true);

            const submitBtn = document.getElementById('submit-order-btn');
            if (submitBtn) {
                submitBtn.textContent = method === 'transfer' 
                    ? 'تأكيد الطلب (الدفع عبر حوالة مصرفية)' 
                    : 'تأكيد الطلب (دفع كاش عند الاستلام)';
            }
        }

        // عرض العطور في الشبكة
        function renderProducts(list) {
            const grid = document.getElementById('products-grid');
            if (!grid) return;

            if (list.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full text-center py-12 text-gray-400">
                        <i class="fa-solid fa-spray-can-sparkles text-4xl text-gold-500/40 mb-3"></i>
                        <p>لم يتم العثور على عطور تطابق بحثك الحالي.</p>
                    </div>
                `;
                return;
            }

            grid.innerHTML = list.map(perfume => `
                <div class="group rounded-3xl bg-velvet-900 border border-velvet-800 hover:border-gold-500/40 overflow-hidden transition-all duration-300 flex flex-col justify-between shadow-lg hover:shadow-gold-500/10">
                    <div>
                        <!-- صورة العطر -->
                        <div class="relative h-72 overflow-hidden bg-velvet-950">
                            <img src="${perfume.image}" 
                                 onerror="this.src='https://placehold.co/600x600/141218/d4af37?text=${encodeURIComponent(perfume.subtitle)}'"
                                 alt="${perfume.name}" 
                                 class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                            
                            <!-- شارة التصنيف -->
                            <span class="absolute top-4 right-4 px-3 py-1 rounded-full bg-velvet-950/85 backdrop-blur-md border border-gold-500/30 text-gold-400 text-xs font-bold">
                                ${perfume.categoryLabel}
                            </span>

                            <!-- زر حذف العطر (يظهر فقط للمدير) -->
                            ${isAdminAuthenticated ? `
                                <button type="button" onclick="deletePerfume(${perfume.id})" class="absolute top-4 left-4 w-8 h-8 rounded-full bg-red-600/90 hover:bg-red-500 text-white flex items-center justify-center shadow-lg transition-colors" title="حذف العطر">
                                    <i class="fa-solid fa-trash-can text-xs"></i>
                                </button>
                            ` : ''}

                            <!-- زر معاينة سريعة -->
                            <button type="button" onclick="openProductModal(${perfume.id})" class="absolute bottom-4 left-4 px-3.5 py-2 rounded-xl bg-velvet-950/85 hover:bg-gold-500 hover:text-velvet-950 text-white text-xs font-semibold backdrop-blur-md border border-white/10 transition-colors flex items-center gap-1.5">
                                <i class="fa-solid fa-eye"></i>
                                <span>المكونات</span>
                            </button>
                        </div>

                        <!-- تفاصيل البطاقة -->
                        <div class="p-6 space-y-2">
                            <div class="flex justify-between items-start">
                                <div>
                                    <h3 class="text-xl font-bold text-white group-hover:text-gold-400 transition-colors">${perfume.name}</h3>
                                    <span class="text-xs text-gray-500 font-serif tracking-wider">${perfume.subtitle}</span>
                                </div>
                                <span class="text-xs text-gray-400 bg-velvet-800 px-2.5 py-1 rounded-lg">${perfume.size}</span>
                            </div>
                            <p class="text-gray-400 text-xs leading-relaxed line-clamp-2 pt-1">
                                ${perfume.description}
                            </p>
                        </div>
                    </div>

                    <!-- السعر وزر الإضافة للسلة -->
                    <div class="px-6 pb-6 pt-2 flex items-center justify-between border-t border-velvet-800/60 mt-2">
                        <div>
                            <span class="text-xs text-gray-400 block">السعر</span>
                            <span class="text-xl font-extrabold text-gold-400">${perfume.price} د.ل</span>
                        </div>
                        <button type="button" onclick="addToCart(${perfume.id})" class="px-5 py-3 rounded-xl bg-velvet-800 hover:bg-gold-500 text-gold-400 hover:text-velvet-950 border border-gold-500/30 font-bold text-sm transition-all flex items-center gap-2">
                            <i class="fa-solid fa-cart-plus"></i>
                            <span>أضف للسلة</span>
                        </button>
                    </div>
                </div>
            `).join('');
        }

        // تصفية العطور حسب الفئة
        function filterProducts(category) {
            currentCategory = category;
            
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('bg-gold-500', 'text-velvet-950', 'font-bold');
                btn.classList.add('bg-velvet-800', 'text-gray-300', 'font-semibold');
            });
            if (event && event.target) {
                event.target.classList.remove('bg-velvet-800', 'text-gray-300', 'font-semibold');
                event.target.classList.add('bg-gold-500', 'text-velvet-950', 'font-bold');
            }

            applyFilters();
        }

        // البحث بالاسم أو المكونات
        function searchProducts() {
            applyFilters();
        }

        function applyFilters() {
            const query = document.getElementById('search-input').value.trim().toLowerCase();
            const filtered = perfumes.filter(p => {
                const matchCategory = currentCategory === 'all' || p.category === currentCategory;
                const matchSearch = p.name.toLowerCase().includes(query) || 
                                    p.subtitle.toLowerCase().includes(query) ||
                                    p.description.toLowerCase().includes(query) ||
                                    p.notes.top.toLowerCase().includes(query) ||
                                    p.notes.heart.toLowerCase().includes(query) ||
                                    p.notes.base.toLowerCase().includes(query);
                return matchCategory && matchSearch;
            });
            renderProducts(filtered);
        }

        // فتح نافذة تفاصيل العطر
        function openProductModal(id) {
            const perfume = perfumes.find(p => p.id === id);
            if (!perfume) return;

            const content = document.getElementById('modal-content');
            content.innerHTML = `
                <div class="h-64 md:h-full bg-velvet-950">
                    <img src="${perfume.image}" 
                         onerror="this.src='https://placehold.co/500x600/141218/d4af37?text=${encodeURIComponent(perfume.subtitle)}'"
                         alt="${perfume.name}" class="w-full h-full object-cover">
                </div>
                <div class="p-6 sm:p-8 flex flex-col justify-between space-y-6">
                    <div class="space-y-4">
                        <div>
                            <span class="text-xs text-gold-400 font-bold">${perfume.categoryLabel} • ${perfume.size}</span>
                            <h3 class="text-2xl font-serif font-bold text-white mt-1">${perfume.name}</h3>
                            <p class="text-xs text-gray-400 font-serif">${perfume.subtitle}</p>
                        </div>
                        <p class="text-gray-300 text-sm leading-relaxed">${perfume.description}</p>
                        
                        <!-- الهرم العطري -->
                        <div class="space-y-2.5 pt-2 border-t border-velvet-800">
                            <h4 class="text-xs font-bold text-gold-400">الهرم العطري:</h4>
                            <div class="text-xs text-gray-300"><strong class="text-white">افتتاحية العطر:</strong> ${perfume.notes.top}</div>
                            <div class="text-xs text-gray-300"><strong class="text-white">قلب العطر:</strong> ${perfume.notes.heart}</div>
                            <div class="text-xs text-gray-300"><strong class="text-white">قاعدة العطر:</strong> ${perfume.notes.base}</div>
                        </div>
                    </div>

                    <div class="flex items-center justify-between pt-4 border-t border-velvet-800">
                        <span class="text-2xl font-extrabold text-gold-400">${perfume.price} د.ل</span>
                        <button type="button" onclick="addToCart(${perfume.id}); closeProductModal();" class="px-6 py-3 rounded-xl bg-gold-500 text-velvet-950 font-bold text-sm hover:bg-gold-400 transition-colors">
                            أضف للسلة
                        </button>
                    </div>
                </div>
            `;
            document.getElementById('product-modal').classList.remove('hidden');
        }

        function closeProductModal() {
            document.getElementById('product-modal').classList.add('hidden');
        }

        // ترشيح عطر حسب ذوق المستخدم
        function recommendScent(type) {
            const matches = perfumes.filter(p => p.scentType === type);
            const chosen = matches.length > 0 ? matches[0] : perfumes[0];
            if (!chosen) return;

            const resultBox = document.getElementById('scent-result');
            resultBox.classList.remove('hidden');
            resultBox.innerHTML = `
                <div class="flex flex-col sm:flex-row items-center gap-4">
                    <img src="${chosen.image}" onerror="this.src='https://placehold.co/150x150/141218/d4af37?text=Velvet'" class="w-24 h-24 rounded-2xl object-cover border border-gold-500/40 shrink-0">
                    <div class="flex-1 text-center sm:text-right space-y-1">
                        <span class="text-xs text-gold-400 font-bold">الترشيح المثالي لك:</span>
                        <h4 class="text-xl font-bold text-white">${chosen.name} (${chosen.subtitle})</h4>
                        <p class="text-xs text-gray-300">${chosen.description}</p>
                    </div>
                    <button type="button" onclick="addToCart(${chosen.id})" class="px-5 py-3 rounded-xl bg-gold-500 text-velvet-950 font-bold text-sm hover:bg-gold-400 transition-colors shrink-0">
                        أضف للسلة (${chosen.price} د.ل)
                    </button>
                </div>
            `;
        }

        // حذف عطر من المتجر (للمالك فقط)
        function deletePerfume(id) {
            if (!isAdminAuthenticated) return;
            perfumes = perfumes.filter(p => p.id !== id);
            localStorage.setItem('velvet_perfumes', JSON.stringify(perfumes));
            renderProducts(perfumes);
            renderAdminPerfumesList();
            showToast("تم حذف العطر من المتجر.");
        }

        // عرض قائمة العطور داخل لوحة الإدارة لسهولة الحذف
        function renderAdminPerfumesList() {
            const listContainer = document.getElementById('admin-perfumes-list');
            const countBadge = document.getElementById('admin-perfumes-count');
            if (!listContainer || !countBadge) return;

            countBadge.textContent = `${perfumes.length} عطور`;

            if (perfumes.length === 0) {
                listContainer.innerHTML = `<p class="text-xs text-gray-500 text-center py-3">لا توجد عطور مضافة حالياً.</p>`;
                return;
            }

            listContainer.innerHTML = perfumes.map(p => `
                <div class="flex items-center justify-between p-2.5 rounded-xl bg-velvet-950/90 border border-velvet-800">
                    <div class="flex items-center gap-2.5">
                        <img src="${p.image}" onerror="this.src='https://placehold.co/40x40/141218/d4af37?text=V'" class="w-9 h-9 rounded-lg object-cover">
                        <div>
                            <div class="text-xs font-bold text-white">${p.name}</div>
                            <div class="text-[11px] text-gold-400">${p.price} د.ل • ${p.categoryLabel}</div>
                        </div>
                    </div>
                    <button type="button" onclick="deletePerfume(${p.id})" class="px-3 py-1.5 rounded-lg bg-red-600/20 hover:bg-red-600 text-red-400 hover:text-white text-xs font-bold transition-colors flex items-center gap-1">
                        <i class="fa-solid fa-trash-can"></i>
                        <span>مسح</span>
                    </button>
                </div>
            `).join('');
        }

        // دوال إدارة إضافة العطور (Admin Panel)
        function openAdminModal() {
            if (!isAdminAuthenticated) return requestAdminAccess();
            renderAdminPerfumesList();
            document.getElementById('admin-modal').classList.remove('hidden');
        }

        function closeAdminModal() {
            document.getElementById('admin-modal').classList.add('hidden');
        }

        function addNewPerfume(e) {
            e.preventDefault();
            if (!isAdminAuthenticated) return;

            const name = document.getElementById('new-name').value.trim();
            const subtitle = document.getElementById('new-subtitle').value.trim();
            const price = parseFloat(document.getElementById('new-price').value);
            const size = document.getElementById('new-size').value.trim();
            const category = document.getElementById('new-category').value;
            const imageInput = document.getElementById('new-image').value.trim();
            const notesInput = document.getElementById('new-notes').value.trim();
            const description = document.getElementById('new-desc').value.trim();

            const categoryLabels = {
                men: "رجالي",
                women: "نسائي",
                unisex: "للجنسين",
                oud: "عود وبخور"
            };

            const defaultImg = "https://images.unsplash.com/photo-1594035910387-fea47794261f?auto=format&fit=crop&w=600&q=80";

            const newPerfume = {
                id: Date.now(),
                name: name,
                subtitle: subtitle,
                category: category,
                categoryLabel: categoryLabels[category] || "حصري",
                scentType: category === 'oud' ? 'woody' : (category === 'women' ? 'floral' : 'fresh'),
                price: price,
                size: size,
                image: imageInput || defaultImg,
                notes: {
                    top: notesInput,
                    heart: "توليفة فيلفيت الخاصة",
                    base: "مسك وعنبر فاخر"
                },
                description: description
            };

            perfumes.unshift(newPerfume);
            localStorage.setItem('velvet_perfumes', JSON.stringify(perfumes));

            renderProducts(perfumes);
            renderAdminPerfumesList();
            e.target.reset();
            closeAdminModal();
            showToast(`تم نشر عطر "${name}" بسعر ${price} د.ل بنجاح!`);
        }

        // إدارة سلة التسوق
        function addToCart(id) {
            const perfume = perfumes.find(p => p.id === id);
            if (!perfume) return;

            const existingItem = cart.find(item => item.id === id);
            if (existingItem) {
                existingItem.qty += 1;
            } else {
                cart.push({ ...perfume, qty: 1 });
            }

            updateCartUI();
            showToast(`تمت إضافة "${perfume.name}" إلى السلة`);
        }

        function updateQty(id, delta) {
            const item = cart.find(i => i.id === id);
            if (!item) return;

            item.qty += delta;
            if (item.qty <= 0) {
                cart = cart.filter(i => i.id !== id);
            }
            updateCartUI();
        }

        function updateCartUI() {
            const badge = document.getElementById('cart-badge');
            const itemsContainer = document.getElementById('cart-items');
            const totalEl = document.getElementById('cart-total');
            const checkoutBtn = document.getElementById('checkout-btn');

            const totalQty = cart.reduce((sum, item) => sum + item.qty, 0);
            const totalPrice = cart.reduce((sum, item) => sum + (item.price * item.qty), 0);

            if (badge) badge.textContent = totalQty;
            if (totalEl) totalEl.textContent = `${totalPrice} د.ل`;
            if (checkoutBtn) checkoutBtn.disabled = cart.length === 0;

            if (!itemsContainer) return;

            if (cart.length === 0) {
                itemsContainer.innerHTML = `
                    <div class="text-center py-16 space-y-3 text-gray-400">
                        <i class="fa-solid fa-bag-shopping text-4xl text-velvet-700"></i>
                        <p class="text-sm">سلة التسوق فارغة حالياً</p>
                    </div>
                `;
                return;
            }

            itemsContainer.innerHTML = cart.map(item => `
                <div class="flex items-center gap-3 p-3 rounded-2xl bg-velvet-950/70 border border-velvet-800">
                    <img src="${item.image}" onerror="this.src='https://placehold.co/80x80/141218/d4af37?text=V'" class="w-16 h-16 rounded-xl object-cover shrink-0">
                    <div class="flex-1">
                        <h4 class="text-sm font-bold text-white">${item.name}</h4>
                        <span class="text-xs text-gold-400 font-semibold">${item.price} د.ل</span>
                    </div>
                    <div class="flex items-center gap-2 bg-velvet-800 rounded-xl p-1">
                        <button type="button" onclick="updateQty(${item.id}, -1)" class="w-7 h-7 rounded-lg hover:bg-velvet-700 text-gray-300 flex items-center justify-center text-xs">-</button>
                        <span class="text-xs font-bold w-4 text-center">${item.qty}</span>
                        <button type="button" onclick="updateQty(${item.id}, 1)" class="w-7 h-7 rounded-lg hover:bg-velvet-700 text-gray-300 flex items-center justify-center text-xs">+</button>
                    </div>
                </div>
            `).join('');
        }

        function toggleCart() {
            const drawer = document.getElementById('cart-drawer');
            drawer.classList.toggle('hidden');
        }

        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        // إتمام الطلب
        function checkout() {
            if (cart.length === 0) return;
            toggleCart();
            syncPaymentMethod(selectedPaymentMethod);
            document.getElementById('checkout-modal').classList.remove('hidden');
        }

        function closeCheckoutModal() {
            document.getElementById('checkout-modal').classList.add('hidden');
        }

        function submitOrder(e) {
            e.preventDefault();
            const paymentText = selectedPaymentMethod === 'transfer' ? 'عبر حوالة مصرفية' : 'كاش عند الاستلام';
            cart = [];
            updateCartUI();
            closeCheckoutModal();
            showToast(`تم استلام طلبك بنجاح (الدفع ${paymentText})! سنتواصل معك قريباً.`);
        }

        function subscribeNewsletter(e) {
            e.preventDefault();
            e.target.reset();
            showToast("شكراً لانضمامك لنادي VelvetParfums! كود الخصم: VELVET15");
        }

        // عرض الإشعارات المنبثقة
        function showToast(message) {
            const toast = document.getElementById('toast');
            const msgEl = document.getElementById('toast-msg');
            if (!toast || !msgEl) return;

            msgEl.textContent = message;
            toast.classList.remove('translate-y-24', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-24', 'opacity-0');
            }, 3500);
        }

        // تهيئة المتجر عند تحميل الصفحة
        window.addEventListener('DOMContentLoaded', () => {
            initVisitorStats();
            renderProducts(perfumes);
            updateCartUI();
        });
    </script>
</body>
</html>
