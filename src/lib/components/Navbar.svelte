<script>
  import { page } from '$app/stores';
  import { onMount } from 'svelte';

  import logo from "$lib/assets/logo.png";
  
  let isMenuOpen = $state(false);
  let isVisible = $state(true);
  let lastScrollY = $state(0);
  
  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function handleScroll() {
    const currentScrollY = window.scrollY;
    
    // Show navbar when scrolling up, hide when scrolling down
    if (currentScrollY < lastScrollY || currentScrollY < 100) {
      isVisible = true;
    } else if (currentScrollY > lastScrollY && currentScrollY > 100) {
      isVisible = false;
      isMenuOpen = false; // Close mobile menu when hiding
    }
    
    lastScrollY = currentScrollY;
  }

  onMount(() => {
    window.addEventListener('scroll', handleScroll);
    
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });
</script>

<nav class="navbar" class:hidden={!isVisible}>
  <div class="container">
    <div class="navbar-content">
      <!-- Logo -->
      <a href="/" class="logo">
        <img src={logo} alt="" class="logo-icon">
        <span class="logo-text">Boibrary</span>
      </a>

      <!-- Desktop Menu -->
      <div class="nav-links desktop-only">
        <a 
          href="/" 
          class="nav-link"
          class:active={$page.url.pathname === '/'}
        >
          Home
        </a>
        <a 
          href="/books" 
          class="nav-link"
          class:active={$page.url.pathname === '/books'}
        >
          Books
        </a>
        <a 
          href="/pricing" 
          class="nav-link"
          class:active={$page.url.pathname === '/pricing'}
        >
          Pricing
        </a>
        <a 
          href="/login" 
          class="nav-link"
        >
          Login
        </a>
      </div>

      <!-- Mobile Menu Button -->
      <button 
        class="mobile-menu-btn"
        onclick={toggleMenu}
      >
        ☰
      </button>
    </div>

    <!-- Mobile Menu -->
    {#if isMenuOpen}
      <div class="mobile-menu">
        <a href="/" class="nav-link">Home</a>
        <a href="/books" class="nav-link">Books</a>
        <a href="/pricing" class="nav-link">Pricing</a>
        <a href="/login" class="nav-link">Login</a>
      </div>
    {/if}
  </div>
</nav>

<style>
  .navbar {
    background: white;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    transition: transform 0.3s ease-in-out;
    transform: translateY(0);
  }

  .navbar.hidden {
    transform: translateY(-100%);
  }

  .navbar-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 0;
  }

  .logo {
    display: flex;
    align-items: center;
    gap: 8px;
    text-decoration: none;
  }

  .logo-icon {
    height: 40px;
    /* width: 28px; */
    transform: scale(1.25);
  }

  .logo-text {
    font-size: 24px;
    font-weight: 700;
    color: var(--orange-primary);
  }

  .nav-links {
    display: flex;
    gap: 32px;
  }

  .nav-link {
    color: var(--gray-700);
    text-decoration: none;
    font-weight: 500;
    transition: color 0.3s;
    padding: 8px 0;
  }

  .nav-link:hover,
  .nav-link.active {
    color: var(--orange-primary);
  }

  .mobile-menu-btn {
    display: none;
    background: none;
    border: none;
    font-size: 24px;
    cursor: pointer;
    color: var(--gray-700);
  }

  .mobile-menu {
    display: flex;
    flex-direction: column;
    gap: 16px;
    padding: 16px 0;
  }

  .desktop-only {
    display: flex;
  }

  @media (max-width: 768px) {
    .desktop-only {
      display: none;
    }

    .mobile-menu-btn {
      display: block;
    }
  }
</style>