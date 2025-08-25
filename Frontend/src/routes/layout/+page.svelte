<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SneakerConnect - Connect. Trade. Collect.</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap');
        
        * {
            font-family: 'Inter', sans-serif;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #FFD700 0%, #FFA500 15%, #FF6347 30%, #DC143C 40%, #1a1a1a 60%, #0a0a0a 100%);
        }
        
        .glass-effect {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 215, 0, 0.2);
        }
        
        .glow-effect {
            box-shadow: 0 0 30px rgba(255, 215, 0, 0.4);
        }
        
        .floating-animation {
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(2deg); }
        }
        
        .pulse-glow {
            animation: pulse-glow 2s ease-in-out infinite alternate;
        }
        
        @keyframes pulse-glow {
            from { box-shadow: 0 0 20px rgba(255, 215, 0, 0.5); }
            to { box-shadow: 0 0 40px rgba(255, 69, 0, 0.8); }
        }
        
        .stat-card {
            transition: all 0.3s ease;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(255, 215, 0, 0.3);
        }
        
        .cursor-trail {
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(255, 215, 0, 0.8) 0%, rgba(255, 69, 0, 0.6) 40%, transparent 70%);
            transform: translate(-50%, -50%);
            transition: all 0.1s ease-out;
        }
        
        .cursor-glow {
            position: fixed;
            pointer-events: none;
            z-index: 9998;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(255, 215, 0, 0.4) 0%, rgba(255, 69, 0, 0.2) 50%, transparent 70%);
            transform: translate(-50%, -50%);
            transition: all 0.15s ease-out;
            filter: blur(8px);
        }
        
        .sneaker-particle {
            position: fixed;
            pointer-events: none;
            z-index: 9997;
            font-size: 12px;
            opacity: 0;
            transform: translate(-50%, -50%);
            animation: particle-float 2s ease-out forwards;
        }
        
        @keyframes particle-float {
            0% {
                opacity: 1;
                transform: translate(-50%, -50%) scale(0.5);
            }
            50% {
                opacity: 0.8;
                transform: translate(-50%, -70px) scale(1) rotate(180deg);
            }
            100% {
                opacity: 0;
                transform: translate(-50%, -120px) scale(0.3) rotate(360deg);
            }
        }
        
        body {
            cursor: none;
        }
        
        button, a, .clickable {
            cursor: none;
        }
        
        .cursor-hover {
            transform: translate(-50%, -50%) scale(1.5);
            background: radial-gradient(circle, rgba(255, 255, 255, 0.9) 0%, rgba(255, 215, 0, 0.7) 40%, transparent 70%);
        }
        
        .cursor-glow-hover {
            transform: translate(-50%, -50%) scale(2);
            background: radial-gradient(circle, rgba(255, 215, 0, 0.6) 0%, rgba(255, 69, 0, 0.3) 50%, transparent 70%);
        }
    </style>
</head>

<body class="gradient-bg min-h-screen text-white overflow-x-hidden">
    <!-- Custom Cursor Elements -->
    <div id="cursor-trail" class="cursor-trail"></div>
    <div id="cursor-glow" class="cursor-glow"></div>
    <!-- Navigation -->
    <nav class="relative z-50 px-6 py-4 border-2">
        <div class="max-w-7xl mx-auto flex items-center justify-between">
            <div class="flex items-center space-x-2">
                <div class="w-8 h-8 bg-gradient-to-r from-yellow-400 to-red-500 rounded-lg flex items-center justify-center">
                    <svg class="w-5 h-5 text-white" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                    </svg>
                </div>
                <span class="text-xl font-bold">SneakerConnect</span>
            </div>
            
            <div class="hidden md:flex items-center space-x-8">
                <a href="#features" class="text-gray-300 hover:text-white transition-colors">Features</a>
                <a href="#community" class="text-gray-300 hover:text-white transition-colors">Community</a>
                <a href="#marketplace" class="text-gray-300 hover:text-white transition-colors">Marketplace</a>
                <a href="#about" class="text-gray-300 hover:text-white transition-colors">About</a>
            </div>
            
            <div class="flex items-center space-x-4">
                <button class="text-gray-300 hover:text-white transition-colors">Login</button>
                <button class="bg-gradient-to-r from-yellow-500 to-red-500 px-6 py-2 rounded-lg font-semibold hover:from-yellow-400 hover:to-red-400 transition-all duration-300 transform hover:scale-105">
                    Join Now
                </button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <main class="relative">
        <div class="max-w-7xl mx-auto px-6 py-20 text-center">
            <div class="mb-8 animate-pulse">
                <span class="inline-block px-4 py-2 bg-gradient-to-r from-yellow-500/20 to-red-600/20 rounded-full text-yellow-300 font-medium border border-yellow-500/30">
                    The Future of Sneaker Trading
                </span>
            </div>
            
            <h1 class="text-5xl md:text-7xl font-bold mb-6 leading-tight">
                Connect with
                <br>
                <span class="text-transparent bg-clip-text bg-gradient-to-r from-yellow-400 to-red-500">
                    Sneakerheads
                </span>
                <br>
                Worldwide
            </h1>
            
            <p class="text-xl text-gray-300 mb-12 max-w-3xl mx-auto leading-relaxed">
                Join the ultimate community for sneaker enthusiasts. Buy, sell, trade, and connect with fellow collectors. 
                Discover rare finds, showcase your collection, and meet up safely with integrated location features.
            </p>
            
            <button class="bg-gradient-to-r from-yellow-500 to-red-500 px-12 py-4 rounded-xl text-lg font-semibold hover:from-yellow-400 hover:to-red-400 transition-all duration-300 transform hover:scale-105 glow-effect pulse-glow mb-8">
                Get Started
                <svg class="inline-block ml-2 w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 8l4 4m0 0l-4 4m4-4H3"/>
                </svg>
            </button>
            
            <div class="flex items-center justify-center space-x-2 text-gray-400">
                <span>Trusted by sneakerheads</span>
                <div class="flex text-yellow-400">
                    <span>★★★★★</span>
                </div>
                <span class="font-semibold">4.9</span>
                <span class="text-yellow-400">PH</span>
            </div>
        </div>

        <!-- Dashboard Preview -->
        <div class="max-w-6xl mx-auto px-6 mb-20">
            <div class="glass-effect rounded-3xl p-8 floating-animation">
                <div class="bg-gradient-to-br from-gray-900 to-gray-800 rounded-2xl overflow-hidden">
                    <!-- Mock Dashboard Header -->
                    <div class="flex items-center justify-between p-6 border-b border-gray-700">
                        <div class="flex items-center space-x-4">
                            <div class="w-8 h-8 bg-gradient-to-r from-yellow-400 to-red-500 rounded-lg"></div>
                            <h3 class="text-xl font-semibold">Main Dashboard</h3>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="w-8 h-8 bg-gray-700 rounded-full"></div>
                            <div class="w-6 h-6 bg-gray-700 rounded"></div>
                        </div>
                    </div>
                    
                    <!-- Mock Dashboard Content -->
                    <div class="p-6">
                        <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
                            <!-- Collection Stats -->
                            <div class="lg:col-span-2">
                                <div class="flex items-center justify-between mb-4">
                                    <h4 class="text-lg font-semibold">Collection Value</h4>
                                    <div class="flex space-x-2 text-sm">
                                        <span class="px-2 py-1 bg-gray-700 rounded">1D</span>
                                        <span class="px-2 py-1 bg-green-600 rounded">7D</span>
                                        <span class="px-2 py-1 bg-gray-700 rounded">1M</span>
                                        <span class="px-2 py-1 bg-gray-700 rounded">1Y</span>
                                    </div>
                                </div>
                                <div class="text-3xl font-bold mb-2">₱247,350 <span class="text-yellow-400 text-lg">+12.3%</span></div>
                                <!-- Mock Chart -->
                                <div class="h-32 bg-gradient-to-r from-yellow-500/20 to-red-600/20 rounded-lg flex items-end justify-center space-x-1 p-4">
                                    <div class="w-2 bg-yellow-400 rounded-t" style="height: 40%"></div>
                                    <div class="w-2 bg-yellow-400 rounded-t" style="height: 60%"></div>
                                    <div class="w-2 bg-yellow-500 rounded-t" style="height: 80%"></div>
                                    <div class="w-2 bg-orange-500 rounded-t" style="height: 70%"></div>
                                    <div class="w-2 bg-orange-400 rounded-t" style="height: 90%"></div>
                                    <div class="w-2 bg-red-500 rounded-t" style="height: 100%"></div>
                                    <div class="w-2 bg-red-400 rounded-t" style="height: 85%"></div>
                                </div>
                            </div>
                            
                            <!-- Quick Actions -->
                            <div class="space-y-4">
                                <div class="bg-gradient-to-r from-yellow-600 to-red-600 p-4 rounded-xl">
                                    <h5 class="font-semibold mb-2">Quick Trade</h5>
                                    <div class="space-y-2">
                                        <div class="flex items-center justify-between text-sm">
                                            <span>0.0018652</span>
                                            <span>🔥 Jordan 1</span>
                                        </div>
                                        <div class="flex items-center justify-between text-sm">
                                            <span>Balance: 0.01054262 SNKR</span>
                                        </div>
                                        <div class="w-full bg-white/20 rounded p-2 text-center text-sm">
                                            ⇄ ₱45,604
                                        </div>
                                        <div class="flex items-center justify-between text-sm">
                                            <span>Balance: 500 HYPE</span>
                                            <span>💎 Yeezy 350</span>
                                        </div>
                                        <button class="w-full bg-white/20 hover:bg-white/30 rounded p-2 text-sm transition-colors">
                                            Execute Trade ↗
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Recent Activity -->
                        <div class="mt-6 grid grid-cols-1 lg:grid-cols-2 gap-6">
                            <div>
                                <h4 class="text-lg font-semibold mb-4">Recent Sneakers</h4>
                                <div class="space-y-3">
                                    <div class="flex items-center justify-between p-3 bg-gray-800 rounded-lg">
                                        <div class="flex items-center space-x-3">
                                            <div class="w-10 h-10 bg-red-600 rounded-lg"></div>
                                            <div>
                                                <div class="font-medium">Air Jordan 1 Retro</div>
                                                <div class="text-sm text-gray-400">Chicago Colorway</div>
                                            </div>
                                        </div>
                                        <div class="text-right">
                                            <div class="font-semibold">₱25,500</div>
                                            <div class="text-sm text-yellow-400">+5.2%</div>
                                        </div>
                                    </div>
                                    <div class="flex items-center justify-between p-3 bg-gray-800 rounded-lg">
                                        <div class="flex items-center space-x-3">
                                            <div class="w-10 h-10 bg-purple-600 rounded-lg"></div>
                                            <div>
                                                <div class="font-medium">Travis Scott x Nike</div>
                                                <div class="text-sm text-gray-400">Fragment Low</div>
                                            </div>
                                        </div>
                                        <div class="text-right">
                                            <div class="font-semibold">₱36,000</div>
                                            <div class="text-sm text-red-400">-2.1%</div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            
                            <div>
                                <h4 class="text-lg font-semibold mb-4">Community Activity</h4>
                                <div class="space-y-3">
                                    <div class="p-3 bg-gray-800 rounded-lg">
                                        <div class="flex items-center space-x-2 mb-2">
                                            <div class="w-6 h-6 bg-blue-500 rounded-full"></div>
                                            <span class="text-sm font-medium">@sneaker_king</span>
                                            <span class="text-xs text-gray-400">posted</span>
                                        </div>
                                        <p class="text-sm text-gray-300">Just copped the new Dunk Lows! 🔥</p>
                                    </div>
                                    <div class="p-3 bg-gray-800 rounded-lg">
                                        <div class="flex items-center space-x-2 mb-2">
                                            <div class="w-6 h-6 bg-green-500 rounded-full"></div>
                                            <span class="text-sm font-medium">@hypebeast23</span>
                                            <span class="text-xs text-gray-400">sold</span>
                                        </div>
                                        <p class="text-sm text-gray-300">Yeezys moved fast! Thanks for the smooth trade ✨</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Features Section -->
    <section class="py-20 px-6" id="features">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <h2 class="text-4xl font-bold mb-4">Everything You Need</h2>
                <p class="text-xl text-gray-300">Built for the modern sneakerhead community</p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="stat-card glass-effect p-6 rounded-2xl text-center">
                    <div class="w-12 h-12 bg-gradient-to-r from-blue-500 to-purple-600 rounded-xl mx-auto mb-4 flex items-center justify-center">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197m13.5-9a2.5 2.5 0 11-5 0 2.5 2.5 0 015 0z"/>
                        </svg>
                    </div>
                    <h3 class="font-semibold text-lg mb-2">Social Profiles</h3>
                    <p class="text-gray-400 text-sm">Showcase your collection and connect with fellow sneaker enthusiasts</p>
                </div>
                
                <div class="stat-card glass-effect p-6 rounded-2xl text-center">
                    <div class="w-12 h-12 bg-gradient-to-r from-yellow-500 to-red-600 rounded-xl mx-auto mb-4 flex items-center justify-center">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"/>
                        </svg>
                    </div>
                    <h3 class="font-semibold text-lg mb-2">Secure Trading</h3>
                    <p class="text-gray-400 text-sm">Safe and secure marketplace with verified sellers and buyers</p>
                </div>
                
                <div class="stat-card glass-effect p-6 rounded-2xl text-center">
                    <div class="w-12 h-12 bg-gradient-to-r from-purple-500 to-pink-600 rounded-xl mx-auto mb-4 flex items-center justify-center">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"/>
                        </svg>
                    </div>
                    <h3 class="font-semibold text-lg mb-2">Direct Messaging</h3>
                    <p class="text-gray-400 text-sm">Chat directly with other users to negotiate deals and build relationships</p>
                </div>
                
                <div class="stat-card glass-effect p-6 rounded-2xl text-center">
                    <div class="w-12 h-12 bg-gradient-to-r from-orange-500 to-red-600 rounded-xl mx-auto mb-4 flex items-center justify-center">
                        <svg class="w-6 h-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"/>
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"/>
                        </svg>
                    </div>
                    <h3 class="font-semibold text-lg mb-2">Meet-up Maps</h3>
                    <p class="text-gray-400 text-sm">Integrated location features for safe in-person trades and meetups</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="py-20 px-6 bg-black/20">
        <div class="max-w-4xl mx-auto text-center">
            <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
                <div>
                    <div class="text-4xl font-bold text-yellow-400 mb-2">50K+</div>
                    <div class="text-gray-300">Active Users</div>
                </div>
                <div>
                    <div class="text-4xl font-bold text-yellow-400 mb-2">2M+</div>
                    <div class="text-gray-300">Sneakers Listed</div>
                </div>
                <div>
                    <div class="text-4xl font-bold text-yellow-400 mb-2">₱1.5B+</div>
                    <div class="text-gray-300">Total Traded</div>
                </div>
                <div>
                    <div class="text-4xl font-bold text-yellow-400 mb-2">99.8%</div>
                    <div class="text-gray-300">Success Rate</div>
                </div>
            </div>
        </div>
    </section>

    <!-- CTA Section -->
    <section class="py-20 px-6">
        <div class="max-w-4xl mx-auto text-center">
            <h2 class="text-4xl font-bold mb-6">Ready to Join the Community?</h2>
            <p class="text-xl text-gray-300 mb-8">Connect with sneakerheads worldwide and take your collection to the next level.</p>
            <div class="flex flex-col sm:flex-row items-center justify-center space-y-4 sm:space-y-0 sm:space-x-4">
                <button class="bg-gradient-to-r from-green-500 to-emerald-600 px-8 py-4 rounded-xl text-lg font-semibold hover:from-green-400 hover:to-emerald-500 transition-all duration-300 transform hover:scale-105 glow-effect">
                    Get Started Free
                </button>
                <button class="border border-gray-600 px-8 py-4 rounded-xl text-lg font-semibold hover:border-green-500 hover:text-green-400 transition-all duration-300">
                    Learn More
                </button>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-gray-800 py-12 px-6">
        <div class="max-w-7xl mx-auto">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-2">
                    <div class="w-8 h-8 bg-gradient-to-r from-green-400 to-emerald-500 rounded-lg flex items-center justify-center">
                        <svg class="w-5 h-5 text-white" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                        </svg>
                    </div>
                    <span class="text-xl font-bold">SneakerConnect</span>
                </div>
                
                <div class="text-gray-400 text-sm">
                    © 2025 SneakerConnect. All rights reserved.
                </div>
            </div>
        </div>
    </footer>

    <script>
        // Custom Cursor System
        let mouseX = 0, mouseY = 0;
        let trailX = 0, trailY = 0;
        let glowX = 0, glowY = 0;
        
        const cursorTrail = document.getElementById('cursor-trail');
        const cursorGlow = document.getElementById('cursor-glow');
        
        // Sneaker emojis for particles
        const sneakerEmojis = ['👟', '👠', '🥿', '👡', '🦶', '💎', '🔥', '⚡', '✨', '🌟'];
        
        // Track mouse movement
        document.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
            
            // Create sneaker particles randomly
            if (Math.random() < 0.05) { // 5% chance per mouse move
                createSneakerParticle(mouseX, mouseY);
            }
        });
        
        // Create floating sneaker particles
        function createSneakerParticle(x, y) {
            const particle = document.createElement('div');
            particle.className = 'sneaker-particle';
            particle.textContent = sneakerEmojis[Math.floor(Math.random() * sneakerEmojis.length)];
            particle.style.left = x + 'px';
            particle.style.top = y + 'px';
            
            // Add some randomness to the starting position
            const randomOffset = (Math.random() - 0.5) * 40;
            particle.style.transform = `translate(-50%, -50%) translateX(${randomOffset}px)`;
            
            document.body.appendChild(particle);
            
            // Remove particle after animation
            setTimeout(() => {
                particle.remove();
            }, 2000);
        }
        
        // Smooth cursor following animation
        function animateCursor() {
            // Trail follows with slight delay
            trailX += (mouseX - trailX) * 0.3;
            trailY += (mouseY - trailY) * 0.3;
            
            // Glow follows with more delay
            glowX += (mouseX - glowX) * 0.15;
            glowY += (mouseY - glowY) * 0.15;
            
            cursorTrail.style.left = trailX + 'px';
            cursorTrail.style.top = trailY + 'px';
            
            cursorGlow.style.left = glowX + 'px';
            cursorGlow.style.top = glowY + 'px';
            
            requestAnimationFrame(animateCursor);
        }
        
        // Start animation
        animateCursor();
        
        // Add hover effects for interactive elements
        const interactiveElements = document.querySelectorAll('button, a, .stat-card');
        
        interactiveElements.forEach(element => {
            element.addEventListener('mouseenter', () => {
                cursorTrail.classList.add('cursor-hover');
                cursorGlow.classList.add('cursor-glow-hover');
                
                // Create burst of particles on hover
                for (let i = 0; i < 3; i++) {
                    setTimeout(() => {
                        createSneakerParticle(mouseX + (Math.random() - 0.5) * 30, mouseY + (Math.random() - 0.5) * 30);
                    }, i * 50);
                }
            });
            
            element.addEventListener('mouseleave', () => {
                cursorTrail.classList.remove('cursor-hover');
                cursorGlow.classList.remove('cursor-glow-hover');
            });
        });
        
        // Add smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Add interactive effects
        document.addEventListener('mousemove', (e) => {
            const cards = document.querySelectorAll('.stat-card');
            cards.forEach(card => {
                const rect = card.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                
                if (x >= 0 && x <= rect.width && y >= 0 && y <= rect.height) {
                    const xPercent = (x / rect.width - 0.5) * 2;
                    const yPercent = (y / rect.height - 0.5) * 2;
                    card.style.transform = `perspective(1000px) rotateX(${yPercent * 5}deg) rotateY(${xPercent * 5}deg) translateY(-5px)`;
                } else {
                    card.style.transform = '';
                }
            });
        });
    </script>
</body>
</html>


