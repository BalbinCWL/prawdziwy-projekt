<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Atelier Élégance - Elegancja w każdym detalu</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F5F5F3;
            color: #1A1A1A;
        }
        .font-cormorant {
            font-family: 'Cormorant Garamond', serif;
        }
        .product-card:hover .secondary-image {
            opacity: 1;
        }
        .secondary-image {
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .accordion-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        .accordion.active .accordion-content {
            max-height: 500px;
        }
        .accordion.active .accordion-icon {
            transform: rotate(180deg);
        }
        .accordion-icon {
            transition: transform 0.3s ease;
        }
        .menu-mobile {
            transform: translateX(100%);
            transition: transform 0.3s ease-out;
        }
        .menu-mobile.open {
            transform: translateX(0);
        }
    </style>
</head>
<body class="antialiased">
    <!-- Header -->
    <header class="fixed w-full bg-white z-50 shadow-sm">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <a href="#" class="text-2xl font-cormorant font-bold tracking-wider">ATELIER ÉLÉGANCE</a>
            
            <!-- Desktop Navigation -->
            <nav class="hidden md:flex space-x-8">
                <a href="#" class="hover:text-gray-600 transition">Strona główna</a>
                <a href="#" class="hover:text-gray-600 transition">Sklep</a>
                <a href="#" class="hover:text-gray-600 transition">Lookbook</a>
                <a href="#" class="hover:text-gray-600 transition">O nas</a>
                <a href="#" class="hover:text-gray-600 transition">Kontakt</a>
            </nav>
            
            <div class="flex items-center space-x-4">
                <div class="hidden md:block relative group">
                    <button class="flex items-center space-x-1">
                        <span class="text-sm">PL</span>
                        <i class="fas fa-chevron-down text-xs"></i>
                    </button>
                    <div class="absolute right-0 mt-2 w-20 bg-white shadow-md opacity-0 invisible group-hover:opacity-100 group-hover:visible transition-all duration-200">
                        <a href="#" class="block px-4 py-2 text-sm hover:bg-gray-100">EN</a>
                        <a href="#" class="block px-4 py-2 text-sm hover:bg-gray-100">ES</a>
                    </div>
                </div>
                
                <div class="flex items-center space-x-4">
                    <a href="#" class="hover:text-gray-600 transition"><i class="far fa-user"></i></a>
                    <a href="#" class="hover:text-gray-600 transition"><i class="far fa-heart"></i></a>
                    <a href="#" class="hover:text-gray-600 transition relative">
                        <i class="fas fa-shopping-bag"></i>
                        <span class="absolute -top-2 -right-2 bg-black text-white text-xs rounded-full w-5 h-5 flex items-center justify-center">0</span>
                    </a>
                    <button id="mobile-menu-button" class="md:hidden">
                        <i class="fas fa-bars"></i>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Mobile Menu -->
    <div id="mobile-menu" class="menu-mobile fixed inset-0 bg-white z-50 pt-20 px-6 overflow-y-auto">
        <div class="flex flex-col space-y-6 text-lg">
            <a href="#" class="border-b border-gray-100 pb-2">Strona główna</a>
            <a href="#" class="border-b border-gray-100 pb-2">Sklep</a>
            <a href="#" class="border-b border-gray-100 pb-2">Lookbook</a>
            <a href="#" class="border-b border-gray-100 pb-2">O nas</a>
            <a href="#" class="border-b border-gray-100 pb-2">Kontakt</a>
            
            <div class="flex items-center space-x-4 pt-4">
                <span class="font-medium">PL</span>
                <span class="text-gray-500">EN</span>
                <span class="text-gray-500">ES</span>
            </div>
        </div>
        <button id="close-menu" class="absolute top-6 right-6 text-2xl">
            <i class="fas fa-times"></i>
        </button>
    </div>

    <!-- Hero Section -->
    <section class="relative h-screen flex items-center pt-16">
        <div class="absolute inset-0 bg-black opacity-30"></div>
        <div class="absolute inset-0 bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1483985988355-763728e1935b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1740&q=80');"></div>
        
        <div class="container mx-auto px-4 relative z-10 text-white">
            <h1 class="font-cormorant text-5xl md:text-7xl font-light mb-6">Elegancja w każdym detalu</h1>
            <p class="text-xl md:text-2xl max-w-2xl mb-8">Ponadczasowe projekty, które staną się fundamentem Twojej garderoby na lata.</p>
            <a href="#" class="inline-block bg-black text-white px-8 py-3 hover:bg-gray-800 transition">Odkryj kolekcję</a>
        </div>
    </section>

    <!-- Katalog -->
    <section class="py-20 container mx-auto px-4">
        <div class="text-center max-w-3xl mx-auto mb-16">
            <h2 class="font-cormorant text-3xl md:text-4xl mb-4">Odkryj nasze kolekcje</h2>
            <p class="text-lg text-gray-600">Poznaj nasze starannie wyselekcjonowane kolekcje, stworzone z myślą o tych, którzy doceniają ponadczasową elegancję i najwyższą jakość wykonania.</p>
        </div>
        
        <div class="grid md:grid-cols-3 gap-8">
            <!-- Kategoria 1 -->
            <div class="relative group overflow-hidden h-[500px]">
                <div class="absolute inset-0 bg-cover bg-center transition-transform duration-500 group-hover:scale-105" style="background-image: url('https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1736&q=80');"></div>
                <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent flex flex-col justify-end p-8 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                    <h3 class="font-cormorant text-3xl text-white mb-2">Spodnie</h3>
                    <p class="text-white/80 mb-4">Klasyczne fasony wykonane z najlepszych materiałów</p>
                    <a href="#" class="text-white border border-white px-6 py-2 hover:bg-white hover:text-black transition w-fit">Zobacz kolekcję →</a>
                </div>
                <div class="absolute bottom-0 left-0 p-6">
                    <span class="bg-white px-4 py-1 text-sm">24 produkty</span>
                </div>
            </div>
            
            <!-- Kategoria 2 -->
            <div class="relative group overflow-hidden h-[500px]">
                <div class="absolute inset-0 bg-cover bg-center transition-transform duration-500 group-hover:scale-105" style="background-image: url('https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80');"></div>
                <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent flex flex-col justify-end p-8 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                    <h3 class="font-cormorant text-3xl text-white mb-2">Koszule</h3>
                    <p class="text-white/80 mb-4">Doskonałe dopasowanie i niezwykła wygoda</p>
                    <a href="#" class="text-white border border-white px-6 py-2 hover:bg-white hover:text-black transition w-fit">Zobacz kolekcję →</a>
                </div>
                <div class="absolute bottom-0 left-0 p-6">
                    <span class="bg-white px-4 py-1 text-sm">18 produktów</span>
                </div>
            </div>
            
            <!-- Kategoria 3 -->
            <div class="relative group overflow-hidden h-[500px]">
                <div class="absolute inset-0 bg-cover bg-center transition-transform duration-500 group-hover:scale-105" style="background-image: url('https://images.unsplash.com/photo-1620799140408-edc6dcb6d633?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1548&q=80');"></div>
                <div class="absolute inset-0 bg-gradient-to-t from-black/70 via-black/30 to-transparent flex flex-col justify-end p-8 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                    <h3 class="font-cormorant text-3xl text-white mb-2">Golfy</h3>
                    <p class="text-white/80 mb-4">Miękkie i ciepłe, idealne na każdą porę roku</p>
                    <a href="#" class="text-white border border-white px-6 py-2 hover:bg-white hover:text-black transition w-fit">Zobacz kolekcję →</a>
                </div>
                <div class="absolute bottom-0 left-0 p-6">
                    <span class="bg-white px-4 py-1 text-sm">12 produktów</span>
                </div>
            </div>
        </div>

        <div class="text-center mt-16">
            <a href="#" class="inline-block border-2 border-black px-8 py-3 hover:bg-black hover:text-white transition font-medium">Przeglądaj cały katalog</a>
        </div>
    </section>

    <!-- Featured Products -->
    <section class="py-20 bg-white">
        <div class="container mx-auto px-4">
            <h2 class="font-cormorant text-3xl md:text-4xl text-center mb-12">Polecane produkty</h2>
            
            <div class="grid sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8">
                <!-- Product 1 -->
                <div class="product-card relative group">
                    <div class="relative overflow-hidden mb-4">
                        <img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1736&q=80" alt="Spodnie klasyczne" class="w-full h-96 object-cover">
                        <img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1736&q=80" alt="Spodnie klasyczne - tył" class="secondary-image absolute inset-0 w-full h-full object-cover">
                        <div class="absolute top-4 right-4">
                            <button class="w-10 h-10 bg-white rounded-full flex items-center justify-center hover:bg-black hover:text-white transition">
                                <i class="far fa-heart"></i>
                            </button>
                        </div>
                    </div>
                    <h3 class="font-medium mb-1">Klasyczne spodnie wełniane</h3>
                    <p class="text-gray-600 mb-2">1 299 PLN</p>
                    <button class="w-full bg-black text-white py-2 hover:bg-gray-800 transition">Dodaj do koszyka</button>
                </div>
                
                <!-- Product 2 -->
                <div class="product-card relative group">
                    <div class="relative overflow-hidden mb-4">
                        <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana" class="w-full h-96 object-cover">
                        <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana - tył" class="secondary-image absolute inset-0 w-full h-full object-cover">
                        <div class="absolute top-4 right-4">
                            <button class="w-10 h-10 bg-white rounded-full flex items-center justify-center hover:bg-black hover:text-white transition">
                                <i class="far fa-heart"></i>
                            </button>
                        </div>
                    </div>
                    <h3 class="font-medium mb-1">Koszula bawełniana</h3>
                    <p class="text-gray-600 mb-2">599 PLN</p>
                    <button class="w-full bg-black text-white py-2 hover:bg-gray-800 transition">Dodaj do koszyka</button>
                </div>
                
                <!-- Product 3 -->
                <div class="product-card relative group">
                    <div class="relative overflow-hidden mb-4">
                        <img src="https://images.unsplash.com/photo-1620799140408-edc6dcb6d633?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1548&q=80" alt="Golf kaszmirowy" class="w-full h-96 object-cover">
                        <img src="https://images.unsplash.com/photo-1620799140408-edc6dcb6d633?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1548&q=80" alt="Golf kaszmirowy - tył" class="secondary-image absolute inset-0 w-full h-full object-cover">
                        <div class="absolute top-4 right-4">
                            <button class="w-10 h-10 bg-white rounded-full flex items-center justify-center hover:bg-black hover:text-white transition">
                                <i class="far fa-heart"></i>
                            </button>
                        </div>
                    </div>
                    <h3 class="font-medium mb-1">Golf kaszmirowy</h3>
                    <p class="text-gray-600 mb-2">899 PLN</p>
                    <button class="w-full bg-black text-white py-2 hover:bg-gray-800 transition">Dodaj do koszyka</button>
                </div>
                
                <!-- Product 4 -->
                <div class="product-card relative group">
                    <div class="relative overflow-hidden mb-4">
                        <img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1736&q=80" alt="Spodnie lniane" class="w-full h-96 object-cover">
                        <img src="https://images.unsplash.com/photo-1591047139829-d91aecb6caea?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1736&q=80" alt="Spodnie lniane - tył" class="secondary-image absolute inset-0 w-full h-full object-cover">
                        <div class="absolute top-4 right-4">
                            <button class="w-10 h-10 bg-white rounded-full flex items-center justify-center hover:bg-black hover:text-white transition">
                                <i class="far fa-heart"></i>
                            </button>
                        </div>
                    </div>
                    <h3 class="font-medium mb-1">Spodnie lniane</h3>
                    <p class="text-gray-600 mb-2">1 099 PLN</p>
                    <button class="w-full bg-black text-white py-2 hover:bg-gray-800 transition">Dodaj do koszyka</button>
                </div>
            </div>
            
            <div class="text-center mt-12">
                <a href="#" class="inline-block border border-black px-8 py-3 hover:bg-black hover:text-white transition">Zobacz wszystkie produkty</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="py-20 bg-gray-50">
        <div class="container mx-auto px-4">
            <div class="flex flex-col md:flex-row items-center md:items-start">
                <div class="md:w-1/2 mb-8 md:mb-0 md:pr-12">
                    <h2 class="font-cormorant text-3xl md:text-4xl mb-6">O Atelier Élégance</h2>
                    <p class="mb-6">W Atelier Élégance wierzymy, że prawdziwy luksus kryje się w ponadczasowym wzornictwie i doskonałej jakości. Nie podążamy za chwilowymi trendami. Zamiast tego, przeszukujemy świat w poszukiwaniu najlepszych dostawców i starannie selekcjonujemy ubrania, które staną się fundamentem Twojej garderoby na lata.</p>
                    <p class="mb-8">Naszą misją jest dostarczanie wyselekcjonowanych, eleganckich ubrań, które łączą w sobie klasyczny styl z nowoczesną wygodą, dając Ci pewność siebie każdego dnia.</p>
                    <a href="#" class="inline-block border border-black px-8 py-3 hover:bg-black hover:text-white transition">Poznaj naszą historię</a>
                </div>
                <div class="md:w-1/2">
                    <img src="https://images.unsplash.com/photo-1605000797499-95a51c5269ae?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1742&q=80" alt="Atelier Élégance" class="w-full h-auto">
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter -->
    <section class="py-16 bg-black text-white">
        <div class="container mx-auto px-4 text-center">
            <h2 class="font-cormorant text-3xl md:text-4xl mb-4">Zapisz się do naszego newslettera</h2>
            <p class="max-w-2xl mx-auto mb-8">Otrzymuj informacje o nowościach, ekskluzywnych ofertach i inspiracje stylistyczne prosto na swoją skrzynkę.</p>
            
            <form class="max-w-md mx-auto flex">
                <input type="email" placeholder="Twój adres e-mail" class="flex-grow px-4 py-3 text-black focus:outline-none">
                <button type="submit" class="bg-white text-black px-6 py-3 hover:bg-gray-200 transition">Zapisz się</button>
            </form>
            
            <p class="text-sm text-gray-400 mt-4">Zapisując się, wyrażasz zgodę na otrzymywanie wiadomości marketingowych.</p>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-white pt-16 pb-8">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-3 gap-8 mb-12">
                <div>
                    <h3 class="font-cormorant text-xl font-medium mb-4">Obsługa klienta</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-gray-600 transition">Kontakt</a></li>
                        <li><a href="#" class="hover:text-gray-600 transition">Zwroty i reklamacje</a></li>
                        <li><a href="#" class="hover:text-gray-600 transition">Regulamin</a></li>
                        <li><a href="#" class="hover:text-gray-600 transition">Polityka prywatności</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="font-cormorant text-xl font-medium mb-4">Atelier Élégance</h3>
                    <ul class="space-y-2">
                        <li><a href="#" class="hover:text-gray-600 transition">O nas</a></li>
                        <li><a href="#" class="hover:text-gray-600 transition">Lookbook</a></li>
                        <li><a href="#" class="hover:text-gray-600 transition">Kariera</a></li>
                        <li><a href="#" class="hover:text-gray-600 transition">Blog</a></li>
                    </ul>
                </div>
                
                <div>
                    <h3 class="font-cormorant text-xl font-medium mb-4">Śledź nas</h3>
                    <div class="flex space-x-4 mb-6">
                        <a href="#" class="w-10 h-10 border border-black rounded-full flex items-center justify-center hover:bg-black hover:text-white transition"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" class="w-10 h-10 border border-black rounded-full flex items-center justify-center hover:bg-black hover:text-white transition"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="w-10 h-10 border border-black rounded-full flex items-center justify-center hover:bg-black hover:text-white transition"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                    
                    <h3 class="font-cormorant text-xl font-medium mb-4">Metody płatności</h3>
                    <div class="flex space-x-2">
                        <img src="https://cdn-icons-png.flaticon.com/512/196/196578.png" alt="Visa" class="h-8">
                        <img src="https://cdn-icons-png.flaticon.com/512/196/196561.png" alt="Mastercard" class="h-8">
                        <img src="https://cdn-icons-png.flaticon.com/512/217/217853.png" alt="PayPal" class="h-8">
                        <img src="https://cdn-icons-png.flaticon.com/512/888/888870.png" alt="Apple Pay" class="h-8">
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-200 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <p class="text-sm text-gray-500 mb-4 md:mb-0">© 2023 Atelier Élégance. Wszelkie prawa zastrzeżone.</p>
                    <div class="flex space-x-4">
                        <img src="https://www.inpost.pl/themes/custom/inpost_theme/images/logo.svg" alt="InPost" class="h-6">
                        <img src="https://www.dpd.com/pl/pl/wp-content/themes/dpdgroup/dist/images/logo.svg" alt="DPD" class="h-6">
                    </div>
                </div>
            </div>
        </div>
    </footer>

    <!-- Product Page Example (Hidden) -->
    <div id="product-page" class="hidden">
        <div class="container mx-auto px-4 py-32">
            <div class="flex flex-col lg:flex-row gap-12">
                <!-- Product Gallery -->
                <div class="lg:w-1/2">
                    <div class="mb-4">
                        <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana" class="w-full h-auto">
                    </div>
                    <div class="grid grid-cols-4 gap-2">
                        <button class="border border-gray-200 p-1">
                            <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana - przód" class="w-full h-20 object-cover">
                        </button>
                        <button class="border border-gray-200 p-1">
                            <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana - tył" class="w-full h-20 object-cover">
                        </button>
                        <button class="border border-gray-200 p-1">
                            <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana - detal" class="w-full h-20 object-cover">
                        </button>
                        <button class="border border-gray-200 p-1">
                            <img src="https://images.unsplash.com/photo-1529374255404-311a2a4f1fd9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1738&q=80" alt="Koszula bawełniana - na modelu" class="w-full h-20 object-cover">
                        </button>
                    </div>
                </div>
                
                <!-- Product Info -->
                <div class="lg:w-1/2">
                    <h1 class="font-cormorant text-3xl md:text-4xl mb-2">Koszula bawełniana</h1>
                    <p class="text-2xl mb-6">599 PLN</p>
                    
                    <div class="mb-6">
                        <h3 class="font-medium mb-2">Kolor</h3>
                        <div class="flex space-x-2">
                            <button class="w-8 h-8 border border-gray-200 bg-white"></button>
                            <button class="w-8 h-8 border border-gray-200 bg-blue-900"></button>
                            <button class="w-8 h-8 border border-gray-200 bg-gray-200"></button>
                            <button class="w-8 h-8 border border-gray-200 bg-red-800"></button>
                        </div>
                    </div>
                    
                    <div class="mb-8">
                        <h3 class="font-medium mb-2">Rozmiar</h3>
                        <div class="flex flex-wrap gap-2">
                            <button class="px-4 py-2 border border-gray-200 hover:border-black transition">XS</button>
                            <button class="px-4 py-2 border border-gray-200 hover:border-black transition">S</button>
                            <button class="px-4 py-2 border border-gray-200 hover:border-black transition">M</button>
                            <button class="px-4 py-2 border border-gray-200 hover:border-black transition">L</button>
                            <button class="px-4 py-2 border border-gray-200 hover:border-black transition">XL</button>
                        </div>
                    </div>
                    
                    <button class="w-full bg-black text-white py-4 mb-6 hover:bg-gray-800 transition">Dodaj do koszyka</button>
                    
                    <div class="space-y-4">
                        <!-- Accordion 1 -->
                        <div class="accordion border-b border-gray-200 pb-4">
                            <button class="accordion-btn w-full flex justify-between items-center">
                                <span class="font-medium">Opis</span>
                                <i class="fas fa-chevron-down accordion-icon text-xs"></i>
                            </button>
                            <div class="accordion-content">
                                <p class="pt-2">Nasza koszula bawełniana to kwintesencja niewymuszonej elegancji. Uszyta z najwyższej jakości tkaniny, zapewnia komfort przez cały dzień. Jej klasyczny krój sprawia, że jest idealną bazą zarówno do biurowych, jak i weekendowych stylizacji.</p>
                            </div>
                        </div>
                        
                        <!-- Accordion 2 -->
                        <div class="accordion border-b border-gray-200 pb-4">
                            <button class="accordion-btn w-full flex justify-between items-center">
                                <span class="font-medium">Skład i pielęgnacja</span>
                                <i class="fas fa-chevron-down accordion-icon text-xs"></i>
                            </button>
                            <div class="accordion-content">
                                <p class="pt-2">100% bawełna egipska. Pranie w temp. 30°C. Prasowanie w średniej temperaturze. Nie wybielać.</p>
                            </div>
                        </div>
                        
                        <!-- Accordion 3 -->
                        <div class="accordion border-b border-gray-200 pb-4">
                            <button class="accordion-btn w-full flex justify-between items-center">
                                <span class="font-medium">Tabela rozmiarów</span>
                                <i class="fas fa-chevron-down accordion-icon text-xs"></i>
                            </button>
                            <div class="accordion-content">
                                <div class="pt-2 overflow-x-auto">
                                    <table class="w-full text-sm">
                                        <thead>
                                            <tr class="border-b border-gray-200">
                                                <th class="text-left py-2">Rozmiar</th>
                                                <th class="text-left py-2">Szerokość (cm)</th>
                                                <th class="text-left py-2">Długość (cm)</th>
                                                <th class="text-left py-2">Długość rękawa (cm)</th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr class="border-b border-gray-200">
                                                <td class="py-2">XS</td>
                                                <td class="py-2">48</td>
                                                <td class="py-2">68</td>
                                                <td class="py-2">62</td>
                                            </tr>
                                            <tr class="border-b border-gray-200">
                                                <td class="py-2">S</td>
                                                <td class="py-2">50</td>
                                                <td class="py-2">70</td>
                                                <td class="py-2">63</td>
                                            </tr>
                                            <tr class="border-b border-gray-200">
                                                <td class="py-2">M</td>
                                                <td class="py-2">52</td>
                                                <td class="py-2">72</td>
                                                <td class="py-2">64</td>
                                            </tr>
                                            <tr class="border-b border-gray-200">
                                                <td class="py-2">L</td>
                                                <td class="py-2">54</td>
                                                <td class="py-2">74</td>
                                                <td class="py-2">65</td>
                                            </tr>
                                            <tr>
                                                <td class="py-2">XL</td>
                                                <td class="py-2">56</td>
                                                <td class="py-2">76</td>
                                                <td class="py-2">66</td>
                                            </tr>
                                        </tbody>
                                    </table>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Mobile menu toggle
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');
        const closeMenuButton = document.getElementById('close-menu');
        
        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.add('open');
            document.body.style.overflow = 'hidden';
        });
        
        closeMenuButton.addEventListener('click', () => {
            mobileMenu.classList.remove('open');
            document.body.style.overflow = '';
        });

        // Accordion functionality
        const accordions = document.querySelectorAll('.accordion');
        
        accordions.forEach(accordion => {
            const btn = accordion.querySelector('.accordion-btn');
            const content = accordion.querySelector('.accordion-content');
            
            btn.addEventListener('click', () => {
                accordion.classList.toggle('active');
            });
        });

        // Product image hover effect
        const productCards = document.querySelectorAll('.product-card');
        
        productCards.forEach(card => {
            const primaryImg = card.querySelector('img:not(.secondary-image)');
            const secondaryImg = card.querySelector('.secondary-image');
            
            card.addEventListener('mouseenter', () => {
                primaryImg.style.opacity = '0';
                secondaryImg.style.opacity = '1';
            });
            
            card.addEventListener('mouseleave', () => {
                primaryImg.style.opacity = '1';
                secondaryImg.style.opacity = '0';
            });
        });
    </script>
</body>
</html>
