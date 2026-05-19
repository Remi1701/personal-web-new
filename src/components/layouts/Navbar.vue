<template>
  <nav>
    <div class="nav-bar">
      <i class="bx bx-menu sidebarOpen"></i>
      <span class="logo navLogo"><a href="#"><img src="/favicon.ico" alt="Remi"></a></span>

      <div class="menu">
        <div class="logo-toggle">
          <span class="logo"><a href="#"><img src="/favicon.ico" alt="Remi"></a></span>
          <i class="bx bx-x siderbarClose"></i>
        </div>

        <ul class="nav-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#portfolio">Portfolio</a></li>
          <li><a href="#stacks">Stacks</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    loadScript() { 
      const body = document.querySelector("body");
      const nav = document.querySelector("nav");
      const sidebarOpen = document.querySelector(".sidebarOpen");
      const siderbarClose = document.querySelector(".siderbarClose");

      // Always use dark mode
      body.classList.add("dark");
      
      sidebarOpen.addEventListener("click", () => {
        nav.classList.add("active");
      });

      body.addEventListener("click", (e) => {
        let clickedElm = e.target;

        if (!clickedElm.classList.contains("sidebarOpen") && !clickedElm.classList.contains("menu")) {
          nav.classList.remove("active");
        }
      });
    }
  },
  mounted() {
    this.$nextTick(function () {
      this.loadScript();
    });
    // Force dark mode on mount
    document.body.classList.add("dark");
  }
}
</script>