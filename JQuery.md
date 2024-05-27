#  JQuery Assignment 



## **Q-1.** What is jQuery?


**Ans.** 
JQuery is a small, light-weight and fast JavaScrip library. It is cross-platform and supports different types of browsers. It is also referred as "write less do more" because it takes a lot of common tasks that requires many lines of JavaScript code to accomplish, and binds tham into methods that can be called with a single line of code whenever needed. It is also very useful to simplify a lot of the complicated things from JavaScript, like AJAX calls and DOM manipulation.
 
jQuery is a lightweight, "write less, do more", JavaScript library. The purpose of jQuery is to make it much easier to use JavaScript.

=>  JQuery is a small, fast and lightweight JavaScript library.
=>  JQuery is platform-independent.
=>  JQuery means "write less do more".
=>  JQuery simplifies AJAX call and DOM manipulation.

## **Q-2.** How to Apply CSS Using JQuery, How to Add Class and Remove Class in Jquery, JQuery Animation?

**Ans.**

    <!DOCTYPE html>
    <html>
    <head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Page Title</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <script src='main.js'></script>
    <style>
        .red{
            color: rgb(60, 73, 67);
        }
        .blake{
            color: aqua;
        }
        .some{
            color: brown;
        }
        .box{
            height: 100px;
            width: 100px;
            margin-top: 50px;
            background-color: rgb(231, 219, 204);
            position: absolute;
        }
    </style>
    </head>
    <body>
    <div class="box red">This is box</div>
    <button>Click here</button>
    <button>Start Animation</button>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" integrity="sha512-v2CJ7UaYy4JwqLDIrZUI/4hqeoQieOmAZNXBeQyjo21dadnwR+8ZaIJVT8EE2iyI61OV8e6M8PP2/4hpQINQ/g==" crossorigin="anonymous" referrerpolicy="no-referrer">
    </script>

    <script>
        $('button').click (() =>{
            $('.box').removeClass('red');
            $('.box').addClass('blake');
            $('.box').toggleClass('some');
            $('.box').hasClass('red');
        });

        $(document).ready(function(){
        $("button").click(function(){
        $("div").animate({
        left: '250px',
        opacity: '0.5',
        height: '150px',
        width: '150px'
        });
        });
    });
    </script>
    </body>
    </html>


## **Q-3.** How to create slider with animation?

**Ans.**

    <!DOCTYPE html>
    <html>
    <head>
        <title>Slider using jQuery</title>
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet"href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" integrity="sha512-v2CJ7UaYy4JwqLDIrZUI/4hqeoQieOmAZNXBeQyjo21dadnwR+8ZaIJVT8EE2iyI61OV8e6M8PP2/4hpQINQ/g==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
        <style>
            h1{
                padding: 10px 0px 0px 550px;
                font-size: 3rem;
                font-weight: 900;
            }
            img {
                width: 100%;
                height: 400px;
                border-radius: 40px;
            }

            .height {
                height: 10px;
            }

            .image-container {
                padding-top: 0px;
                max-width: 800px;
                position: relative;
                margin: auto;
            }

            .next {
                right: 0;
            }

            .previous,
            .next {
                cursor: pointer;
                position: absolute;
                top: 50%;
                padding: 10px;
                margin-top: -25px;
            }

            .captionText {
                color: #000000;
                font-size: 14px;
                position: absolute;
                padding: 12px 12px;
                bottom: 8px;
                width: 100%;
                text-align: center;
            }

            .fa {
                font-size: 32px;
            }

            .footerdot {
                cursor: pointer;
                height: 15px;
                width: 15px;
                margin: 0 2px;
                background-color: #bbbbbb;
                border-radius: 50%;
                display: inline-block;
                transition: background-color 0.5s ease;
            }

            .active,
            .footerdot:hover {
                background-color: black;
            }
        </style>
    </head>
    <body>
        <h1>jQurey Slider</h1>
        
        <div class="image-container">
            <div class="slide">
                <img src="https://images.pexels.com/photos/133081/pexels-photo-133081.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1">
            </div>

            <div class="slide">
                <img src="https://images.pexels.com/photos/326055/pexels-photo-326055.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1">
            </div>

            <div class="slide">
                <img src="https://images.pexels.com/photos/1043458/pexels-photo-1043458.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1">
            </div>

            
            <a class="previous" onclick="moveSlides(-1)">
                <i class="fa fa-chevron-circle-left"></i>
            </a>
            <a class="next" onclick="moveSlides(1)">
                <i class="fa fa-chevron-circle-right"></i>
            </a>
        </div>

        <br>

        <div style="text-align:center">
            <span class="footerdot" onclick="activeSlide(1)">
            </span>
            <span class="footerdot" onclick="activeSlide(2)">
            </span>
            <span class="footerdot" onclick="activeSlide(3)">
            </span>
        </div>

        <script>
            let slideIndex = 1;
            displaySlide(slideIndex);

            function moveSlides(n) {
                displaySlide(slideIndex += n);
            }

            function activeSlide(n) {
                displaySlide(slideIndex = n);
            }


            function displaySlide(n) {
                let i;
                let totalslides =
                    document.getElementsByClassName("slide");

                let totaldots =
                    document.getElementsByClassName("footerdot");

                if (n > totalslides.length) {
                    slideIndex = 1;
                }
                if (n < 1) {
                    slideIndex = totalslides.length;
                }
                for (i = 0; i < totalslides.length; i++) {
                    totalslides[i].style.display = "none";
                }
                for (i = 0; i < totaldots.length; i++) {
                    totaldots[i].className =
                        totaldots[i].className.replace(" active", "");
                }
                totalslides[slideIndex - 1].style.display = "block";
                totaldots[slideIndex - 1].className += " active";
            }
        </script>
    </body>
    </html>


## **Q-4.** Event bubbling tickling example

**Ans.**

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset='utf-8'>
        <meta http-equiv='X-UA-Compatible' content='IE=edge'>
        <title>Page Title</title>
        <meta name='viewport' content='width=device-width, initial-scale=1'>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" integrity="sha512-v2CJ7UaYy4JwqLDIrZUI/4hqeoQieOmAZNXBeQyjo21dadnwR+8ZaIJVT8EE2iyI61OV8e6M8PP2/4hpQINQ/g==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
        <style>
            div {
                color: black;
                display: flex;
                justify-content: center;
                align-items: center;
                flex-direction: column;
            }
            
            .boss {
                width: 500px;
                height: 500px;
                background-color: bisque;
                display: flex;
                justify-content: center;
                align-items: center;
                margin: 60px 0px 0px 400px;
            }


            .Client {
                width: 300px;
                height: 300px;
                background-color: burlywood;
                display: flex;
                justify-content: center;
                align-items: center;
            }

            .sub-client {
                width: 100px;
                height: 100px;
                background-color: violet;
                display: flex;
                justify-content: center;
                align-items: center;
            }
        </style>
    </head>
    <body>
        <div class="boss">boss
            <div class="Client">client
                <div class="sub-client">sub-client
                    <button>Click here</button>
                </div>
            </div>
        </div>

        <script>
        let boss = document.getElementsByClassName('boss')[0];
        let Client = document.getElementsByClassName('Client')[0];
        let subClient = document.getElementsByClassName('sub-client')[0];
        let btn = document.getElementsByTagName('button')[0];


        document.addEventListener('click', (event) => {
            console.log("Document capturing");
        }, {capture: true});

        boss.addEventListener('click', (event) => {
        console.log("boss capturing");
        btn.style.color = 'red';
        Client.style.backgroundColor = 'blue';
        }, {capture: true});

        Client.addEventListener('click', (event) => {
        console.log("Client capturing");
        }, {capture: true});

        subClient.addEventListener('click', (event) => {
        console.log("sub-client capturing");
        }, {capture: true});

        btn.addEventListener('click', (event) => {
        console.log("sub-client capturing");
        }, {capture: true});
        

        document.addEventListener('click', (event) => {
            console.log("Document capturing");
        }, {capture: false});

        boss.addEventListener('click', (event) => {
        console.log("boss capturing");
        btn.style.color = 'red';
        Client.style.backgroundColor = 'blue';
        }, {capture: false});

        Client.addEventListener('click', (event) => {
        console.log("Client capturing");
        }, {capture: false});

        subClient.addEventListener('click', (event) => {
        console.log("sub-client capturing");
        }, {capture: false});

        btn.addEventListener('click', (event) => {
        console.log("sub-client capturing");
        }, {capture: false});
    </script>

        <script>
            $(document).ready(function () {
                $(".boss").click(function () {
                    event.stopPropagation();
                    alert("boss");
                });

                $(".Client").click(function () {
                    alert("Client");
                });

                $(".sub-client").click(function () {
                    alert("sub-client");
                });

                $("button").click(function () {
                    alert("button");
                });
            });
        </script>
    </body>
    </html>

