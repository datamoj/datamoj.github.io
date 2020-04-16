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
			
			article {
			position: relative;
			padding: 0.5rem;
			margin: 0 auto;
			width: 100%;
			}
			
			.step {
			  margin: 0.5rem auto 0.5rem auto;
			  background-color: white;
			  color: white;
			  font-family: Arial, Helvetica, sans-serif;
			  opacity: 15%;
			}

			.step.is-active {
			  background-color: white;
			  color: #3b3b3b;
			  opacity: 100%;
			}
			
			.step p {
			text-align: center;
			padding: 0.5rem;
			font-size: 1rem;
			}
			
		</style>

	</head>
	
	<body>
	<main>
	<section id="scrolly">
        <article>
          <div class="step" data-step="1">
            <p><a href="https://imgur.com/UTrTEFu"><img src="https://i.imgur.com/UTrTEFu.gif" title="source: imgur.com" /></a></p>
          </div>
          <div class="step" data-step="2">
           <p>I wake up with moving skin. In the night, it’s become a living being. My lover’s warmth seeps my arm, and I feel it from outside of myself. They ask me about my dreams and I don’t tell them. </p>
	<p>Weeks later, I stand in front of a Dali painting and almost have a panic attack. The mania rises, compounds. I still it with my breaths, but the levels keep getting higher. I can’t pull myself away. </p>
          </div>
          <div class="step" data-step="3">
	  <p>A friend once told me the way LSD changes your brain chemistry. He gets caught in simple, repetitive motions, still moments. Particles of the drug are released into his system, irrevocable embedded into him. He falls into the clinking of a spoon against a cup, the swirling of the cream and coffee. A moment turned more lucid, more evocative than reality. </p>
	<p>I hadn’t really believed him, at the time. But the painting moves. It pulls me in. The mythical texture of the paint—no photograph could ever do it justice. I lose myself in it and lose my partner in the gallery. Like so many times before, we miss each other. <i>I thought you needed space; I wanted you there. I thought it didn’t matter; it was a small moment that cut deep.</i></p> 
           </div>
          <div class="step" data-step="4">
           <p>This is a softer opening. Warm skin and open lips, gold tinted hair and sleepy mornings in slanted sunlight. Two people who love each other, two people who hurt each other, two people who learn and grow together.</p> 
	<p>Aches and pains buried, blackened earth crumbling.  A moment of stillness before confession. Terrified breath. Streaked hands when we dig them out again. We bury them again, lay them to rest. Cultivate a tenuous reconciliation. We grow, reach each other again.</p>
	<p>Work that is difficult, heart-wrenching, rewarding: but we don’t let it kill.</p>
          </div>
	  <div class="step" data-step="5">
	  <p><a href="https://imgur.com/JG8tQaF"><img src="https://i.imgur.com/JG8tQaF.jpg" title="source: imgur.com" /></a></p>
	  </div>
	  <div class ="step" data-step="6">
	  <h>◆</h>
	  </div>
	  <div class="step" data-step="7">
	  <p>Let’s look at another opening. What my life used to be like before I learned to live it better.</p>
	  </div>
	  <div class="step" data-step="8">
	  <p>So. My brother. The humanitarian, empathetic soul, who didn’t have a violent bone in his body. My brother, who has made my cry more than any other person on earth.</p> 
<p>In an image more vivid than memory, more crystalline, with thicker and more vibrant strokes:</p>
<p>His expression visibly darkens. He says, “I already try hard enough not to hit mom.” His voice sends a cold shock through me. He keeps talking in a similar vein. It fills me with a muddy feeling of fear.</p>
<p> debug 3 </p>
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
          var v = 10 + Math.floor((Math.random() * window.innerHeight) / 15);
          step.style.padding = v + "px 0px";
        });

        // 1. setup the scroller with the bare-bones options
        // 		this will also initialize trigger observations
        // 2. bind scrollama event handlers (this can be chained like below)
        scroller
          .setup({
            step: "#scrolly article .step",
            debug: false,
            offset: 0.3
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
