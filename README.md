# Fitlife.pro
<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FitLife Pro | Modern Fitness & Wellness</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Tailwind Config -->
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        primary: {
                            50: '#f0fdf4', 100: '#dcfce7', 500: '#22c55e', 600: '#16a34a', 700: '#15803d', 900: '#14532d',
                        },
                        secondary: {
                            500: '#f59e0b', 600: '#d97706',
                        },
                        dark: {
                            800: '#1e293b', 900: '#0f172a'
                        }
                    },
                    animation: {
                        'bounce-slow': 'bounce 3s infinite',
                        'fade-in-up': 'fadeInUp 0.8s ease-out forwards',
                        'float': 'float 6s ease-in-out infinite',
                        'pulse-glow': 'pulseGlow 2s ease-in-out infinite alternate',
                        'gradient': 'gradient 15s ease infinite',
                    },
                    keyframes: {
                        fadeInUp: {
                            '0%': { opacity: '0', transform: 'translateY(20px)' },
                            '100%': { opacity: '1', transform: 'translateY(0)' },
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0)' },
                            '50%': { transform: 'translateY(-10px)' },
                        },
                        pulseGlow: {
                            '0%': { boxShadow: '0 0 5px rgba(34, 197, 94, 0.5)' },
                            '100%': { boxShadow: '0 0 20px rgba(34, 197, 94, 0.8)' },
                        },
                        gradient: {
                            '0%': { backgroundPosition: '0% 50%' },
                            '50%': { backgroundPosition: '100% 50%' },
                            '100%': { backgroundPosition: '0% 50%' },
                        }
                    },
                    backgroundSize: {
                        'gradient': '200% 200%',
                    }
                }
            }
        }
    </script>
    <!-- Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 10px; }
        ::-webkit-scrollbar-track { background: #f1f1f1; }
        .dark ::-webkit-scrollbar-track { background: #1f2937; }
        ::-webkit-scrollbar-thumb { background: #22c55e; border-radius: 5px; }
        ::-webkit-scrollbar-thumb:hover { background: #16a34a; }

        /* Glassmorphism */
        .glass {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
        }
        .dark .glass {
            background: rgba(17, 24, 39, 0.85);
        }

        /* Chat Widget Animation */
        .chat-open { transform: scale(1); opacity: 1; pointer-events: auto; }
        .chat-closed { transform: scale(0.9); opacity: 0; pointer-events: none; }

        /* Loader */
        .typing-dot {
            animation: typing 1.4s infinite ease-in-out both;
        }
        .typing-dot:nth-child(1) { animation-delay: -0.32s; }
        .typing-dot:nth-child(2) { animation-delay: -0.16s; }
        @keyframes typing {
            0%, 80%, 100% { transform: scale(0); }
            40% { transform: scale(1); }
        }

        /* Gradient Text */
        .gradient-text {
            background: linear-gradient(90deg, #22c55e, #f59e0b, #84cc16);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradient 4s linear infinite;
        }

        /* Enhanced Button Styles */
        .btn-glow {
            box-shadow: 0 4px 14px 0 rgba(34, 197, 94, 0.4);
            transition: all 0.3s ease;
        }
        .btn-glow:hover {
            box-shadow: 0 6px 20px rgba(34, 197, 94, 0.6);
            transform: translateY(-2px);
        }

        /* Card Hover Effects */
        .card-hover {
            transition: all 0.3s ease;
        }
        .card-hover:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
        }

        /* Pulse Animation */
        .pulse-animate {
            animation: pulse 2s infinite;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-900 dark:bg-gray-950 dark:text-gray-100 transition-colors duration-300 font-sans selection:bg-primary-500 selection:text-white">

    <!-- Preloader -->
    <div id="preloader" class="fixed inset-0 bg-white dark:bg-gray-950 z-[100] flex items-center justify-center transition-opacity duration-500">
        <div class="text-center">
            <div class="w-16 h-16 border-4 border-primary-500 border-t-transparent rounded-full animate-spin mx-auto mb-4"></div>
            <h2 class="text-xl font-bold">FitLife Pro</h2>
            <p class="text-gray-500 mt-2">Loading your fitness journey...</p>
        </div>
    </div>

    <!-- Scroll Progress Bar -->
    <div class="fixed top-0 left-0 h-1 bg-gradient-to-r from-primary-500 to-secondary-500 z-[60]" id="scroll-progress" style="width: 0%"></div>

    <!-- Navigation -->
    <nav class="fixed w-full z-50 glass border-b border-gray-200 dark:border-gray-800 transition-all duration-300" id="navbar">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <!-- Logo -->
                <div class="flex items-center gap-2 cursor-pointer group" onclick="window.scrollTo(0,0)">
                    <div class="bg-primary-600 text-white p-1.5 rounded-lg group-hover:rotate-12 transition-transform">
                        <i data-lucide="dumbbell" class="h-6 w-6"></i>
                    </div>
                    <span class="font-bold text-xl tracking-tight">FitLife<span class="text-primary-600">Pro</span></span>
                </div>

                <!-- Desktop Menu -->
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#programs" class="hover:text-primary-600 transition-colors relative group">
                        Programs
                        <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 group-hover:w-full transition-all duration-300"></span>
                    </a>
                    <a href="#trainers" class="hover:text-primary-600 transition-colors relative group">
                        Trainers
                        <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 group-hover:w-full transition-all duration-300"></span>
                    </a>
                    <a href="#pricing" class="hover:text-primary-600 transition-colors relative group">
                        Pricing
                        <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 group-hover:w-full transition-all duration-300"></span>
                    </a>
                    <a href="#testimonials" class="hover:text-primary-600 transition-colors relative group">
                        Success Stories
                        <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 group-hover:w-full transition-all duration-300"></span>
                    </a>
                    <a href="#faq" class="hover:text-primary-600 transition-colors relative group">
                        FAQ
                        <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-primary-600 group-hover:w-full transition-all duration-300"></span>
                    </a>
                    
                    <button id="theme-toggle" class="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-700 transition-colors">
                        <i data-lucide="sun" class="h-5 w-5 dark:hidden"></i>
                        <i data-lucide="moon" class="h-5 w-5 hidden dark:block"></i>
                    </button>

                    <button onclick="scrollToSection('contact')" class="btn-glow bg-primary-600 hover:bg-primary-700 text-white px-5 py-2 rounded-full font-medium transition-all">
                        Start Today
                    </button>
                </div>

                <!-- Mobile Menu Button -->
                <div class="md:hidden flex items-center gap-4">
                    <button id="theme-toggle-mobile" class="p-2 rounded-full hover:bg-gray-200 dark:hover:bg-gray-800">
                        <i data-lucide="sun" class="h-5 w-5 dark:hidden"></i>
                        <i data-lucide="moon" class="h-5 w-5 hidden dark:block"></i>
                    </button>
                    <button id="mobile-menu-btn" class="p-2 rounded-md hover:bg-gray-200 dark:hover:bg-gray-800">
                        <i data-lucide="menu" class="h-6 w-6"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white dark:bg-gray-900 border-b border-gray-200 dark:border-gray-800 absolute w-full">
            <div class="px-4 py-4 space-y-3">
                <a href="#programs" onclick="toggleMobileMenu()" class="block text-lg font-medium hover:text-primary-600 transition-colors">Programs</a>
                <a href="#trainers" onclick="toggleMobileMenu()" class="block text-lg font-medium hover:text-primary-600 transition-colors">Trainers</a>
                <a href="#pricing" onclick="toggleMobileMenu()" class="block text-lg font-medium hover:text-primary-600 transition-colors">Pricing</a>
                <a href="#testimonials" onclick="toggleMobileMenu()" class="block text-lg font-medium hover:text-primary-600 transition-colors">Success Stories</a>
                <a href="#faq" onclick="toggleMobileMenu()" class="block text-lg font-medium hover:text-primary-600 transition-colors">FAQ</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="pt-32 pb-20 px-4 text-center max-w-7xl mx-auto min-h-[80vh] flex flex-col justify-center items-center relative overflow-hidden bg-gradient-to-br from-primary-500/10 to-secondary-500/10">
        <div class="animate-fade-in-up relative z-10">
            <span class="inline-block py-1 px-3 rounded-full bg-primary-100 dark:bg-primary-900 text-primary-600 dark:text-primary-300 text-sm font-semibold mb-6">
                New: AI Personal Training
            </span>
            <h1 class="text-5xl md:text-7xl font-extrabold tracking-tight mb-6">
                Transform Your <span class="gradient-text">Body & Mind</span><span class="animate-pulse">|</span>
            </h1>
            <p class="text-xl text-gray-600 dark:text-gray-300 mb-10 max-w-2xl mx-auto leading-relaxed">
                Join thousands who have transformed their lives with our personalized fitness programs, expert trainers, and supportive community.
            </p>
            <div class="flex flex-col sm:flex-row justify-center gap-4">
                <button onclick="scrollToSection('pricing')" class="btn-glow px-8 py-4 rounded-full bg-primary-600 text-white font-bold hover:bg-primary-700 transition-all flex items-center justify-center gap-2 group">
                    Start Free Trial <i data-lucide="arrow-right" class="group-hover:translate-x-1 transition-transform"></i>
                </button>
                <button onclick="scrollToSection('programs')" class="px-8 py-4 rounded-full border border-gray-300 dark:border-gray-700 hover:bg-gray-100 dark:hover:bg-gray-800 transition-colors font-bold flex items-center justify-center gap-2">
                    <i data-lucide="play-circle" class="h-5 w-5"></i> Watch Demo
                </button>
            </div>
        </div>
        
        <!-- Floating Elements -->
        <div class="absolute top-1/4 left-10 w-24 h-24 bg-primary-500/10 rounded-full blur-2xl animate-float -z-10"></div>
        <div class="absolute bottom-1/4 right-10 w-32 h-32 bg-secondary-500/10 rounded-full blur-2xl animate-float -z-10" style="animation-delay: 2s"></div>
        
        <!-- Scroll Indicator -->
        <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
            <i data-lucide="chevron-down" class="h-6 w-6 text-gray-400"></i>
        </div>
    </section>

    <!-- Stats Section -->
    <section id="stats" class="py-16 bg-gradient-to-br from-primary-600 via-green-600 to-secondary-600 text-white relative overflow-hidden">
        <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGNpcmNsZSBjeD0iMiIgY3k9IjIiIHI9IjIiIGZpbGw9InJnYmEoMjU1LDI1NSwyNTUsMC4xKSIvPjwvc3ZnPg==')] opacity-20"></div>
        <div class="max-w-7xl mx-auto px-4 grid grid-cols-2 md:grid-cols-4 gap-8 text-center relative z-10">
            <div class="p-4 transform transition-all hover:scale-105">
                <div class="text-4xl md:text-5xl font-bold mb-2 count-up" data-target="5000">0</div>
                <div class="text-primary-100">Active Members</div>
            </div>
            <div class="p-4 transform transition-all hover:scale-105">
                <div class="text-4xl md:text-5xl font-bold mb-2 count-up" data-target="98">0</div>
                <div class="text-primary-100">Success Rate</div>
            </div>
            <div class="p-4 transform transition-all hover:scale-105">
                <div class="text-4xl md:text-5xl font-bold mb-2 count-up" data-target="25">0</div>
                <div class="text-primary-100">Expert Trainers</div>
            </div>
            <div class="p-4 transform transition-all hover:scale-105">
                <div class="text-4xl md:text-5xl font-bold mb-2 count-up" data-target="15">0</div>
                <div class="text-primary-100">Years Experience</div>
            </div>
        </div>
    </section>

    <!-- Programs Section -->
    <section id="programs" class="py-20 bg-white dark:bg-gray-900 transition-colors">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold mb-4">Our Fitness Programs</h2>
                <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto">Choose from our variety of specialized programs designed for all fitness levels and goals.</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Program 1 -->
                <div class="card-hover bg-gray-50 dark:bg-gray-800 p-6 rounded-xl relative overflow-hidden">
                    <div class="absolute top-4 right-4 w-12 h-12 bg-primary-500 text-white rounded-full flex items-center justify-center">
                        <i data-lucide="dumbbell" class="h-6 w-6"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-2">Strength Training</h3>
                    <p class="text-gray-600 dark:text-gray-400 mb-4">Build muscle and increase strength with our proven weight training programs.</p>
                    <ul class="space-y-2 mb-6 text-gray-600 dark:text-gray-400">
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Personalized workout plans</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Form correction</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Progressive overload</li>
                    </ul>
                    <button class="w-full py-3 rounded-lg bg-primary-100 dark:bg-gray-700 text-primary-700 dark:text-white font-bold hover:bg-primary-200 dark:hover:bg-gray-600 transition-colors">Learn More</button>
                </div>
                
                <!-- Program 2 -->
                <div class="card-hover bg-gray-50 dark:bg-gray-800 p-6 rounded-xl relative overflow-hidden">
                    <div class="absolute top-4 right-4 w-12 h-12 bg-secondary-500 text-white rounded-full flex items-center justify-center">
                        <i data-lucide="heart" class="h-6 w-6"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-2">Cardio & Endurance</h3>
                    <p class="text-gray-600 dark:text-gray-400 mb-4">Improve cardiovascular health and build endurance with dynamic workouts.</p>
                    <ul class="space-y-2 mb-6 text-gray-600 dark:text-gray-400">
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> HIIT workouts</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Running programs</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Heart rate monitoring</li>
                    </ul>
                    <button class="w-full py-3 rounded-lg bg-primary-100 dark:bg-gray-700 text-primary-700 dark:text-white font-bold hover:bg-primary-200 dark:hover:bg-gray-600 transition-colors">Learn More</button>
                </div>
                
                <!-- Program 3 -->
                <div class="card-hover bg-gray-50 dark:bg-gray-800 p-6 rounded-xl relative overflow-hidden">
                    <div class="absolute top-4 right-4 w-12 h-12 bg-primary-500 text-white rounded-full flex items-center justify-center">
                        <i data-lucide="leaf" class="h-6 w-6"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-2">Yoga & Mindfulness</h3>
                    <p class="text-gray-600 dark:text-gray-400 mb-4">Find balance and flexibility through our yoga and meditation programs.</p>
                    <ul class="space-y-2 mb-6 text-gray-600 dark:text-gray-400">
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Guided meditation</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Flexibility training</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Stress reduction</li>
                    </ul>
                    <button class="w-full py-3 rounded-lg bg-primary-100 dark:bg-gray-700 text-primary-700 dark:text-white font-bold hover:bg-primary-200 dark:hover:bg-gray-600 transition-colors">Learn More</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Trainers Section -->
    <section id="trainers" class="py-20 bg-gray-50 dark:bg-gray-800/50 transition-colors">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-16">
                <h2 class="text-3xl font-bold mb-4">Meet Our Expert Trainers</h2>
                <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto">Our certified trainers are dedicated to helping you achieve your fitness goals.</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Trainer 1 -->
                <div class="card-hover bg-white dark:bg-gray-800 rounded-xl overflow-hidden text-center">
                    <img src="https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?auto=format&fit=crop&w=800&q=80" class="w-full h-64 object-cover" alt="Trainer">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-1">Sarah Johnson</h3>
                        <p class="text-primary-600 mb-4">Strength & Conditioning Specialist</p>
                        <p class="text-gray-600 dark:text-gray-400 mb-4">10+ years experience in strength training and athletic performance.</p>
                        <div class="flex justify-center gap-3">
                            <a href="#" class="p-2 bg-primary-100 text-primary-600 rounded-full hover:bg-primary-200 transition-colors">
                                <i data-lucide="instagram" class="h-4 w-4"></i>
                            </a>
                            <a href="#" class="p-2 bg-primary-100 text-primary-600 rounded-full hover:bg-primary-200 transition-colors">
                                <i data-lucide="linkedin" class="h-4 w-4"></i>
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Trainer 2 -->
                <div class="card-hover bg-white dark:bg-gray-800 rounded-xl overflow-hidden text-center">
                    <img src="https://images.unsplash.com/photo-1534367507877-0edd93bd013b?auto=format&fit=crop&w=800&q=80" class="w-full h-64 object-cover" alt="Trainer">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-1">Mike Rodriguez</h3>
                        <p class="text-primary-600 mb-4">Cardio & Nutrition Coach</p>
                        <p class="text-gray-600 dark:text-gray-400 mb-4">Specialized in marathon training and sports nutrition.</p>
                        <div class="flex justify-center gap-3">
                            <a href="#" class="p-2 bg-primary-100 text-primary-600 rounded-full hover:bg-primary-200 transition-colors">
                                <i data-lucide="instagram" class="h-4 w-4"></i>
                            </a>
                            <a href="#" class="p-2 bg-primary-100 text-primary-600 rounded-full hover:bg-primary-200 transition-colors">
                                <i data-lucide="linkedin" class="h-4 w-4"></i>
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Trainer 3 -->
                <div class="card-hover bg-white dark:bg-gray-800 rounded-xl overflow-hidden text-center">
                    <img src="https://images.unsplash.com/photo-1544367567-0f2fcb009e0b?auto=format&fit=crop&w=800&q=80" class="w-full h-64 object-cover" alt="Trainer">
                    <div class="p-6">
                        <h3 class="text-xl font-bold mb-1">Emily Chen</h3>
                        <p class="text-primary-600 mb-4">Yoga & Wellness Instructor</p>
                        <p class="text-gray-600 dark:text-gray-400 mb-4">RYT-500 certified with expertise in mindfulness and flexibility.</p>
                        <div class="flex justify-center gap-3">
                            <a href="#" class="p-2 bg-primary-100 text-primary-600 rounded-full hover:bg-primary-200 transition-colors">
                                <i data-lucide="instagram" class="h-4 w-4"></i>
                            </a>
                            <a href="#" class="p-2 bg-primary-100 text-primary-600 rounded-full hover:bg-primary-200 transition-colors">
                                <i data-lucide="linkedin" class="h-4 w-4"></i>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="py-20 bg-white dark:bg-gray-900 transition-colors">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <h2 class="text-3xl font-bold mb-6">Choose Your Plan</h2>
            <p class="text-gray-600 dark:text-gray-400 max-w-2xl mx-auto mb-12">Flexible pricing options to fit your fitness journey and budget.</p>
            
            <!-- Toggle -->
            <div class="flex items-center justify-center gap-4 mb-12">
                <span class="text-gray-600 dark:text-gray-400 font-medium">Monthly</span>
                <button id="billing-toggle" class="w-14 h-8 bg-gray-300 dark:bg-gray-600 rounded-full p-1 transition-colors relative focus:outline-none" onclick="toggleBilling()">
                    <div id="toggle-circle" class="w-6 h-6 bg-white rounded-full shadow-md transform transition-transform duration-300"></div>
                </button>
                <span class="text-gray-900 dark:text-gray-100 font-bold">Yearly <span class="text-xs text-green-500 ml-1">Save 20%</span></span>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                <!-- Basic -->
                <div class="card-hover bg-white dark:bg-gray-800 p-8 rounded-2xl shadow-lg border border-gray-200 dark:border-gray-700 transition-all">
                    <h3 class="text-xl font-bold mb-2">Starter</h3>
                    <div class="text-4xl font-extrabold mb-6 flex justify-center items-end">
                        $<span class="price-amount" data-monthly="29" data-yearly="24">29</span>
                        <span class="text-base text-gray-500 dark:text-gray-400 font-normal mb-1">/mo</span>
                    </div>
                    <ul class="space-y-4 mb-8 text-left text-gray-600 dark:text-gray-400">
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Basic Workout Plans</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> App Access</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Email Support</li>
                        <li class="flex gap-2"><i data-lucide="x" class="text-gray-400 h-5 w-5"></i> Personal Trainer</li>
                    </ul>
                    <button class="w-full py-3 rounded-lg bg-primary-100 dark:bg-gray-700 text-primary-700 dark:text-white font-bold hover:bg-primary-200 dark:hover:bg-gray-600 transition-colors">Get Started</button>
                </div>

                <!-- Pro -->
                <div class="card-hover bg-white dark:bg-gray-800 p-8 rounded-2xl shadow-xl border-2 border-primary-500 transform md:-translate-y-4 animate-pulse-glow">
                    <div class="bg-primary-500 text-white text-xs font-bold px-3 py-1 rounded-full inline-block mb-4">MOST POPULAR</div>
                    <h3 class="text-xl font-bold mb-2">Pro</h3>
                    <div class="text-4xl font-extrabold mb-6 flex justify-center items-end">
                        $<span class="price-amount" data-monthly="79" data-yearly="63">79</span>
                        <span class="text-base text-gray-500 dark:text-gray-400 font-normal mb-1">/mo</span>
                    </div>
                    <ul class="space-y-4 mb-8 text-left text-gray-600 dark:text-gray-400">
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Personalized Plans</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> 1-on-1 Coaching</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Nutrition Guidance</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Progress Tracking</li>
                    </ul>
                    <button class="btn-glow w-full py-3 rounded-lg bg-primary-600 text-white font-bold hover:bg-primary-700 transition-colors">Get Started</button>
                </div>

                <!-- Elite -->
                <div class="card-hover bg-white dark:bg-gray-800 p-8 rounded-2xl shadow-lg border border-gray-200 dark:border-gray-700 transition-all">
                    <h3 class="text-xl font-bold mb-2">Elite</h3>
                    <div class="text-4xl font-extrabold mb-6 flex justify-center items-end">
                        $<span class="price-amount" data-monthly="149" data-yearly="119">149</span>
                        <span class="text-base text-gray-500 dark:text-gray-400 font-normal mb-1">/mo</span>
                    </div>
                    <ul class="space-y-4 mb-8 text-left text-gray-600 dark:text-gray-400">
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> All Pro Features</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Unlimited Sessions</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> 24/7 Support</li>
                        <li class="flex gap-2"><i data-lucide="check" class="text-primary-500 h-5 w-5"></i> Custom Meal Plans</li>
                    </ul>
                    <button class="w-full py-3 rounded-lg bg-primary-100 dark:bg-gray-700 text-primary-700 dark:text-white font-bold hover:bg-primary-200 dark:hover:bg-gray-600 transition-colors">Get Started</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section id="testimonials" class="py-20 bg-gradient-to-br from-primary-600 via-green-600 to-secondary-600 text-white relative overflow-hidden">
        <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGNpcmNsZSBjeD0iMiIgY3k9IjIiIHI9IjIiIGZpbGw9InJnYmEoMjU1LDI1NSwyNTUsMC4xKSIvPjwvc3ZnPg==')] opacity-20"></div>
        <div class="max-w-4xl mx-auto px-4 text-center relative z-10">
            <h2 class="text-3xl font-bold mb-12">Success Stories</h2>
            <div class="grid md:grid-cols-2 gap-8">
                <div class="bg-white/10 backdrop-blur rounded-xl p-6 text-left">
                    <div class="flex items-center gap-4 mb-4">
                        <img src="https://images.unsplash.com/photo-1494790108755-2616b612b786?auto=format&fit=crop&w=100&q=80" class="w-12 h-12 rounded-full" alt="User">
                        <div>
                            <h4 class="font-bold">Jessica Miller</h4>
                            <p class="text-primary-100 text-sm">Lost 35 lbs</p>
                        </div>
                    </div>
                    <p class="text-primary-50">"The personalized training and nutrition plan helped me achieve my weight loss goals in just 6 months. The support from my trainer was incredible!"</p>
                </div>
                <div class="bg-white/10 backdrop-blur rounded-xl p-6 text-left">
                    <div class="flex items-center gap-4 mb-4">
                        <img src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?auto=format&fit=crop&w=100&q=80" class="w-12 h-12 rounded-full" alt="User">
                        <div>
                            <h4 class="font-bold">David Chen</h4>
                            <p class="text-primary-100 text-sm">Gained 15 lbs muscle</p>
                        </div>
                    </div>
                    <p class="text-primary-50">"As someone who struggled to gain weight, the strength training program and nutritional guidance helped me build the physique I always wanted."</p>
                </div>
            </div>
        </div>
    </section>

    <!-- FAQ Section -->
    <section id="faq" class="py-20 max-w-3xl mx-auto px-4 bg-gray-50 dark:bg-gray-800/50 transition-colors">
        <h2 class="text-3xl font-bold text-center mb-10">Frequently Asked Questions</h2>
        <div class="space-y-4" id="faq-container">
            <!-- FAQ Item 1 -->
            <div class="border border-gray-200 dark:border-gray-700 rounded-lg overflow-hidden bg-white dark:bg-gray-800 transition-colors">
                <button class="w-full flex justify-between items-center p-4 bg-white dark:bg-gray-800 hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors text-left font-medium" onclick="toggleAccordion(this)">
                    <span>How do I get started with a program?</span>
                    <i data-lucide="chevron-down" class="transition-transform duration-300"></i>
                </button>
                <div class="hidden bg-gray-50 dark:bg-gray-900 p-4 text-gray-600 dark:text-gray-300 border-t border-gray-200 dark:border-gray-700">
                    Simply choose a plan, complete our fitness assessment, and we'll match you with the perfect program and trainer for your goals.
                </div>
            </div>
            <!-- FAQ Item 2 -->
            <div class="border border-gray-200 dark:border-gray-700 rounded-lg overflow-hidden bg-white dark:bg-gray-800 transition-colors">
                <button class="w-full flex justify-between items-center p-4 bg-white dark:bg-gray-800 hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors text-left font-medium" onclick="toggleAccordion(this)">
                    <span>Can I change my program later?</span>
                    <i data-lucide="chevron-down" class="transition-transform duration-300"></i>
                </button>
                <div class="hidden bg-gray-50 dark:bg-gray-900 p-4 text-gray-600 dark:text-gray-300 border-t border-gray-200 dark:border-gray-700">
                    Absolutely! You can switch programs or adjust your training focus at any time based on your evolving fitness goals.
                </div>
            </div>
             <!-- FAQ Item 3 -->
             <div class="border border-gray-200 dark:border-gray-700 rounded-lg overflow-hidden bg-white dark:bg-gray-800 transition-colors">
                <button class="w-full flex justify-between items-center p-4 bg-white dark:bg-gray-800 hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors text-left font-medium" onclick="toggleAccordion(this)">
                    <span>What equipment do I need?</span>
                    <i data-lucide="chevron-down" class="transition-transform duration-300"></i>
                </button>
                <div class="hidden bg-gray-50 dark:bg-gray-900 p-4 text-gray-600 dark:text-gray-300 border-t border-gray-200 dark:border-gray-700">
                    Most programs require minimal equipment. We provide bodyweight alternatives and can adapt workouts based on the equipment you have available.
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-gradient-to-br from-primary-600 via-green-600 to-secondary-600 text-white relative overflow-hidden">
        <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PGNpcmNsZSBjeD0iMiIgY3k9IjIiIHI9IjIiIGZpbGw9InJnYmEoMjU1LDI1NSwyNTUsMC4xKSIvPjwvc3ZnPg==')] opacity-20"></div>
        <div class="max-w-4xl mx-auto px-4 flex flex-col md:flex-row gap-12 items-center relative z-10">
            <div class="md:w-1/2">
                <h2 class="text-3xl font-bold mb-4">Start Your Fitness Journey</h2>
                <p class="text-primary-100 mb-8">Ready to transform your body and mind? Get in touch for a free consultation and personalized plan.</p>
                <div class="space-y-4">
                    <div class="flex items-center gap-3">
                        <div class="p-2 bg-primary-500 rounded-lg"><i data-lucide="mail" class="h-5 w-5"></i></div>
                        <span>hello@fitlifepro.com</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <div class="p-2 bg-primary-500 rounded-lg"><i data-lucide="map-pin" class="h-5 w-5"></i></div>
                        <span>123 Fitness Street, Wellness City</span>
                    </div>
                    <div class="flex items-center gap-3">
                        <div class="p-2 bg-primary-500 rounded-lg"><i data-lucide="phone" class="h-5 w-5"></i></div>
                        <span>+1 (555) 123-FITNESS</span>
                    </div>
                </div>
            </div>
            <div class="md:w-1/2 w-full bg-white dark:bg-gray-900 text-gray-900 dark:text-gray-100 p-8 rounded-2xl shadow-2xl">
                <form onsubmit="handleContact(event)" class="space-y-4">
                    <div>
                        <label class="block text-sm font-medium mb-1">Name</label>
                        <input type="text" required class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-700 bg-gray-50 dark:bg-gray-800 focus:ring-2 focus:ring-primary-500 outline-none transition-all">
                    </div>
                    <div>
                        <label class="block text-sm font-medium mb-1">Email</label>
                        <input type="email" required class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-700 bg-gray-50 dark:bg-gray-800 focus:ring-2 focus:ring-primary-500 outline-none transition-all">
                    </div>
                    <div>
                        <label class="block text-sm font-medium mb-1">Fitness Goals</label>
                        <select class="w-full px-4 py-2 rounded-lg border border-gray-300 dark:border-gray-700 bg-gray-50 dark:bg-gray-800 focus:ring-2 focus:ring-primary-500 outline-none transition-all">
                            <option>Weight Loss</option>
                            <option>Muscle Gain</option>
                            <option>Endurance Training</option>
                            <option>General Fitness</option>
                        </select>
                    </div>
                    <button type="submit" class="btn-glow w-full bg-primary-600 text-white py-3 rounded-lg font-bold hover:bg-primary-700 transition-colors">Get Free Consultation</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-gray-400 py-12 border-t border-gray-800">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <div class="flex items-center justify-center gap-2 mb-4">
                <i data-lucide="dumbbell" class="h-6 w-6 text-primary-500"></i>
                <span class="text-white font-bold text-lg">FitLife Pro</span>
            </div>
            <p class="mb-8">Transform your body, transform your life.</p>
            <div class="flex justify-center gap-6 mb-8">
                <a href="#" class="hover:text-white transition-colors transform hover:scale-110"><i data-lucide="instagram"></i></a>
                <a href="#" class="hover:text-white transition-colors transform hover:scale-110"><i data-lucide="facebook"></i></a>
                <a href="#" class="hover:text-white transition-colors transform hover:scale-110"><i data-lucide="twitter"></i></a>
                <a href="#" class="hover:text-white transition-colors transform hover:scale-110"><i data-lucide="youtube"></i></a>
            </div>
            <p class="text-sm text-gray-600">&copy; 2024 FitLife Pro. All rights reserved.</p>
        </div>
    </footer>

    <!-- JavaScript Logic (same as original with minor theme adjustments) -->
    <script>
        // Initialize icons and preloader
        lucide.createIcons();
        
        window.addEventListener('load', function() {
            setTimeout(() => {
                document.getElementById('preloader').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('preloader').style.display = 'none';
                }, 500);
            }, 1000);
        });

        // Theme Logic
        const html = document.documentElement;
        const toggleBtns = [document.getElementById('theme-toggle'), document.getElementById('theme-toggle-mobile')];
        
        function initTheme() {
            if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
                html.classList.add('dark');
            } else {
                html.classList.remove('dark');
            }
        }
        initTheme();

        toggleBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                html.classList.toggle('dark');
                localStorage.theme = html.classList.contains('dark') ? 'dark' : 'light';
            });
        });

        // Scroll Progress Bar
        window.onscroll = function() {
            let winScroll = document.body.scrollTop || document.documentElement.scrollTop;
            let height = document.documentElement.scrollHeight - document.documentElement.clientHeight;
            let scrolled = (winScroll / height) * 100;
            document.getElementById("scroll-progress").style.width = scrolled + "%";
            
            const nav = document.getElementById('navbar');
            if (winScroll > 50) {
                nav.classList.add('shadow-md');
            } else {
                nav.classList.remove('shadow-md');
            }
        };

        // Mobile Menu
        function toggleMobileMenu() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        }

        document.getElementById('mobile-menu-btn').addEventListener('click', toggleMobileMenu);

        // Scroll to Section
        function scrollToSection(id) {
            document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
        }

        // Animated Stats Counter
        const observerOptions = { threshold: 0.5 };
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const counters = entry.target.querySelectorAll('.count-up');
                    counters.forEach(counter => {
                        const target = +counter.getAttribute('data-target');
                        const duration = 2000;
                        const increment = target / (duration / 16);
                        
                        let current = 0;
                        const updateCount = () => {
                            current += increment;
                            if (current < target) {
                                counter.innerText = Math.ceil(current);
                                requestAnimationFrame(updateCount);
                            } else {
                                counter.innerText = target + (target > 100 ? '+' : '');
                            }
                        };
                        updateCount();
                    });
                    statsObserver.unobserve(entry.target);
                }
            });
        }, observerOptions);
        
        statsObserver.observe(document.getElementById('stats'));

        // Pricing Toggle
        let isYearly = false;
        function toggleBilling() {
            isYearly = !isYearly;
            const toggleCircle = document.getElementById('toggle-circle');
            const toggleBtn = document.getElementById('billing-toggle');
            
            toggleCircle.style.transform = isYearly ? 'translateX(24px)' : 'translateX(0)';
            toggleBtn.classList.toggle('bg-primary-500', isYearly);
            toggleBtn.classList.toggle('bg-gray-300', !isYearly);

            document.querySelectorAll('.price-amount').forEach(el => {
                const newVal = isYearly ? el.getAttribute('data-yearly') : el.getAttribute('data-monthly');
                el.style.opacity = 0;
                setTimeout(() => {
                    el.textContent = newVal;
                    el.style.opacity = 1;
                }, 200);
            });
        }

        // FAQ Accordion
        function toggleAccordion(button) {
            const content = button.nextElementSibling;
            const icon = button.querySelector('i');
            
            content.classList.toggle('hidden');
            icon.style.transform = content.classList.contains('hidden') ? 'rotate(0deg)' : 'rotate(180deg)';
        }

        // Contact Form
        function handleContact(e) {
            e.preventDefault();
            const btn = e.target.querySelector('button');
            const oldText = btn.innerText;
            btn.innerText = 'Sending...';
            btn.disabled = true;
            
            setTimeout(() => {
                btn.innerText = oldText;
                btn.disabled = false;
                e.target.reset();
                alert('Thank you! We will contact you within 24 hours to schedule your free consultation.');
            }, 1500);
        }
    </script>
</body>
</html>
