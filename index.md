<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <title>Gentil's Portfolio</title>
    
    <!-- load CSS -->
    <link
      rel="stylesheet"
      href="https://fonts.googleapis.com/css?family=Open+Sans:300,400,600"
    />
    <!-- Google web font "Open Sans" -->
    <link rel="stylesheet" href="css/bootstrap.min.css" />
    <!-- https://getbootstrap.com/ -->
    <link rel="stylesheet" href="slick/slick.css" />
    <link rel="stylesheet" href="slick/slick-theme.css" />
    <link rel="stylesheet" href="css/magnific-popup.css" />
    <link rel="stylesheet" href="css/tooplate-style.css" />
 
  </head>
  <body>
    <!-- Loader -->
    <div id="loader-wrapper">
      <div id="loader"></div>
      <div class="loader-section section-left"></div>
      <div class="loader-section section-right"></div>
    </div>
        <!-- Site header -->
        <header class="tm-site-header-box tm-bg-dark">
          <h1 class="tm-site-title">Gentil's Portfolio</h1>
        </header>
      </div>
      

      <div class="container-fluid">
        <div class="row">
          <div class="col-md-12">
            <!-- Site content -->
            <div class="tm-content">
              <!-- Section 0 Introduction -->
              <section class="tm-section tm-section-0">
                <h2 class="tm-section-title mb-3 font-weight-bold">
                  Introduction
                </h2>
                <div class="tm-textbox tm-bg-dark">
                  <p>
                    I am a student at MKUR(Mount Kenya University of Rwanda), been attending this school since 2018/september and I'm doing BBICT!
                  </p>
                  <p class="mb-0">
                    Below there are some more information about me!
                  </p>
                </div>
                <a href="#" id="tm_about_link" data-linkid="1" class="tm-link">More Info</a>
              </section>

              <!-- Section 1 About Me -->
              <section class="tm-section tm-section-1">
                <div class="tm-textbox tm-textbox-2 tm-bg-dark">
                  <h2 class="tm-text-blue mb-4">About Me</h2>
                  <p class="mb-4">
                    I am an adaptable college student doing BBICT(Bachelor in Business Information Communication and Technology) currently at the Mount Kenya University/Kigali campus in My Third Academic Year. During the course of my academic career, I have managed to accrue nearly two years of work experience. I learned valuable professional skills such as Customer Communication, Customer Needs Assessment and Customer Satisfactions both in the Business  and in IT deparment. Whether working on academic, extracurricular, or professional projects. I apply proven communication, research and planning skills.
                  </p>
                  <br>
                  <a href="https://www.instagram.com/">
                    <img src="./instagram icon.png">
                  instagram
                  </a>
                  <a href="https://www.whatsapp.com/">
                    <img src="./whatsapp icon.png">
                  whatsapp
                  </a>
                  <a href="https://www.facebook.com/">
                    <img src="./facebook icon.png">
                  facebook
                  </a>
                  
                </div>
                <br>
                <a href="index.html" class="tm-link" >Previous</a>
              </section>
              <section class="tm-section tm-section-1">
                <div class="tm-textbox tm-textbox-2 tm-bg-dark">
                  <h2 class="tm-text-blue mb-4">INFO</h2>
                  <p class="mb-4">
                  Gentil Abednego IRADUKUNDA

                  Rwanda, Kigali,
                  Kicukiro,
                  Tel : +250 789 050 774
                  E-mail : gentilgino224@gmail.com

                  EXPERIENCE
                  Beauty for Ashes Rwanda, Kigali, Rwanda                                 (October 2018) – Present.
                  Staff Support as a volunteer
                  - Available at any point at work as my job title describes. 
                  - Assisting all my coworkers and team leaders.
                  - Stepping in for IT problem solving when needed.


                  New Life Bible Church, Kigali, Rwanda                                    (June 2014) - Present 
                  Volunteer in Technical issues 
                  - Assisting Technical department 
                  - Volunteering as a Projector and screen manager/controller 

                  EDUCATION
                  Mount Kenya University, Kigali campus 
                  Bachelor degree in Business Information Communication and Technology
                  (Information and Technology Option) 2018 - present

                  EFOTEC/Kanombe
                  High School,
                  MEG (Mathematics Economics Geography)
                  Kigali, Kicukiro 2015

                  SKILLS
                  Integrity
                  Time management
                  Clear communication skills
                  Advanced Competitive Native
                  Computer related skills (As my current academic career)
                  Music Skills (Which I did in my gap year from high school)
                  Technical Skills (Musically)
                  Graphic Designing
                  Entrepreneurial Skills

                  LANGUAGES
                  • English: Advanced
                  • French: Competitive
                  • Kinyarwanda: Native
                  . Kiswahili: Good.
                  </p>
                </div>
              </section>
              
            </div>

          </div>
        </div>
      </div>

     
    </div>

    <script src="js/jquery-1.11.0.min.js"></script>
    <script src="js/background.cycle.js"></script>
    <script src="slick/slick.min.js"></script>
    <script src="js/jquery.magnific-popup.min.js"></script>
    <script>
      let slickInitDone = false;
      let previousImageId = 0,
        currentImageId = 0;
      let pageAlign = "right";
      let bgCycle;
      let links;
      let eachNavLink;

      window.onload = function() {
        $("body").addClass("loaded");
      };

      function navLinkClick(e) {
        if ($(e.target).hasClass("external")) {
          return;
        }

        e.preventDefault();

        if ($(e.target).data("align")) {
          pageAlign = $(e.target).data("align");
        }

        // Change bg image
        previousImageId = currentImageId;
        currentImageId = $(e.target).data("linkid");
        bgCycle.cycleToNextImage(previousImageId, currentImageId);

        // Change menu item highlight
        $(`.tm-nav-item:eq(${previousImageId})`).removeClass("active");
        $(`.tm-nav-item:eq(${currentImageId})`).addClass("active");

        // Change page content
        $(`.tm-section-${previousImageId}`).fadeOut(function(e) {
          $(`.tm-section-${currentImageId}`).fadeIn();
          // Gallery
          if (currentImageId === 2) {
            setupSlider();
          }
        });

        adjustFooter();
      }

      $(document).ready(function() {
        // Set first page
        $(".tm-section").fadeOut(0);
        $(".tm-section-0").fadeIn();

        // Set Background images
        // https://www.jqueryscript.net/slideshow/Simple-jQuery-Background-Image-Slideshow-with-Fade-Transitions-Background-Cycle.html
        bgCycle = $("body").backgroundCycle({
          imageUrls: [
            "HD Astronaut .jpg",
            "nelly raw 3-13.jpg",
            "img/photo-04.jpg",
            "img/photo-05.jpg"
          ],
          fadeSpeed: 1000,
          duration: -1,
          backgroundSize: SCALING_MODE_COVER
        });

        eachNavLink = $(".tm-nav-link");
        links = $(".tm-nav-links");

        // "Menu" open/close
        if (links.hasClass("open")) {
          links.fadeIn(0);
        } else {
          links.fadeOut(0);
        }

        $("#tm_about_link").on("click", navLinkClick);
        $("#tm_work_link").on("click", navLinkClick);

        // Each menu item click
        eachNavLink.on("click", navLinkClick);

        $(".tm-navbar-menu").click(function(e) {
          if (links.hasClass("open")) {
            links.fadeOut();
          } else {
            links.fadeIn();
          }

          links.toggleClass("open");
        });

        // window resize
        $(window).resize(function() {
          // If current page is Gallery page, set it up
          if (currentImageId === 2) {
            setupSlider();
          }

          // Adjust footer
          adjustFooter();
        });

        adjustFooter();
      }); // DOM is ready

      function adjustFooter() {
        const windowHeight = $(window).height();
        const topHeight = $(".tm-top-container").height();
        const middleHeight = $(".tm-content").height();
        let contentHeight = topHeight + middleHeight;

        if (pageAlign === "left") {
          contentHeight += $(".tm-bottom-container").height();
        }

        if (contentHeight > windowHeight) {
          $(".tm-bottom-container").addClass("tm-static");
        } else {
          $(".tm-bottom-container").removeClass("tm-static");
        }
      }

      function setupSlider() {
        let slidesToShow = 4;
        let slidesToScroll = 2;
        let windowWidth = $(window).width();

        if (windowWidth < 480) {
          slidesToShow = 1;
          slidesToScroll = 1;
        } else if (windowWidth < 768) {
          slidesToShow = 2;
          slidesToScroll = 1;
        } else if (windowWidth < 992) {
          slidesToShow = 3;
          slidesToScroll = 2;
        }

        if (slickInitDone) {
          $(".tm-gallery").slick("unslick");
        }

        slickInitDone = true;

        $(".tm-gallery").slick({
          dots: true,
          customPaging: function(slider, i) {
            var thumb = $(slider.$slides[i]).data();
            return `<a>${i + 1}</a>`;
          },
          infinite: true,
          prevArrow: false,
          nextArrow: false,
          slidesToShow: slidesToShow,
          slidesToScroll: slidesToScroll
        });

        // Open big image when a gallery image is clicked.
        $(".slick-list").magnificPopup({
          delegate: "a",
          type: "image",
          gallery: {
            enabled: true
          }
        });
      }
    </script>
  </body>
</html>
