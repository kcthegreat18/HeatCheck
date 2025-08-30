<script>
import Header from '../lib/components/header.svelte';
</script>


<main class="gradient-bg min-h-screen text-white overflow-x-hidden">
    <Header />
    
    <section id="about" class="flex flex-col md:flex-row items-center justify-between">

        <!-- Left Side: Text Content -->
        <div class="flex flex-col border- border-amber-200 px-6 md:px-12 lg:px-24 py-12 md:py-24 lg:py-32 text-center md:text-left gap-10">
            <h1 class="font-michroma text-6xl md:text-6xl lg:text-6 xl mb-4 leading-tight"> 
            <span class="font-bold">The Place <br /> </span>
           <span class="font-bold">For </span> <span class="font-game text-8xl bg-gradient-to-r from-emerald-600 to-green-400 bg-clip-text text-transparent"> Filipino <br/> </span>
           <span class="font-bold">Sneaker Heads<br /> </span>
           </h1>

           <div class="flex flex-row gap-5 font-tech text-lg border-0 max-w-3xl mx-auto relative">
            <!-- Decorative rectangle -->
            <div class="absolute left-0 top-0 w-2 h-full bg-gradient-to-b from-emerald-500 to-green-700"></div>
            
            <!-- Added padding-left to create space for the rectangle -->
            <h2 class="font-tech text-2xl pl-6 tracking-normal"><span class="font-bold">Join the ultimate community for sneaker enthusiasts in the Philippines. <br/> </span> 
            Buy, sell, trade, and connect with fellow collectors. Discover rare finds, showcase your collection, 
            message with fellow sneakerheads, and meet up safely with integrated location features.
            </h2>
           </div>

           <button class="flex transition-all duration-300 hover:scale-102 hover:text-gray-200 mt-3">
            <a href="#features" class="font-tech text-lg bg-gradient-to-r from-green-600 to-emerald-700 px-6 py-2 rounded-lg font-semibold hover:from-green-500 hover:to-emerald-500 ">
                Explore Features
            </a>
           </button>
           
        </div>

      
        <!-- Right Side (Image) -->
        <div class="mt-10 mr-50 md:mt-0 md:ml-12 relative group">
            <!-- Outer glow effect -->
            <div class="absolute -inset-2 bg-gradient-to-r from-emerald-600 to-green-800 rounded-3xl blur opacity-25 group-hover:opacity-75 transition duration-1000"></div>
                
            <!-- Card frame -->
            <div class="relative p-6 bg-gradient-to-b from-gray-800/80 to-gray-900/80 rounded-2xl border border-emerald-500/30 backdrop-blur-sm">
            <!-- Image container -->
            <div class="relative overflow-hidden rounded-xl">
            <img
            src="/pinegreen.png"
            alt="Featured Sneaker"
            class="w-[550px] md:w-[600px] transform transition duration-500 hover:scale-105"
            />
            <!-- Shine effect overlay -->
            <div class="absolute inset-0 bg-gradient-to-tr from-white/5 to-transparent"></div>
            </div>
            
            <!-- Optional: Card bottom accent -->
            <div class="h-1 w-1/3 mx-auto mt-3 bg-gradient-to-r from-transparent via-emerald-500/50 to-transparent rounded-full"></div>
            </div>
        </div>

    </section>

    <!-- Features Section -->
    <section class="py-20 px-6" id="features">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <h2 class="text-4xl font-bold mb-4 font-michroma">Everything You Need</h2>
                <p class="text-xl text-gray-300 font-tech">Built for the modern sneakerhead community</p>
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

</main>


<style>
        .gradient-bg {
            background: linear-gradient(135deg, #1b2a1b 20%, #131a13 40%, #0c100c 70%, #001400 100%);
        }

        .glass-effect {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border: 1px solid #053805;
        }
        

        .stat-card {
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px #053805;
        }

        
</style>    