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
          <div class="article" data-step="1">
            <p><a href="https://imgur.com/UTrTEFu"><img src="https://i.imgur.com/UTrTEFu.gif" title="source: imgur.com" /></a></p>
          </div>
          <div class="article" data-step="2">
           <p>I wake up with moving skin. In the night, it’s become a living being. My lover’s warmth seeps my arm, and I feel it from outside of myself. They ask me about my dreams and I don’t tell them. </p>
	<p>Weeks later, I stand in front of a Dali painting and almost have a panic attack. The mania rises, compounds. I still it with my breaths, but the levels keep getting higher. I can’t pull myself away. </p>
	<p>A friend once told me the way LSD changes your brain chemistry. He gets caught in simple, repetitive motions, still moments. Particles of the drug are released into his system, irrevocable embedded into him. He falls into the clinking of a spoon against a cup, the swirling of the cream and coffee. A moment turned more lucid, more evocative than reality. </p>
	<p>I hadn’t really believed him, at the time. But the painting moves. It pulls me in. The mythical texture of the paint—no photograph could ever do it justice. I lose myself in it and lose my partner in the gallery. Like so many times before, we miss each other. <i>I thought you needed space; I wanted you there. I thought it didn’t matter; it was a small moment that cut deep.</i><p> 
	<p>Nightmares. For weeks on end.</p> 
	<p>The same imagery, the same evocation. The saccharine desperation, the withering rejection. Am I enough—do I love enough? Do I love the right way? The sense of something not understood, but simmering beneath the surface in its power, its obscurity.</p>

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
