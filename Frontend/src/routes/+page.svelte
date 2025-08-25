<script>
import Header from '../lib/components/header.svelte';
</script>


<main class="gradient-bg min-h-screen text-white overflow-x-hidden">
    <Header />
    
    <section id="about" class="flex flex-col md:flex-row items-center justify-between">

        <!-- Left Side: Text Content -->
        <div class="flex flex-col border-0 border-amber-200 px-6 md:px-12 lg:px-24 py-12 md:py-24 lg:py-32 text-center md:text-left gap-4">
            <h1 class="font-michroma text-5xl md:text-6xl lg:text-6 xl mb-4 leading-tight"> 
            <span class="font-bold">The Place <br /> </span>
           <span class="font-bold">For </span> <span class="font-game text-8xl bg-gradient-to-r from-emerald-600 to-green-400 bg-clip-text text-transparent"> Filipino <br/> </span>
           <span class="font-bold">Sneaker Heads<br /> </span>
           </h1>

           <div class="flex flex-col gap-5 font-tech text-lg">
            <h2 class="font-tech text-3xl">Join the ultimate community for sneaker enthusiasts in the Philippines. <br/> </h2>

            Buy, sell, trade, and connect with fellow collectors. Discover rare finds, showcase your collection, <br/>
            message with fellow sneakerheads, and meet up safely with integrated location features.
           </div>

           <button class="flex transition-all duration-300 transform hover:scale-102 hover:text-gray-200 mt-3">
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


</main>


<style>
        .gradient-bg {
            background: linear-gradient(135deg, #1b2a1b 20%, #131a13 40%, #0c100c 70%, #001400 100%);
        }
</style>    