<script>
    let isMenuOpen = false;
    const toggleMenu = () => isMenuOpen = !isMenuOpen;
</script>

<header class="fixed w-full top-0 z-50 bg-white/80 backdrop-blur-md border-b border-gray-100 shadow-sm">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex items-center justify-between h-16">
      <!-- Logo -->
      <div class="flex items-center gap-3">
        <svg width="32" height="32" viewBox="0 0 24 24" class="text-red-500">
          <path d="M2 17L22 17L19 7L5 7L2 17Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <circle cx="7" cy="19" r="2" fill="currentColor"/>
          <circle cx="17" cy="19" r="2" fill="currentColor"/>
        </svg>
        <span class="text-2xl font-bold bg-gradient-to-r from-red-500 to-orange-500 bg-clip-text text-transparent">HeatMap</span>
      </div>

      <!-- Desktop Nav -->
      <nav class="hidden md:flex space-x-8">
        <a href="/" class="text-gray-700 font-medium hover:text-red-500 transition-colors">Home</a>
        <a href="/marketplace" class="text-gray-700 font-medium hover:text-red-500 transition-colors">Marketplace</a>
        <a href="/map" class="text-gray-700 font-medium hover:text-red-500 transition-colors">Meetup Map</a>
        <a href="/messages" class="text-gray-700 font-medium hover:text-red-500 transition-colors">Messages</a>
        <a href="/profile" class="text-gray-700 font-medium hover:text-red-500 transition-colors">Profile</a>
      </nav>

      <!-- Mobile Button -->
      <button class="md:hidden" on:click={toggleMenu}>
        {#if isMenuOpen}
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path d="M6 18L18 6M6 6l12 12" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"/>
          </svg>
        {:else}
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path d="M4 6h16M4 12h16M4 18h16" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"/>
          </svg>
        {/if}
      </button>
    </div>
  </div>

  <!-- Mobile Menu -->
  {#if isMenuOpen}
    <div class="md:hidden bg-white/95 backdrop-blur-md">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a href="/" class="block px-3 py-2 text-base font-medium text-gray-700 hover:text-red-500 hover:bg-gray-50 rounded-md">Home</a>
        <a href="/marketplace" class="block px-3 py-2 text-base font-medium text-gray-700 hover:text-red-500 hover:bg-gray-50 rounded-md">Marketplace</a>
        <a href="/map" class="block px-3 py-2 text-base font-medium text-gray-700 hover:text-red-500 hover:bg-gray-50 rounded-md">Meetup Map</a>
        <a href="/messages" class="block px-3 py-2 text-base font-medium text-gray-700 hover:text-red-500 hover:bg-gray-50 rounded-md">Messages</a>
        <a href="/profile" class="block px-3 py-2 text-base font-medium text-gray-700 hover:text-red-500 hover:bg-gray-50 rounded-md">Profile</a>
      </div>
    </div>
  {/if}
</header>
