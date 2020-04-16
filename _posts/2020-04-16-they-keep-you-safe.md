---
layout: post
author: Daniel Dykiel
---

<html>
  
	<head>
	 <meta charset="utf-8" />
		<style>
			#scrolly {
			  position: relative;
			}
			.scroll__text {
			  padding: 0 1rem;
			  max-width: 30rem;
			}
			
			article {
			position: relative;
			padding: 0 1rem;
			margin: 0 auto;
			width: 33%;
			}
			
			.step {
			  margin: 2rem auto 4rem auto;
			  opacity: 0;
			  padding: 1rem;
			}

			.step.is-active {
			  opacity: 1;
			}
			
			.step p {
			text-align: center;
			padding: 1rem;
			font-size: 1.5rem;
			}
			
		</style>

	</head>
	
	<body>
	<main>
	<section id="scrolly">
        <article>
          <div class="step" data-step="1">
            <p>STEP 1</p>
          </div>
          <div class="step" data-step="2">
            <p>STEP 2</p>
          </div>
          <div class="step" data-step="3">
            <p>STEP 3</p>
          </div>
          <div class="step" data-step="4">
            <p>STEP 4</p>
          </div>
        </article>
      </section>
	</main>
	
	//JS goes here
	<script src="https://unpkg.com/intersection-observer"></script>
	<script src="https://unpkg.com/scrollama"></script>
	<script>
	  var scrolly = document.querySelector("#scrolly");
          var article = scrolly.querySelector("article");
          var step = article.querySelectorAll(".step");

      // initialize the scrollama
      var scroller = scrollama();

      // scrollama event handlers
      function handleStepEnter(response) {
        // response = { element, direction, index }
        console.log(response);
        // add to color to current step
        response.element.classList.add("is-active");
      }

      function handleStepExit(response) {
        // response = { element, direction, index }
        console.log(response);
        // remove color from current step
        response.element.classList.remove("is-active");
      }

      function init() {
        // set random padding for different step heights (not required)
        step.forEach(function(step) {
          var v = 100 + Math.floor((Math.random() * window.innerHeight) / 4);
          step.style.padding = v + "px 0px";
        });

        // 1. setup the scroller with the bare-bones options
        // 		this will also initialize trigger observations
        // 2. bind scrollama event handlers (this can be chained like below)
        scroller
          .setup({
            step: "#scrolly article .step",
            debug: true,
            offset: 0.5
          })
          .onStepEnter(handleStepEnter)
          .onStepExit(handleStepExit);

        // 3. setup resize event
        window.addEventListener("resize", scroller.resize);
      }

      // kick things off
      init();
	</script>

	</body>

</html>
