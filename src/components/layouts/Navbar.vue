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
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Portfolio</a></li>
          <li><a href="#">Services</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </div>

      <div class="darkLight-searchBox">
        <div class="dark-light">
          <i class="bx bx-moon moon"></i>
          <i class="bx bx-sun sun"></i>
        </div>
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
      const modeToggle = document.querySelector(".dark-light");
      const searchToggle = document.querySelector(".searchToggle");
      const sidebarOpen = document.querySelector(".sidebarOpen");
      const siderbarClose = document.querySelector(".siderbarClose");

      let getMode = localStorage.getItem("mode");
      if (getMode && getMode === "dark-mode") {
        body.classList.add("dark");
      }
      modeToggle.addEventListener("click", () => {
        modeToggle.classList.toggle("active");
        body.classList.toggle("dark");
        if (!body.classList.contains("dark")) {
          localStorage.setItem("mode", "light-mode");
        } else {
          localStorage.setItem("mode", "dark-mode");
        }
      });
      searchToggle.addEventListener("click", () => {
        searchToggle.classList.toggle("active");
      });
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
  }
}
</script>