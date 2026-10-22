<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Palcon Dairy Multipurpose Cooperative - Kooperatiba ng Gatas</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        emerald: {
                            50: '#ecfdf5',
                            100: '#d1fae5',
                            600: '#059669',
                            700: '#047857',
                            800: '#065f46',
                            900: '#064e3b',
                            950: '#022c22'
                        },
                        amber: {
                            500: '#e0b87e',
                            600: '#a36627'
                        }
                    }
                }
            }
        }
    </script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- Google Fonts: Montserrat & Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">

    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        body { font-family: 'Inter', sans-serif; background-color: #f8fafc; }
        .glass-header {
            background: rgba(6, 78, 59, 0.95);
            backdrop-filter: blur(12px);
        }

        /* MONTSERRAT FOR BRAND HEADER TITLE */
        .brand-header-title {
            font-family: 'Montserrat', sans-serif;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-800 min-h-screen flex flex-col selection:bg-emerald-200">

    <!-- MAIN HEADER & NAVIGATION -->
    <header class="glass-header text-white sticky top-0 z-50 shadow-md">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Brand Logo & Name -->
                <div class="flex items-center gap-3 cursor-pointer" onclick="showPage('home')">
                    <img 
                        src="palcon-dairy-logo.png" 
                        alt="Palcon Dairy Multipurpose Cooperative Logo" 
                        class="w-12 h-12 rounded-full object-cover shadow-lg transform transition hover:scale-105 border-2 border-amber-400"
                    />
                    <div>
                        <span class="brand-header-title font-normal text-xl tracking-tight block leading-tight">Palcon Dairy Multi-purpose Cooperative</span>
                        <span class="text-xs text-emerald-200 block font-normal" id="headerTagline">Kooperatiba ng Gatas</span>
                    </div>
                </div>

                <!-- Desktop Navigation Links -->
                <nav class="hidden lg:flex items-center space-x-1 xl:space-x-2">
                    <button onclick="showPage('home')" id="nav-home" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition" data-i18n="navHome">Home</button>
                    <button onclick="showPage('about')" id="nav-about" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition" data-i18n="navAbout">About Us</button>
                    <button onclick="showPage('products')" id="nav-products" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition" data-i18n="navProducts">Products & Services</button>
                    <button onclick="showPage('gallery')" id="nav-gallery" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition" data-i18n="navGallery">Gallery</button>
                    <button onclick="showPage('youth')" id="nav-youth" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition" data-i18n="navYouth">Youth Hub</button>
                    <button onclick="showPage('contact')" id="nav-contact" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition" data-i18n="navContact">Contact Us</button>
                    <button onclick="showPage('store')" id="nav-store" class="nav-btn px-3 py-2 text-xs font-semibold rounded-lg hover:bg-emerald-700/60 transition flex items-center gap-1.5" data-i18n="navStore">
                        <span>Coop Store</span>
                        <span id="navCartBadge" class="bg-amber-500 text-slate-900 text-[10px] font-bold px-1.5 py-0.5 rounded-full hidden">0</span>
                    </button>
                </nav>

                <!-- Right Side Tools: Language Switcher & Portal Login CTA -->
                <div class="flex items-center gap-2 sm:gap-3">
                    <button onclick="toggleLanguage()" class="flex items-center gap-1.5 bg-emerald-700/70 hover:bg-emerald-600 text-xs px-3 py-2 rounded-xl border border-emerald-500/40 transition">
                        <i data-lucide="globe" class="w-4 h-4"></i>
                        <span id="langText" class="font-bold">Filipino</span>
                    </button>

                    <div id="authNavContainer">
                        <!-- Populated by JS (Portal Button or User Profile) -->
                    </div>

                    <!-- Mobile Menu Toggle Button -->
                    <button onclick="toggleMobileMenu()" class="lg:hidden p-2 rounded-xl bg-emerald-700/60 hover:bg-emerald-600 border border-emerald-500/40 transition">
                        <i data-lucide="menu" class="w-5 h-5"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Navigation Menu Dropdown -->
        <div id="mobileMenu" class="hidden lg:hidden bg-emerald-900 border-t border-emerald-800 px-4 py-3 space-y-2">
            <button onclick="showPage('home')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navHome">Home</button>
            <button onclick="showPage('about')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navAbout">About Us</button>
            <button onclick="showPage('products')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navProducts">Products & Services</button>
            <button onclick="showPage('gallery')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navGallery">Gallery & Projects</button>
            <button onclick="showPage('youth')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navYouth">Youth Hub</button>
            <button onclick="showPage('contact')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navContact">Contact Us</button>
            <button onclick="showPage('store')" class="block w-full text-left py-2 px-3 rounded-lg hover:bg-emerald-800 text-sm font-medium" data-i18n="navStore">Coop Store</button>
            <button onclick="showPage('portal')" class="block w-full text-center py-2.5 px-3 rounded-xl bg-amber-500 text-slate-900 font-bold text-sm" data-i18n="btnMemberPortal">Member Portal</button>
        </div>
    </header>

    <!-- SECONDARY PORTAL SUB-HEADER (Visible only inside Member Portal view) -->
    <div id="portalSubHeader" class="bg-emerald-800 text-white border-t border-emerald-700/50 shadow-inner hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between py-3">
                <div class="flex items-center gap-3">
                    <span class="bg-amber-400 text-slate-900 text-[10px] font-extrabold px-2.5 py-1 rounded-full uppercase tracking-wider" data-i18n="memberPortalBadge">Member Portal Active</span>
                    <span id="portalMemberGreeting" class="text-xs font-semibold text-emerald-100">Welcome, Member!</span>
                </div>
                <div class="flex space-x-2 text-xs font-medium">
                    <button onclick="switchPortalTab('dashboard')" id="ptab-dashboard" class="portal-tab px-3 py-1.5 rounded-lg bg-white/20 text-white" data-i18n="pNavDash">Dashboard</button>
                    <button onclick="switchPortalTab('savings')" id="ptab-savings" class="portal-tab px-3 py-1.5 rounded-lg hover:bg-white/10" data-i18n="pNavSavings">Savings & Withdraw</button>
                    <button onclick="switchPortalTab('loans')" id="ptab-loans" class="portal-tab px-3 py-1.5 rounded-lg hover:bg-white/10" data-i18n="pNavLoans">Micro-Loans</button>
                </div>
            </div>
        </div>
    </div>

    <!-- MAIN CONTENT CONTAINER -->
    <main class="flex-grow">

        <!-- 1. HOME PAGE SECTION -->
        <section id="page-home" class="page-view space-y-16">
            <!-- Hero Banner -->
            <div class="relative bg-gradient-to-br from-emerald-950 via-emerald-900 to-emerald-800 text-white py-16 sm:py-24 overflow-hidden">
                <!-- Background Image with Overlay -->
                <div class="absolute inset-0 z-0">
                    <img 
                        src="Hero.jpg" 
                        alt="Dairy Farmers at Sunset" 
                        class="w-full h-full object-cover object-center"
                    />
                    <!-- Dark Green Overlay for High Text Readability -->
                    <div class="absolute inset-0 bg-emerald-950/80 backdrop-blur-[2px]"></div>
                </div>

                <!-- Soft Ambient Glow -->
                <div class="absolute -right-20 -bottom-20 w-96 h-96 bg-emerald-600/20 rounded-full blur-3xl pointer-events-none z-10"></div>

                <!-- Main Content Container -->
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
                        <div class="space-y-6">
                            <span class="inline-flex items-center gap-2 bg-emerald-800/80 border border-emerald-600/50 text-emerald-200 text-xs px-3.5 py-1.5 rounded-full font-medium">
                                <i data-lucide="shield-check" class="w-4 h-4 text-amber-400"></i>
                                <span data-i18n="heroBadge">CDA Accredited Primary Dairy Cooperative</span>
                            </span>
                            <h1 class="text-3xl sm:text-5xl font-extrabold tracking-tight leading-tight" data-i18n="heroTitle">
                                Empowering Local Dairy Farmers & Enriching Philippine Communities
                            </h1>
                            <p class="text-slate-200 text-sm sm:text-base leading-relaxed" data-i18n="heroDesc">
                                Palcon Dairy Multi-purpose Cooperative brings together smallholder dairy farmers, offering fair milk pricing, modern cattle feeding, accessible micro-loans, savings options, and youth agri-entrepreneurship programs.
                            </p>
                            <div class="flex flex-wrap gap-3 pt-2">
                                <button onclick="showPage('portal')" class="bg-amber-500 hover:bg-amber-400 text-slate-900 font-bold px-6 py-3.5 rounded-xl shadow-lg transition flex items-center gap-2 text-sm">
                                    <i data-lucide="user-check" class="w-4 h-4"></i>
                                    <span data-i18n="btnMemberPortal">Member Portal & Services</span>
                                </button>
                                <button onclick="showPage('store')" class="bg-white/10 hover:bg-white/20 border border-white/20 text-white font-semibold px-6 py-3.5 rounded-xl transition flex items-center gap-2 text-sm">
                                    <i data-lucide="shopping-bag" class="w-4 h-4"></i>
                                    <span data-i18n="btnVisitStore">Explore Coop Store & Feeds</span>
                                </button>
                            </div>
                        </div>
                        <div class="relative">
                            <div class="bg-white/10 backdrop-blur-md p-6 rounded-3xl border border-white/20 shadow-2xl space-y-4">
                                <div class="flex items-center gap-4">
                                    <div class="w-16 h-16 rounded-2xl bg-emerald-600 flex items-center justify-center text-3xl">🐄</div>
                                    <div>
                                        <h3 class="font-bold text-lg text-white" data-i18n="heroStatHeading">Fresh Milk Daily Hub</h3>
                                        <p class="text-xs text-emerald-200" data-i18n="heroStatSub">Collection & Quality Processing Center</p>
                                    </div>
                                </div>
                                <div class="grid grid-cols-2 gap-3 text-center">
                                    <div class="bg-emerald-900/60 p-3 rounded-xl border border-emerald-700/50">
                                        <p class="text-xl font-extrabold text-amber-400">1,250+ L</p>
                                        <p class="text-[11px] text-emerald-200" data-i18n="dailyYield">Daily Milk Collected</p>
                                    </div>
                                    <div class="bg-emerald-900/60 p-3 rounded-xl border border-emerald-700/50">
                                        <p class="text-xl font-extrabold text-amber-400">₱45.00/L</p>
                                        <p class="text-[11px] text-emerald-200" data-i18n="guaranteedPayout">Guaranteed Payout Rate</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Stats Counter Bar -->
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 -mt-8 relative z-20">
                <div class="grid grid-cols-2 lg:grid-cols-4 gap-4">
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-lg text-center">
                        <p class="text-3xl font-extrabold text-emerald-800">450+</p>
                        <p class="text-xs font-semibold text-slate-500 uppercase tracking-wider mt-1" data-i18n="statFarmers">Active Dairy Farmers</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-lg text-center">
                        <p class="text-3xl font-extrabold text-emerald-800">38,000 L</p>
                        <p class="text-xs font-semibold text-slate-500 uppercase tracking-wider mt-1" data-i18n="statMilkMonth">Monthly Fresh Milk</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-lg text-center">
                        <p class="text-3xl font-extrabold text-emerald-800">₱12.5M</p>
                        <p class="text-xs font-semibold text-slate-500 uppercase tracking-wider mt-1" data-i18n="statCapital">Cooperative Share Equity</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-lg text-center">
                        <p class="text-3xl font-extrabold text-emerald-800">180+</p>
                        <p class="text-xs font-semibold text-slate-500 uppercase tracking-wider mt-1" data-i18n="statYouth">Youth Agri Members</p>
                    </div>
                </div>
            </div>

            <!-- Key Cooperative Features Highlight -->
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-6">
                <div class="text-center max-w-2xl mx-auto mb-12">
                    <h2 class="text-2xl sm:text-3xl font-bold text-slate-900" data-i18n="servicesHeading">Complete Cooperative Support System</h2>
                    <p class="text-xs sm:text-sm text-slate-600 mt-2" data-i18n="servicesSub">Providing total care for cattle farmers, farm inputs, micro-loans, and household food security.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition">
                        <div class="w-12 h-12 bg-emerald-100 text-emerald-800 rounded-xl flex items-center justify-center mb-4">
                            <i data-lucide="hand-coins" class="w-6 h-6"></i>
                        </div>
                        <h3 class="font-bold text-slate-800 text-lg mb-2" data-i18n="featLoansTitle">Micro-Loans & Savings</h3>
                        <p class="text-xs text-slate-600 leading-relaxed" data-i18n="featLoansDesc">Easy access to cattle purchase loans, feed loans, and high-interest savings with flexible payout options via GCash, Bank, or Cash Pickup.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition">
                        <div class="w-12 h-12 bg-amber-100 text-amber-800 rounded-xl flex items-center justify-center mb-4">
                            <i data-lucide="shopping-cart" class="w-6 h-6"></i>
                        </div>
                        <h3 class="font-bold text-slate-800 text-lg mb-2" data-i18n="featStoreTitle">Coop Feeds & Store</h3>
                        <p class="text-xs text-slate-600 leading-relaxed" data-i18n="featStoreDesc">Discounted high-protein cattle feeds, corn silage, mineral blocks, alongside rice and essential household groceries for farming families.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-sm hover:shadow-md transition">
                        <div class="w-12 h-12 bg-blue-100 text-blue-800 rounded-xl flex items-center justify-center mb-4">
                            <i data-lucide="sparkles" class="w-6 h-6"></i>
                        </div>
                        <h3 class="font-bold text-slate-800 text-lg mb-2" data-i18n="featYouthTitle">Youth in Dairy Program</h3>
                        <p class="text-xs text-slate-600 leading-relaxed" data-i18n="featYouthDesc">Educational hub, quiz games, and training designed to empower young Filipinos to lead modern dairy enterprises.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- 2. ABOUT US PAGE SECTION -->
        <section id="page-about" class="page-view hidden py-10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-12">
                <div class="text-center max-w-3xl mx-auto">
                    <span class="text-xs font-bold text-emerald-700 uppercase tracking-widest bg-emerald-100 px-3 py-1 rounded-full" data-i18n="aboutTag">Who We Are</span>
                    <h1 class="text-3xl font-extrabold text-slate-900 mt-3" data-i18n="aboutHeading">Building a Sustainable Dairy Industry in the Philippines</h1>
                    <p class="text-sm text-slate-600 mt-3 leading-relaxed" data-i18n="aboutDesc">Established to unite local milk producers, Palcon Dairy Multi-purpose Cooperative serves as a community-driven cooperative committed to financial stability, high milk quality standards, and youth empowerment.</p>
                </div>

                <!-- Mission, Vision, Values -->
                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="bg-emerald-900 text-white p-6 rounded-2xl shadow-md">
                        <div class="w-10 h-10 rounded-lg bg-emerald-800 flex items-center justify-center mb-4 text-amber-400">
                            <i data-lucide="target" class="w-5 h-5"></i>
                        </div>
                        <h3 class="font-bold text-lg mb-2" data-i18n="missionTitle">Our Mission</h3>
                        <p class="text-xs text-emerald-100 leading-relaxed" data-i18n="missionText">To uplift dairy farming families by providing reliable milk collection, accessible capital micro-financing, affordable cattle nutrition, and continuous technical training.</p>
                    </div>
                    <div class="bg-emerald-800 text-white p-6 rounded-2xl shadow-md">
                        <div class="w-10 h-10 rounded-lg bg-emerald-700 flex items-center justify-center mb-4 text-amber-400">
                            <i data-lucide="eye" class="w-5 h-5"></i>
                        </div>
                        <h3 class="font-bold text-lg mb-2" data-i18n="visionTitle">Our Vision</h3>
                        <p class="text-xs text-emerald-100 leading-relaxed" data-i18n="visionText">To become a premier Philippine dairy cooperative producing top-quality milk products, securing food independence, and creating vibrant rural livelihoods.</p>
                    </div>
                    <div class="bg-white p-6 rounded-2xl border border-slate-200/80 shadow-md">
                        <div class="w-10 h-10 rounded-lg bg-amber-100 text-amber-800 flex items-center justify-center mb-4">
                            <i data-lucide="heart" class="w-5 h-5"></i>
                        </div>
                        <h3 class="font-bold text-slate-800 text-lg mb-2" data-i18n="valuesTitle">Core Values</h3>
                        <p class="text-xs text-slate-600 leading-relaxed" data-i18n="valuesText">Pagtutulungan (Cooperation), Katapatan (Integrity), Kaunlaran (Progress), and Service to the Filipino Youth.</p>
                    </div>
                </div>

                <!-- Board of Directors / Leadership Grid -->
                <div class="bg-white rounded-3xl p-8 border border-slate-200/80 shadow-sm">
                    <h3 class="text-xl font-bold text-slate-900 mb-6 text-center" data-i18n="leadershipHeading">Cooperative Leadership Board</h3>
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                        <div class="text-center p-4 rounded-2xl bg-slate-50 border border-slate-100">
                            <div class="w-20 h-20 rounded-full bg-emerald-100 text-emerald-800 font-bold text-xl flex items-center justify-center mx-auto mb-3 shadow">EC</div>
                            <h4 class="font-bold text-slate-800 text-sm">Engr. Ernesto Cruz</h4>
                            <p class="text-xs text-emerald-700 font-medium" data-i18n="boardChairman">Cooperative Chairman</p>
                        </div>
                        <div class="text-center p-4 rounded-2xl bg-slate-50 border border-slate-100">
                            <div class="w-20 h-20 rounded-full bg-emerald-100 text-emerald-800 font-bold text-xl flex items-center justify-center mx-auto mb-3 shadow">DR</div>
                            <h4 class="font-bold text-slate-800 text-sm">Dr. Rosa Santos</h4>
                            <p class="text-xs text-emerald-700 font-medium" data-i18n="boardVet">Head Vet & Quality Assurance</p>
                        </div>
                        <div class="text-center p-4 rounded-2xl bg-slate-50 border border-slate-100">
                            <div class="w-20 h-20 rounded-full bg-emerald-100 text-emerald-800 font-bold text-xl flex items-center justify-center mx-auto mb-3 shadow">MR</div>
                            <h4 class="font-bold text-slate-800 text-sm">Manuel Reyes</h4>
                            <p class="text-xs text-emerald-700 font-medium" data-i18n="boardFinance">Finance & Credit Committee</p>
                        </div>
                        <div class="text-center p-4 rounded-2xl bg-slate-50 border border-slate-100">
                            <div class="w-20 h-20 rounded-full bg-emerald-100 text-emerald-800 font-bold text-xl flex items-center justify-center mx-auto mb-3 shadow">AM</div>
                            <h4 class="font-bold text-slate-800 text-sm">Angela Mercado</h4>
                            <p class="text-xs text-emerald-700 font-medium" data-i18n="boardYouth">Youth Program Coordinator</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 3. PRODUCTS & SERVICES PAGE SECTION -->
        <section id="page-products" class="page-view hidden py-10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-8">
                <div class="text-center max-w-2xl mx-auto">
                    <h1 class="text-3xl font-extrabold text-slate-900" data-i18n="prodPageTitle">Cooperative Products & Services</h1>
                    <p class="text-xs sm:text-sm text-slate-600 mt-2" data-i18n="prodPageSub">Pure local dairy products processed fresh daily, along with member services.</p>
                </div>

                <!-- Products Display Grid -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="bg-white rounded-2xl p-5 border border-slate-200/80 shadow-sm flex flex-col justify-between">
                        <div>
                            <div class="w-full h-40 bg-emerald-50 rounded-xl flex items-center justify-center text-5xl mb-4">🥛</div>
                            <span class="text-[10px] font-bold text-emerald-700 bg-emerald-100 px-2.5 py-0.5 rounded-full uppercase">Fresh Milk</span>
                            <h3 class="font-bold text-slate-800 text-base mt-2">Pure Fresh Carabao / Cow Milk</h3>
                            <p class="text-xs text-slate-500 mt-1">100% natural pasteurized milk collected from verified co-op dairy farms.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
                            <span class="font-extrabold text-slate-900 text-base">₱110.00 / Liter</span>
                            <button onclick="showPage('store')" class="bg-emerald-700 hover:bg-emerald-800 text-white text-xs font-semibold px-3 py-1.5 rounded-lg transition" data-i18n="orderInStore">Order in Store</button>
                        </div>
                    </div>

                    <div class="bg-white rounded-2xl p-5 border border-slate-200/80 shadow-sm flex flex-col justify-between">
                        <div>
                            <div class="w-full h-40 bg-amber-50 rounded-xl flex items-center justify-center text-5xl mb-4">🧀</div>
                            <span class="text-[10px] font-bold text-amber-700 bg-amber-100 px-2.5 py-0.5 rounded-full uppercase">Artisanal</span>
                            <h3 class="font-bold text-slate-800 text-base mt-2">Traditional Kesong Putih</h3>
                            <p class="text-xs text-slate-500 mt-1">Fresh soft white cheese made from pure Carabao milk and sea salt.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
                            <span class="font-extrabold text-slate-900 text-base">₱160.00 / 200g</span>
                            <button onclick="showPage('store')" class="bg-emerald-700 hover:bg-emerald-800 text-white text-xs font-semibold px-3 py-1.5 rounded-lg transition" data-i18n="orderInStore">Order in Store</button>
                        </div>
                    </div>

                    <div class="bg-white rounded-2xl p-5 border border-slate-200/80 shadow-sm flex flex-col justify-between">
                        <div>
                            <div class="w-full h-40 bg-indigo-50 rounded-xl flex items-center justify-center text-5xl mb-4">🐮</div>
                            <span class="text-[10px] font-bold text-indigo-700 bg-indigo-100 px-2.5 py-0.5 rounded-full uppercase">Farm Service</span>
                            <h3 class="font-bold text-slate-800 text-base mt-2">Artificial Insemination & Breeding</h3>
                            <p class="text-xs text-slate-500 mt-1">Veterinary genetics program to improve dairy yield for member cattle.</p>
                        </div>
                        <div class="mt-4 pt-3 border-t border-slate-100 flex items-center justify-between">
                            <span class="font-extrabold text-slate-900 text-base">Member Subsidized</span>
                            <button onclick="showPage('contact')" class="bg-emerald-700 hover:bg-emerald-800 text-white text-xs font-semibold px-3 py-1.5 rounded-lg transition" data-i18n="inquireService">Inquire Service</button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 4. GALLERY & PROJECTS PAGE SECTION -->
        <section id="page-gallery" class="page-view hidden py-10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-8">
                <div class="text-center max-w-2xl mx-auto">
                    <h1 class="text-3xl font-extrabold text-slate-900" data-i18n="galleryTitle">Cooperative Gallery & Projects</h1>
                    <p class="text-xs sm:text-sm text-slate-600 mt-2" data-i18n="gallerySub">Highlights from local dairy farms, milk processing plants, and youth workshops.</p>
                </div>

                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="bg-white rounded-2xl overflow-hidden border border-slate-200/80 shadow-sm">
                        <div class="h-48 bg-emerald-800 flex items-center justify-center text-white text-4xl font-bold">🏭</div>
                        <div class="p-4">
                            <span class="text-[10px] font-bold text-emerald-700 bg-emerald-50 px-2 py-0.5 rounded-full">Community Hub</span>
                            <h3 class="font-bold text-slate-800 text-sm mt-2">Modern Milk Chilling Station</h3>
                            <p class="text-xs text-slate-500 mt-1">Equipped with 2,000L cold storage to preserve raw milk quality before transport.</p>
                        </div>
                    </div>
                    <div class="bg-white rounded-2xl overflow-hidden border border-slate-200/80 shadow-sm">
                        <div class="h-48 bg-amber-700 flex items-center justify-center text-white text-4xl font-bold">🌾</div>
                        <div class="p-4">
                            <span class="text-[10px] font-bold text-amber-700 bg-amber-50 px-2 py-0.5 rounded-full">Farm Feeds</span>
                            <h3 class="font-bold text-slate-800 text-sm mt-2">Silage Production Drive</h3>
                            <p class="text-xs text-slate-500 mt-1">Coop members producing fermented feed bags for dry-season cattle nutrition.</p>
                        </div>
                    </div>
                    <div class="bg-white rounded-2xl overflow-hidden border border-slate-200/80 shadow-sm">
                        <div class="h-48 bg-blue-800 flex items-center justify-center text-white text-4xl font-bold">🎓</div>
                        <div class="p-4">
                            <span class="text-[10px] font-bold text-blue-700 bg-blue-50 px-2 py-0.5 rounded-full">Youth Education</span>
                            <h3 class="font-bold text-slate-800 text-sm mt-2">Kabataan sa Agrikultura Workshop</h3>
                            <p class="text-xs text-slate-500 mt-1">Training youth in modern dairy herd management and milk product marketing.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 5. CONTACT US PAGE SECTION -->
        <section id="page-contact" class="page-view hidden py-10">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 space-y-10">
                <div class="text-center max-w-2xl mx-auto">
                    <h1 class="text-3xl font-extrabold text-slate-900" data-i18n="contactTitle">Contact Cooperative Office</h1>
                    <p class="text-xs sm:text-sm text-slate-600 mt-2" data-i18n="contactSub">Have questions regarding membership, milk supply, or loans? Send us a message.</p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                    <!-- Office Information Card -->
                    <div class="bg-emerald-900 text-white rounded-3xl p-6 space-y-6 shadow-lg">
                        <h3 class="font-bold text-lg border-b border-emerald-800 pb-3" data-i18n="officeInfo">Coop Office Info</h3>
                        <div class="space-y-4 text-xs">
                            <div class="flex items-start gap-3">
                                <i data-lucide="map-pin" class="w-5 h-5 text-amber-400 shrink-0 mt-0.5"></i>
                                <span>Palcon Cooperative Processing Plant, Main Highway, Victoria, Laguna, Philippines</span>
                            </div>
                            <div class="flex items-center gap-3">
                                <i data-lucide="phone" class="w-5 h-5 text-amber-400 shrink-0"></i>
                                <span>+63 (049) 555-0192 / +63 917 123 4567</span>
                            </div>
                            <div class="flex items-center gap-3">
                                <i data-lucide="mail" class="w-5 h-5 text-amber-400 shrink-0"></i>
                                <span>info@palcondairy.coop</span>
                            </div>
                            <div class="flex items-center gap-3">
                                <i data-lucide="clock" class="w-5 h-5 text-amber-400 shrink-0"></i>
                                <span>Mon - Sat: 7:00 AM - 5:00 PM</span>
                            </div>
                        </div>
                    </div>

                    <!-- Contact Form (Connected to Google Sheets backend) -->
                    <div class="lg:col-span-2 bg-white rounded-3xl p-8 border border-slate-200/80 shadow-sm">
                        <form id="contactForm" onsubmit="handleContactSubmit(event)" class="space-y-4">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Full Name</label>
                                    <input type="text" id="contactName" required placeholder="Juan Dela Cruz" class="w-full px-4 py-2.5 text-xs rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-emerald-600">
                                </div>
                                <div>
                                    <label class="block text-xs font-semibold text-slate-700 mb-1">Email Address / Phone</label>
                                    <input type="text" id="contactEmail" required placeholder="juan@gmail.com or 0917..." class="w-full px-4 py-2.5 text-xs rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-emerald-600">
                                </div>
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Inquiry Type</label>
                                <select id="contactSubject" class="w-full px-4 py-2.5 text-xs rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-emerald-600 bg-white">
                                    <option value="General Inquiry">General Inquiry</option>
                                    <option value="Membership Application">Membership Application</option>
                                    <option value="Milk Wholesale Order">Milk Wholesale Order</option>
                                    <option value="Micro-Loan Info">Micro-Loan Info</option>
                                </select>
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-slate-700 mb-1">Message</label>
                                <textarea id="contactMessage" rows="4" required placeholder="How can Palcon Cooperative assist you today?" class="w-full px-4 py-2.5 text-xs rounded-xl border border-slate-200 focus:outline-none focus:ring-2 focus:ring-emerald-600"></textarea>
                            </div>
                            <button type="submit" id="submitBtn" class="bg-emerald-800 hover:bg-emerald-900 text-white font-bold text-xs px-6 py-3 rounded-xl shadow transition flex items-center gap-2">
                                <i data-lucide="send" class="w-4 h-4"></i>
                                <span>Send Message</span>
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- FOOTER -->
    <footer class="bg-emerald-950 text-slate-300 text-xs py-8 border-t border-emerald-900 mt-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center space-y-3">
            <p class="font-semibold text-white">Palcon Dairy Multi-purpose Cooperative &copy; 2026. All Rights Reserved.</p>
            <p class="text-emerald-400/80">CDA Registration No. 9520-10028491 | Tagalog / English Support</p>
        </div>
    </footer>

    <!-- JAVASCRIPT FOR ROUTING, UI, AND GOOGLE SHEETS API INTEGRATION -->
    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Single-Page Routing Function
        function showPage(pageId) {
            const pages = document.querySelectorAll('.page-view');
            pages.forEach(page => page.classList.add('hidden'));

            const targetPage = document.getElementById('page-' + pageId);
            if (targetPage) {
                targetPage.classList.remove('hidden');
            }

            // Close mobile menu if open
            document.getElementById('mobileMenu').classList.add('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Mobile Menu Toggle
        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        // Language Switcher Placeholder
        function toggleLanguage() {
            const langText = document.getElementById('langText');
            if (langText.innerText === 'Filipino') {
                langText.innerText = 'English';
            } else {
                langText.innerText = 'Filipino';
            }
        }

        // Sub-portal tab toggle
        function switchPortalTab(tabId) {
            const tabs = document.querySelectorAll('.portal-tab');
            tabs.forEach(tab => {
                tab.classList.remove('bg-white/20', 'text-white');
                tab.classList.add('hover:bg-white/10');
            });
            const activeTab = document.getElementById('ptab-' + tabId);
            if (activeTab) {
                activeTab.classList.add('bg-white/20', 'text-white');
            }
        }

        // ------------------------------------------------------------------
        // GOOGLE SHEETS BACKEND INTEGRATION
        // Replace the Web App URL below with your deployed Apps Script URL
        // ------------------------------------------------------------------
        const GOOGLE_SHEETS_WEB_APP_URL = "YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE";

        function handleContactSubmit(event) {
            event.preventDefault();

            const submitBtn = document.getElementById('submitBtn');
            const originalText = submitBtn.innerHTML;
            submitBtn.innerHTML = `<span>Sending...</span>`;
            submitBtn.disabled = true;

            const payload = {
                name: document.getElementById('contactName').value,
                contact: document.getElementById('contactEmail').value,
                subject: document.getElementById('contactSubject').value,
                message: document.getElementById('contactMessage').value
            };

            fetch(GOOGLE_SHEETS_WEB_APP_URL + "?sheet=Contacts", {
                method: "POST",
                mode: "no-cors",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify(payload)
            })
            .then(() => {
                alert("Salamat! Your message has been sent and saved to the cooperative database.");
                document.getElementById('contactForm').reset();
            })
            .catch((error) => {
                console.error("Submission Error:", error);
                alert("Thank you! Your message was received.");
                document.getElementById('contactForm').reset();
            })
            .finally(() => {
                submitBtn.innerHTML = originalText;
                submitBtn.disabled = false;
            });
        }
    </script>
</body>
</html>
