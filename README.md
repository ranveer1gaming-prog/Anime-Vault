# 🛒 **Otaku Haven** - Complete Anime E-commerce Website (Single HTML File)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Otaku Haven - Premium Anime Merch Store</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/@lottiefiles/lottie-player@latest/dist/lottie-player.js"></script>
    <style>
        :root {
            --purple: #8b5cf6;
            --pink: #ec4899;
            --blue: #3b82f6;
            --neon-glow: 0 0 20px rgba(139, 92, 246, 0.5);
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #0f0f23 0%, #1a0033 50%, #0f0f23 100%);
            color: white;
            overflow-x: hidden;
        }
        
        .gradient-text {
            background: linear-gradient(45deg, #8b5cf6, #ec4899, #3b82f6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .glass {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .neon-glow {
            box-shadow: 0 0 20px rgba(139, 92, 246, 0.5), 0 0 40px rgba(236, 72, 153, 0.3);
        }
        
        .btn-primary {
            background: linear-gradient(45deg, #8b5cf6, #ec4899);
            transition: all 0.3s ease;
        }
        
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(139, 92, 246, 0.4);
        }
        
        .product-card {
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        
        .product-card:hover {
            transform: translateY(-15px) scale(1.02);
        }
        
        .orbitron {
            font-family: 'Orbitron', monospace;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .float {
            animation: float 3s ease-in-out infinite;
        }
        
        .loading-screen {
            background: linear-gradient(45deg, #0f0f23, #1a0033, #2a0a4a);
        }
    </style>
</head>
<body class="relative">
    <!-- Loading Screen -->
    <div id="loadingScreen" class="loading-screen fixed inset-0 z-50 flex items-center justify-center">
        <div class="text-center">
            <lottie-player 
                src="https://assets4.lottiefiles.com/packages/lf20_yf3k.json" 
                background="transparent" 
                speed="1" 
                style="width: 200px; height: 200px;" 
                loop 
                autoplay>
            </lottie-player>
            <h1 class="text-3xl font-bold gradient-text orbitron mt-8">Otaku Haven</h1>
            <p class="text-white/60 mt-2">Loading your anime paradise...</p>
        </div>
    </div>

    <!-- Floating Anime Particles -->
    <div class="fixed inset-0 pointer-events-none z-0">
        <div class="absolute top-20 left-10 w-20 h-20 bg-purple-500/20 rounded-full blur-xl animate-pulse"></div>
        <div class="absolute top-40 right-20 w-32 h-32 bg-pink-500/20 rounded-full blur-xl animation-delay-1000"></div>
        <div class="absolute bottom-32 left-1/4 w-24 h-24 bg-blue-500/20 rounded-full blur-xl animation-delay-2000"></div>
        <div class="absolute bottom-20 right-1/4 w-40 h-40 bg-purple-500/10 rounded-full blur-3xl float"></div>
    </div>

    <!-- Navigation -->
    <nav id="navbar" class="fixed top-0 w-full z-40 glass px-6 py-4 transition-all duration-500">
        <div class="max-w-7xl mx-auto flex items-center justify-between">
            <!-- Logo -->
            <div class="flex items-center space-x-3">
                <div class="w-12 h-12 bg-gradient-to-br from-purple-500 to-pink-500 rounded-2xl neon-glow flex items-center justify-center">
                    <i class="fas fa-dragon text-white text-xl"></i>
                </div>
                <div>
                    <h1 class="text-2xl font-black gradient-text orbitron">Otaku Haven</h1>
                    <p class="text-xs text-purple-300">Anime Paradise</p>
                </div>
            </div>

            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center space-x-8">
                <a href="#home" class="text-lg font-medium text-white/80 hover:text-purple-400 transition-all duration-300 relative group">
                    Home
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-to-r from-purple-400 to-pink-400 group-hover:w-full transition-all duration-300"></span>
                </a>
                <a href="#shop" class="text-lg font-medium text-white/80 hover:text-purple-400 transition-all duration-300 relative group">
                    Shop
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-to-r from-purple-400 to-pink-400 group-hover:w-full transition-all duration-300"></span>
                </a>
                <a href="#categories" class="text-lg font-medium text-white/80 hover:text-purple-400 transition-all duration-300 relative group">
                    Categories
                    <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-to-r from-purple-400 to-pink-400 group-hover:w-full transition-all duration-300"></span>
                </a>
            </div>

            <!-- Search -->
            <div class="hidden lg:flex flex-1 max-w-md mx-12">
                <div class="relative w-full">
                    <i class="fas fa-search absolute left-4 top-1/2 -translate-y-1/2 text-purple-400"></i>
                    <input 
                        type="text" 
                        id="searchInput"
                        placeholder="Search anime merch..." 
                        class="w-full pl-12 pr-6 py-3 bg-white/10 glass rounded-2xl text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-purple-500/50 transition-all duration-300"
                    >
                </div>
            </div>

            <!-- Icons -->
            <div class="flex items-center space-x-4">
                <!-- Wishlist -->
                <div class="relative group">
                    <button id="wishlistBtn" class="p-3 rounded-2xl bg-white/10 hover:bg-white/20 transition-all duration-300">
                        <i class="fas fa-heart text-pink-400 text-xl group-hover:scale-110 transition-transform"></i>
                    </button>
                    <span id="wishlistCount" class="absolute -top-1 -right-1 bg-pink-500 text-white text-xs rounded-full w-6 h-6 flex items-center justify-center text-sm font-bold hidden">0</span>
                </div>

                <!-- Cart -->
                <div class="relative group">
                    <button id="cartBtn" class="p-3 rounded-2xl bg-white/10 hover:bg-white/20 transition-all duration-300">
                        <i class="fas fa-shopping-cart text-blue-400 text-xl group-hover:scale-110 transition-transform"></i>
                    </button>
                    <span id="cartCount" class="absolute -top-1 -right-1 bg-gradient-to-r from-purple-500 to-pink-500 text-white text-xs rounded-full w-6 h-6 flex items-center justify-center text-sm font-bold">0</span>
                </div>

                <!-- Account -->
                <div class="relative group">
                    <button id="accountBtn" class="p-3 rounded-2xl bg-white/10 hover:bg-white/20 transition-all duration-300">
                        <i class="fas fa-user text-white text-xl group-hover:scale-110 transition-transform"></i>
                    </button>
                </div>

                <!-- Mobile Menu -->
                <button id="mobileMenuBtn" class="md:hidden p-3 rounded-2xl bg-white/10 hover:bg-white/20">
                    <i class="fas fa-bars text-xl"></i>
                </button>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobileMenu" class="md:hidden hidden pb-6 pt-4">
            <a href="#home" class="block py-3 px-6 text-lg font-medium hover:bg-white/10 rounded-xl mx-6">Home</a>
            <a href="#shop" class="block py-3 px-6 text-lg font-medium hover:bg-white/10 rounded-xl mx-6">Shop</a>
            <a href="#categories" class="block py-3 px-6 text-lg font-medium hover:bg-white/10 rounded-xl mx-6">Categories</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative pt-28 pb-32 overflow-hidden">
        <div class="absolute inset-0 bg-gradient-to-br from-purple-900/40 to-blue-900/40"></div>
        <div class="relative max-w-7xl mx-auto px-6 lg:px-8">
            <div class="grid lg:grid-cols-2 gap-12 items-center">
                <div class="lg:pr-16">
                    <div class="float">
                        <h1 class="text-5xl md:text-7xl lg:text-8xl font-black orbitron mb-8 leading-tight">
                            <span class="block gradient-text">Otaku</span>
                            <span class="block text-white">Haven</span>
                        </h1>
                        <p class="text-xl md:text-2xl text-white/80 mb-12 max-w-lg leading-relaxed">
                            Premium anime merchandise paradise. 
                            <span class="gradient-text font-semibold">T-Shirts, Figures, Hoodies & More!</span>
                        </p>
                        <div class="flex flex-col sm:flex-row gap-4">
                            <a href="#shop" class="btn-primary text-xl font-bold px-12 py-6 rounded-2xl text-white neon-glow text-center">
                                Shop Now
                            </a>
                            <a href="#categories" class="border-2 border-white/30 text-xl font-bold px-12 py-6 rounded-2xl hover:bg-white/10 transition-all duration-300">
                                View Categories
                            </a>
                        </div>
                    </div>
                </div>
                <div class="relative">
                    <div class="relative z-10">
                        <img src="https://images.unsplash.com/photo-1608043152266-1191e91a5ccf?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" 
                             alt="Anime Hero" 
                             class="w-full h-96 lg:h-[500px] object-cover rounded-3xl shadow-2xl neon-glow">
                        <div class="absolute -bottom-6 -right-6 w-48 h-48 bg-gradient-to-br from-purple-500/30 to-pink-500/30 rounded-3xl blur-xl"></div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="py-24 bg-white/5">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="grid md:grid-cols-4 gap-8 text-center">
                <div>
                    <div class="text-4xl font-black gradient-text orbitron mb-2">10K+</div>
                    <div class="text-white/80">Happy Otakus</div>
                </div>
                <div>
                    <div class="text-4xl font-black gradient-text orbitron mb-2">500+</div>
                    <div class="text-white/80">Products</div>
                </div>
                <div>
                    <div class="text-4xl font-black gradient-text orbitron mb-2">4.9</div>
                    <div class="text-white/80 flex items-center justify-center gap-1">
                        <i class="fas fa-star text-yellow-400"></i>
                        Rating
                    </div>
                </div>
                <div>
                    <div class="text-4xl font-black gradient-text orbitron mb-2">24/7</div>
                    <div class="text-white/80">Support</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Products -->
    <section id="featured" class="py-24">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="text-center mb-20">
                <h2 class="text-4xl md:text-5xl font-black orbitron mb-6">Featured Collection</h2>
                <p class="text-xl text-white/80 max-w-2xl mx-auto">Our top picks that every true otaku needs in their collection</p>
            </div>
            <div id="featuredProducts" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Products will be loaded here -->
            </div>
        </div>
    </section>

    <!-- Categories -->
    <section id="categories" class="py-24 bg-white/5">
        <div class="max-w-7xl mx-auto px-6 lg:px-8">
            <div class="text-center mb-20">
                <h2 class="text-4xl md:text-5xl font-black orbitron mb-6 gradient-text">Anime Categories</h2>
                <p class="text-xl text-white/80">Find your favorite anime universe</p>
            </div>
            <div class="grid md:grid-cols-3 lg:grid-cols-5 gap-6">
                <a href="#" class="group relative overflow-hidden rounded-3xl h-64 bg-gradient-to-br from-purple-500/20 to-pink-500/20 glass hover:from-purple-500/40 hover:to-pink-500/40 transition-all duration-500">
                    <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1578662996442-48f60103fc96?w=400')] bg-cover opacity-70 group-hover:opacity-90 transition-opacity"></div>
                    <div class="relative p-8 h-full flex flex-col justify-end">
                        <h3 class="text-2xl font-bold mb-2">Naruto</h3>
                        <div class="flex items-center gap-2 text-sm opacity-90">
                            <i class="fas fa-fire"></i>
                            <span>45 Products</span>
                        </div>
                    </div>
                </a>
                <a href="#" class="group relative overflow-hidden rounded-3xl h-64 bg-gradient-to-br from-pink-500/20 to-blue-500/20 glass hover:from-pink-500/40 hover:to-blue-500/40 transition-all duration-500">
                    <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1645559150867-415e6690b93f?w=400')] bg-cover opacity-70 group-hover:opacity-90"></div>
                    <div class="relative p-8 h-full flex flex-col justify-end">
                        <h3 class="text-2xl font-bold mb-2">Jujutsu Kaisen</h3>
                        <div class="flex items-center gap-2 text-sm opacity-90">
                            <i class="fas fa-skull"></i>
                            <span>38 Products</span>
                        </div>
                    </div>
                </a>
                <a href="#" class="group relative overflow-hidden rounded-3xl h-64 bg-gradient-to-br from-blue-500/20 to-purple-500/20 glass hover:from-blue-500/40 hover:to-purple-500/40 transition-all duration-500">
                    <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1590342441461-65d41c7d8205?w=400')] bg-cover opacity-70 group-hover:opacity-90"></div>
                    <div class="relative p-8 h-full flex flex-col justify-end">
                        <h3 class="text-2xl font-bold mb-2">Attack on Titan</h3>
                        <div class="flex items-center gap-2 text-sm opacity-90">
                            <i class="fas fa-shield-alt"></i>
                            <span>29 Products</span>
                        </div>
                    </div>
                </a>
                <a href="#" class="group relative overflow-hidden rounded-3xl h-64 bg-gradient-to-br from-orange-500/20 to-red-500/20 glass hover:from-orange-500/40 hover:to-red-500/40 transition-all duration-500">
                    <div class="absolute inset-0 bg-[url('https://images.unsplash.com/photo-1605818421588-20647e5cf18d?w=400')] bg-cover opacity-70 group-hover:opacity-90"></div>
                    <div class="relative p-8 h-full flex flex-col justify-end">
                        <h3 class="text-2xl font-bold mb-2">Demon Slayer
