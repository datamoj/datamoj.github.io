---
layout: post
author: Cal Murgu
---

<html>

<head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <title>Scrollama: Basic Example</title>
    <style>
        #scrolly {
            position: relative;
        }
        article {
            position: relative;
            padding: 0 1rem;
            margin: 0 auto;
            width: 50%;
        }
        .step-first {
            margin: 2rem auto 4rem auto;
            background-color: white;
            color: black;
            font-family: Arial, Helvetica, sans-serif;
            opacity: 100%;
        }
        .step {
            margin: 2rem auto 4rem auto;
            background-color: white;
            color: black;
            font-family: Arial, Helvetica, sans-serif;
            opacity: 15%;
        }
        .step.is-active {
            background-color: white;
            color: #3b3b3b;
            opacity: 100%;
        }
        .step p {
            padding: 1rem;
            font-size: 1rem;
        }
    </style>
</head>

<body>
    <main>
        <section id="intro">
            <h1 class="intro__hed">Basic Example</h1>
            <p class="intro__dek">
                Start scrolling to see how it works.
            </p>
        </section>
        <section id="scrolly">
            <article>
                <div class="step-first" data-step="1">
                    <h1>INTRODUCTION</h1>
                    <p>I’ve brought together a few different sources to display the growing number of academic libraries closing in North America as a response to the COVID-19 pandemic. This map will update regularly (every hour, or so). I’ll try my best to keep on top of new closures. While I'm aggregating data from multiple sources, the most authorative source is Ithaka: to view click here.</p>
                </div>
                <div class="step" data-step="2">
                    <p>GRAPHIC</p>
                    <iframe title="University and State College Library Closures"
                            aria-label="North America Symbol map" id="datawrapper-chart-Xve0N"
                            src="https://datawrapper.dwcdn.net/Xve0N/10/" scrolling="no" frameborder="0"
                            style="width: 0; min-width: 100% !important; border: none;" height="668"></iframe>
                </div>
                <div class="step" data-step="3">
                    <p>Maecenas nec ullamcorper nunc, nec pellentesque ligula. Aliquam faucibus nulla justo, et accumsan dui fringilla nec. Proin eu ante dolor. Etiam aliquam eu dolor a congue. Aliquam erat volutpat. Praesent porta risus vitae lectus efficitur fringilla. Curabitur non magna eget enim rhoncus varius. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Duis a placerat dui, eget auctor elit. Fusce commodo mattis metus, a ultrices purus malesuada et. Morbi enim mauris, mollis quis nibh quis, luctus aliquet metus. Aenean eu enim blandit, fringilla mauris sit amet, pellentesque enim. Aliquam vulputate facilisis neque, eu malesuada purus vestibulum sagittis. Maecenas vitae odio imperdiet, finibus ante ac, egestas ipsum. Nulla sapien felis, iaculis ut eleifend at, tincidunt in enim.</p>
                    <iframe title="University and State College Library Closures"
                            aria-label="North America Symbol map" id="datawrapper-chart-Xve0N"
                            src="https://datawrapper.dwcdn.net/XjO0P/2/" scrolling="no" frameborder="0"
                            style="width: 0; min-width: 100% !important; border: none;" height="668"></iframe>
                </div>
                <div class="step" data-step="4">
                    <p>Maecenas nec ullamcorper nunc, nec pellentesque ligula. Aliquam faucibus nulla justo, et accumsan dui fringilla nec. Proin eu ante dolor. Etiam aliquam eu dolor a congue. Aliquam erat volutpat. Praesent porta risus vitae lectus efficitur fringilla. Curabitur non magna eget enim rhoncus varius. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Duis a placerat dui, eget auctor elit. Fusce commodo mattis metus, a ultrices purus malesuada et. Morbi enim mauris, mollis quis nibh quis, luctus aliquet metus. Aenean eu enim blandit, fringilla mauris sit amet, pellentesque enim. Aliquam vulputate facilisis neque, eu malesuada purus vestibulum sagittis. Maecenas vitae odio imperdiet, finibus ante ac, egestas ipsum. Nulla sapien felis, iaculis ut eleifend at, tincidunt in enim.</p>
                </div>
            </article>
        </section>
        <section id="outro"></section>
    </main>

    <script src="https://unpkg.com/intersection-observer"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/scrollama/2.2.0/scrollama.min.js"></script>
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
            step.forEach(function (step) {
                var v = 'auto';
                step.style.padding = v + " 0px";
            });

            // 1. setup the scroller with the bare-bones options
            // 		this will also initialize trigger observations
            // 2. bind scrollama event handlers (this can be chained like below)
            scroller
                .setup({
                    step: "#scrolly article .step",
                    debug: false,
                    offset: 0.7
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
