<template>
  <!-- home section start -->
  <section class="home" id="home">
    <div class="max-width">
      <div class="home-content">
        <div class="text-1">Hello, my name is</div>
        <div class="text-2">Rassel Muhammad Indra</div>
        <div class="text-3">And I'm a <span class="typing"></span></div>
      </div>
    </div>
  </section>

  <!-- about section start -->
  <section class="about" id="about">
    <div class="max-width">
      <h2 class="title">About me</h2>
      <div class="about-content">
        <div class="about-text">
          <p>
            Greetings! I’m Rassel, a recent graduate of Software Engineering from <a href="https://smkwikrama.sch.id/" target="_blank">SMK Wikrama Bogor</a>.
            My strong fascination with technology drives me to continuously explore coding and its endless
            possibilities. Passionate about creating innovative software solutions, I’m fully committed to sharpening my
            skills and embracing new challenges in this fast-evolving field.
          </p>
          <a href="/CV - Rassel Muhammad Indra.pdf" download>Download CV</a>
        </div>
      </div>
    </div>
  </section>

  <!-- teams section start -->
  <section class="portfolio" id="portfolio">
    <div class="max-width">
      <h2 class="title" style="color: var(--title-color);">Portfolio</h2>
      <div class="portfolio-container">
        <!-- Year Filter Navigation -->
        <div class="year-filter">
          <div v-for="year in availableYears" :key="year" class="year-item" :class="{ active: selectedYear === year }"
            @click="selectedYear = year">
            {{ year }}
          </div>
        </div>
        <!-- Carousel -->
        <div class="carousel-wrapper">
          <div class="carousel owl-carousel">
          </div>
        </div>
        <div class="year-spacer"></div>
      </div>
    </div>
  </section>

  <!-- stacks section start -->
  <section class="stacks" id="stacks">
    <div class="max-width">
      <h2 class="title">Tech Stack</h2>
      <div class="serv-content">
        <div v-for="tech in techStack" :key="tech.id" class="card">
          <div class="box">
            <i :class="tech.icon"></i>
            <div class="text">{{ tech.name }}</div>
            <p>{{ tech.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- contact section start -->
  <section class="contact" id="contact">
    <div class="max-width">
      <h2 class="title" style="color: var(--title-color);">Contact me</h2>
      <div class="contact-content">
        <div class="column left">
          <div class="text">Get in Touch</div>
          <p>I'm always open to discussions, questions, or opportunities. Feel free to reach out via email or WhatsApp
            for any personal or business inquiries.</p>
          <div class="icons">
            <div class="row">
              <i class="fas fa-user"></i>
              <div class="info">
                <div class="head">Name</div>
                <div class="sub-title">Rassel Muhammad Indra</div>
              </div>
            </div>
            <div class="row">
              <i class="fas fa-map-marker-alt"></i>
              <div class="info">
                <div class="head">Address</div>
                <div class="sub-title">Ciawi, Bogor, Jawa Barat, Indonesia</div>
              </div>
            </div>
            <div class="row">
              <i class="fas fa-envelope"></i>
              <div class="info">
                <div class="head">Email</div>
                <div class="sub-title">rasselmuhamadindra@gmail.com</div>
              </div>
            </div>
            <div class="row">
              <i class="fas fa-phone"></i>
              <div class="info">
                <div class="head">Phone Number</div>
                <div class="sub-title">+62 882-9662-6382</div>
              </div>
            </div>
          </div>
          <div class="social-links">
            <a href="https://github.com/Remi1701" target="_blank" class="social-btn github-btn">
              <i class="fab fa-github"></i> GitHub
            </a>
            <a href="https://www.linkedin.com/in/rassel-muhammad-indra" target="_blank" class="social-btn linkedin-btn">
              <i class="fab fa-linkedin"></i> LinkedIn
            </a>
          </div>
        </div>
        <div class="column right">
          <div class="text">Message me</div>
          <form @submit.prevent="sendEmail">
            <div class="fields">
              <div class="field name">
                <input v-model="form.name" type="text" placeholder="Name" required />
              </div>
              <div class="field email">
                <input v-model="form.email" type="email" placeholder="Email" required />
              </div>
            </div>
            <div class="field">
              <input v-model="form.subject" type="text" placeholder="Subject" required />
            </div>
            <div class="field textarea">
              <textarea v-model="form.message" cols="30" rows="10" placeholder="Message.." required></textarea>
            </div>
            <div class="button-area">
              <button type="submit" :disabled="isSubmitting">{{ isSubmitting ? 'Sending...' : 'Send message' }}</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>

  <!-- footer section start -->
  <footer>
    <div class="footer-content">
      <p class="footer-text">Crafted by <a href="#home">Rassel Muhammad Indra</a></p>
      <p class="footer-divider">|</p>
      <p class="footer-text"><span class="far fa-copyright"></span> 2026 All rights reserved.</p>
    </div>
  </footer>
</template>
<script>
export default {
  data() {
    return {
      selectedYear: 2024,
      isSubmitting: false,
      form: {
        name: '',
        email: '',
        subject: '',
        message: ''
      },
      techStack: [
        { id: 1, name: "Frontend", icon: "fas fa-palette", description: "Vue.js, Laravel, HTML5, CSS3, JavaScript - Building responsive and interactive user interfaces" },
        { id: 2, name: "Backend", icon: "fas fa-server", description: "Laravel, C++, Python - Creating robust server-side applications and APIs" },
        { id: 3, name: "Database", icon: "fas fa-database", description: "MongoDB, MySQL, PostgreSQL - Managing and optimizing data storage solutions" },
        { id: 4, name: "Tools & DevOps", icon: "fas fa-tools", description: "Git, Docker, Vite, Webpack - Streamlining development workflow and deployment" },
        { id: 5, name: "Mobile", icon: "fas fa-mobile-alt", description: "Flutter - Developing cross-platform mobile applications" },
        { id: 6, name: "Cloud", icon: "fas fa-cloud", description: "AWS, Vercel - Deploying and managing cloud-based solutions" }
      ],
      portfolioProjects: [
        { id: 1, title: "1st Personal Website CV", description: "My first ever self-made website with pure HTML and CSS", image: "/portfolio-1.png", year: 2022 },
        { id: 2, title: "2nd Personal Website", description: "My second personal website with better knowledge on CSS animation", image: "/portfolio-2.png", year: 2022 },
        { id: 3, title: "Caferatu", description: "A coffee shop management system with orders and flexible menu inventory built with PHP", image: "/portfolio-3.png", year: 2023 },
        { id: 4, title: "Flutter Personal Website", description: "A personal website built with Flutter", image: "/portfolio-4.png", year: 2024 },
      ]
    }
  },
  computed: {
    availableYears() {
      const years = [...new Set(this.portfolioProjects.map(p => p.year))];
      return years.sort((a, b) => b - a);
    },
    filteredProjects() {
      return this.portfolioProjects.filter(p => p.year === this.selectedYear);
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.initCarousel();
    });

    $(document).ready(() => {
      $(window).scroll(() => {
        if (window.scrollY > 20) {
          $('.navbar').addClass("sticky");
        } else {
          $('.navbar').removeClass("sticky");
        }
        if (window.scrollY > 500) {
          $('.scroll-up-btn').addClass("show");
        } else {
          $('.scroll-up-btn').removeClass("show");
        }
      });

      $('.scroll-up-btn').click(() => {
        $('html').animate({ scrollTop: 0 });
        $('html').css("scrollBehavior", "auto");
      });

      $('.navbar .menu li a').click(() => {
        $('html').css("scrollBehavior", "smooth");
      });

      $('.menu-btn').click(() => {
        $('.navbar .menu').toggleClass("active");
        $('.menu-btn i').toggleClass("active");
      });

      if (document.querySelector(".typing")) {
        new Typed(".typing", {
          strings: ["Software Engineer"],
          typeSpeed: 100,
          backSpeed: 100,
          loop: true
        });
      }
    });
  },
  watch: {
    selectedYear() {
      this.$nextTick(() => {
        this.initCarousel();
      });
    }
  },
  methods: {
    async sendEmail() {
      this.isSubmitting = true;
      try {
        const response = await fetch('https://formspree.io/f/xojbapqb', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({
            name: this.form.name,
            email: this.form.email,
            subject: this.form.subject,
            message: this.form.message,
            _replyto: this.form.email
          })
        });

        if (response.ok) {
          alert('Message sent successfully!');
          this.form = { name: '', email: '', subject: '', message: '' };
        } else {
          alert('Failed to send message. Please try again.');
        }
      } catch (error) {
        console.error('Error:', error);
        alert('Error sending message. Please try again.');
      } finally {
        this.isSubmitting = false;
      }
    },
    buildSlides(projects) {
      // Build slide HTML manually — no v-for, pure JS
      return projects.map(project => `
        <div class="card">
          <div class="box">
            <img src="${project.image}" alt="${project.title}" />
            <div class="text">${project.title}</div>
            <p>${project.description}</p>
          </div>
        </div>
      `).join('');
    },

    initCarousel() {
      const $carousel = $('.carousel');

      // Step 1: destroy Owl if active
      if ($carousel.hasClass('owl-loaded')) {
        $carousel.trigger('destroy.owl.carousel');
        $carousel.removeClass('owl-loaded owl-drag owl-text-select-off');
      }

      // Step 2: clear and inject fresh slides directly (no Vue DOM involvement)
      $carousel.empty();
      const projects = this.filteredProjects;

      if (projects.length === 0) {
        $carousel.html('<div class="card"><div class="box"><p>No projects for this year.</p></div></div>');
      } else {
        $carousel.html(this.buildSlides(projects));
      }

      // Step 3: init Owl on the fresh HTML
      $carousel.owlCarousel({
        margin: 20,
        loop: false,
        autoplay: false,
        autoplayTimeout: 2000,
        autoplayHoverPause: true,
        dots: true,
        nav: false,
        responsive: {
          0: { items: 1 },
          600: { items: 1 },
          1000: { items: 1 }
        }
      });
    }
  }
}
</script>