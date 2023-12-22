<template>
  <!-- home section start -->
  <section class="home" id="home">
    <div class="max-width">
      <div class="home-content">
        <div class="text-1">Hello, my name is</div>
        <div class="text-2">Rassel Muhammad Indra</div>
        <div class="text-3">And I'm a <span class="typing">Software Engineer</span></div>
      </div>
    </div>
  </section>

  <!-- about section start -->
  <section class="about" id="about">
    <div class="max-width">
      <h2 class="title">About me</h2>
      <div class="about-content">
        <div class="column left">
          <img src="" alt="" />
        </div>
        <div class="column right">
          <p>
            Greetings! I'm Rassel, currently studying Software Engineering at SMK WIKRAMA BOGOR. My fascination with technology fuels my drive to delve into coding and explore its endless possibilities. Passionate about crafting innovative
            software solutions, I am wholeheartedly devoted to honing my skills and embracing challenges in this ever-evolving field.
          </p>
          <a href="#">Download CV</a>
        </div>
      </div>
    </div>
  </section>

  <!-- teams section start -->
  <section class="teams" id="teams">
    <div class="max-width">
      <h2 class="title">Portfolio</h2>
      <div class="carousel owl-carousel">
        <div class="card">
          <div class="box">
            <img src="" alt="" />
            <div class="text">Someone name</div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
        <div class="card">
          <div class="box">
            <img src="" alt="" />
            <div class="text">Someone name</div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
        <div class="card">
          <div class="box">
            <img src="g" alt="" />
            <div class="text">Someone name</div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
        <div class="card">
          <div class="box">
            <img src="" alt="" />
            <div class="text">Someone name</div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
        <div class="card">
          <div class="box">
            <img src="" alt="" />
            <div class="text">Someone name</div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- services section start -->
  <section class="services" id="services">
    <div class="max-width">
      <h2 class="title">My services</h2>
      <div class="serv-content">
        <div class="card">
          <div class="box">
            <i class="fas fa-paint-brush"></i>
            <div class="text">Web Design</div>
            <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rem quia sunt, quasi quo illo enim.</p>
          </div>
        </div>
        <div class="card">
          <div class="box">
            <i class="fas fa-chart-line"></i>
            <div class="text">Advertising</div>
            <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rem quia sunt, quasi quo illo enim.</p>
          </div>
        </div>
        <div class="card">
          <div class="box">
            <i class="fas fa-code"></i>
            <div class="text">Apps Design</div>
            <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rem quia sunt, quasi quo illo enim.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- contact section start -->
  <section class="contact" id="contact">
    <div class="max-width">
      <h2 class="title">Contact me</h2>
      <div class="contact-content">
        <div class="column left">
          <div class="text">Get in Touch</div>
          <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dignissimos harum corporis fuga corrupti. Doloribus quis soluta nesciunt veritatis vitae nobis?</p>
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
                <div class="sub-title">Warung Seri Ciawi, Bogor, Jawa Barat ,Indonesia</div>
              </div>
            </div>
            <div class="row">
              <i class="fas fa-envelope"></i>
              <div class="info">
                <div class="head">Email</div>
                <div class="sub-title">rasselmuhamadindra@gmail.com</div>
              </div>
            </div>
          </div>
        </div>
        <div class="column right">
          <div class="text">Message me</div>
          <form action="#">
            <div class="fields">
              <div class="field name">
                <input type="text" placeholder="Name" required />
              </div>
              <div class="field email">
                <input type="email" placeholder="Email" required />
              </div>
            </div>
            <div class="field">
              <input type="text" placeholder="Subject" required />
            </div>
            <div class="field textarea">
              <textarea cols="30" rows="10" placeholder="Message.." required></textarea>
            </div>
            <div class="button-area">
              <button type="submit">Send message</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>

  <!-- footer section start -->
  <footer>
    <span>Created By <a href="https://www.codingnepalweb.com">CodingNepal</a> | <span class="far fa-copyright"></span> 2020 All rights reserved.</span>
  </footer>
</template>
<script>
export default {
  mounted() {
    $(document).ready(() => {
      $(window).scroll(() => {
        // sticky navbar on scroll script
        if (this.scrollY > 20) {
          $('.navbar').addClass("sticky");
        } else {
          $('.navbar').removeClass("sticky");
        }

        // scroll-up button show/hide script
        if (this.scrollY > 500) {
          $('.scroll-up-btn').addClass("show");
        } else {
          $('.scroll-up-btn').removeClass("show");
        }
      });

      // slide-up script
      $('.scroll-up-btn').click(() => {
        $('html').animate({ scrollTop: 0 });
        // removing smooth scroll on slide-up button click
        $('html').css("scrollBehavior", "auto");
      });

      $('.navbar .menu li a').click(() => {
        // applying again smooth scroll on menu items click
        $('html').css("scrollBehavior", "smooth");
      });

      // toggle menu/navbar script
      $('.menu-btn').click(() => {
        $('.navbar .menu').toggleClass("active");
        $('.menu-btn i').toggleClass("active");
      });

      // typing text animation script
      let typed = new Typed(".typing", {
        strings: ["YouTuber", "Developer", "Blogger", "Designer", "Freelancer"],
        typeSpeed: 100,
        backSpeed: 60,
        loop: true
      });

      let typed2 = new Typed(".typing-2", {
        strings: ["YouTuber", "Developer", "Blogger", "Designer", "Freelancer"],
        typeSpeed: 100,
        backSpeed: 60,
        loop: true
      });

      // owl carousel script
      $('.carousel').owlCarousel({
        margin: 20,
        loop: true,
        autoplay: true,
        autoplayTimeout: 2000,
        autoplayHoverPause: true,
        responsive: {
          0: {
            items: 1,
            nav: false
          },
          600: {
            items: 2,
            nav: false
          },
          1000: {
            items: 3,
            nav: false
          }
        }
      });
    });
  }
}
</script>
