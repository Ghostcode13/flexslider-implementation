# flexslider-implementation
An effective hero slider provides users with the most valuable content on your site aligned with your goals and prompts them to take action. In Part I of our FlexSlider Series, [Solodev](https://www.solodev.com/) provides you with the code you need to easily add a hero slider to your homepage using the fully responsive jQuery toolkit [FlexSlider by woothemes](https://woocommerce.com/flexslider/).

## Tutorial

For detailed instructions, view Solodev's [Adding a Hero Slider to your Website Using FlexSlider](https://www.solodev.com/blog/web-design/adding-a-hero-slider-to-your-website-using-flexslider.stml) article.

## Demo

Check out a working example on [JSFiddle](https://jsfiddle.net/solodev/ewzx8qLw/).

## HTML

The flexslider has the following HTML markup.
```
<!-- @zone - hightlighted -->
<!--Showshow-->
<div class="container slider-container">
   <div class="row">
      <div class="col-md-12 slider-left">
         <section class="flexslider-wrapper">
            <div id="main-slider" class="flexslider" data-transition="fade" data-page-class="slider-full-width">
               <div class="slides">
                  <div data-slide-alt="alt" data-slide-bg-stretch=true class="slide slide-bg" data-slide-bg="images/slide1.jpg">
                     <div class="slide-caption">
                        <div class="row">
                           <div class="col-md-12">
                              <div class="slide-text">
                                 <div class="slide-title">This is Slide #1</div>
                                 This is text for the first slide.
                              </div>
                           </div>
                        </div>
                     </div>
                  </div>
                  <div data-slide-alt="alt" data-slide-bg-stretch=true class="slide slide-bg" data-slide-bg="images/slide2.jpg">
                     <div class="slide-caption">
                        <div class="row">
                           <div class="col-md-12">
                              <div class="slide-text">
                                 <div class="slide-title">This is Slide #2</div>
                                 This is text for the second slide.
                              </div>
                           </div>
                        </div>
                     </div>
                  </div>
                  <div data-slide-alt="alt" data-slide-bg-stretch=true class="slide slide-bg" data-slide-bg="images/slide3.jpg">
                     <div class="slide-caption">
                        <div class="row">
                           <div class="col-md-12">
                              <div class="slide-text">
                                 <div class="slide-title">This is Slide #3</div>
                                 This is text for the third slide.
                              </div>
                           </div>
                        </div>
                     </div>
                  </div>
               </div>
         </section>
         </div>
      </div>
   </div>
</div>


```
## JavaScript

The following JavaScript needs to be initiated on page load. 
```
$(document).ready(function () {
if (jQuery().flexslider) {
    //flexslider ticker
    $('.flexslider-ticker').each(function() {
      var tickerSettings =  {
        animation: "slide",
        animationLoop: false,
        selector: ".items > .item",
        move: 1,
        controlNav: false,
        slideshow: true,
        direction: 'vertical'
      };
      $(this).flexslider(tickerSettings);
    });
    // flexsliders
    $('.flexslider').each(function() {
      var sliderSettings =  {
        animation: $(this).attr('data-transition'),
        selector: ".slides > .slide",
        controlNav: false,
        smoothHeight: true,
        prevText: "",
        nextText: "",
        sync: $(this).data('slidernav') || '',
        start: function(slider) {
          if (slider.find('[data-slide-bg-stretch=true]').length > 0) {
            slider.find('[data-slide-bg-stretch=true]').each(function() {
              if ($(this).data('slide-bg')) {
                $(this).backstretch($(this).data('slide-bg'));
                // $(this).data('slide-bg');
              }
            });
          }
        }
      };
      
      $('html').addClass('has-flexslider');
      $(this).flexslider(sliderSettings);
    });
    $(window).delay(1000).trigger('resize'); //make sure height is right load assets loaded
}})
```

## CSS

All necessary CSS is in flex.css

## External Includes

This tutorial includes the following third-party resources:

```
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/flexslider/2.6.2/flexslider.css">
<link rel="stylesheet" href="flex.css">

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-backstretch/2.0.4/jquery.backstretch.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/flexslider/2.6.2/jquery.flexslider.js"></script>
```
