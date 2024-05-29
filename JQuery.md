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
    
    body {
        font-family: Arial, sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        background-color: #f0e8e8;
    }

    .slider {
        height: 400px;
        width: 80%;
        overflow: hidden;
        border: 2px solid #ddd;
        border-radius: 10px;
        box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    .slides {
        display: flex;
        transition: transform 0.5s ease-in-out;
    }

    .slide {
        min-width: 100%;
        box-sizing: border-box;
    }

    .slide img {
        width: 100%;
        border-radius: 10px;
        
    }
        </style>
    </head>
    <body>
        <div class="slider">
            <div class="slides">
                <div class="slide"><img src="https://th.bing.com/th/id/R.7383028831604862ec47fefee3e8f43f?rik=JvqjDCfPocchLg&riu=http%3a%2f%2fthewowstyle.com%2fwp-content%2fuploads%2f2015%2f01%2fimages-of-nature-4.jpg&ehk=%2b1REJDS0cEPD0z2IP%2fddCyP9IgFz6xVpp8fyQr78SJ0%3d&risl=&pid=ImgRaw&r=0" alt="Image 1"></div>

                <div class="slide"><img src="https://images.pexels.com/photos/462118/pexels-photo-462118.jpeg?cs=srgb&dl=bloom-blooming-blossom-462118.jpg&fm=jpg" alt="Image 2"></div>

                <div class="slide"><img src="https://th.bing.com/th/id/R.d22aafa9433efcc9ed4d9a7808c05a8a?rik=8tekSpiFRq3jhg&riu=http%3a%2f%2fwww.pixelstalk.net%2fwp-content%2fuploads%2f2016%2f07%2fDownload-Free-Pictures-3840x2160.jpg&ehk=ZfChm9icVrVUFSnPnWsPaf7qOQGA9l1qj0BRZx4lTzE%3d&risl=&pid=ImgRaw&r=0" alt="Image 3"></div>
            </div>
        </div>
        <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

        <script>
            $(document).ready(function() {
        const $slides = $('.slides');
        const slideCount = $('.slide').length;
        let currentIndex = 0;

        function goToSlide(index) {
            $slides.css('transform', `translateX(${-index * 100}%)`);
            currentIndex = index;
        }

        function nextSlide() {
            if (currentIndex < slideCount - 1) {
                goToSlide(currentIndex + 1);
            } else {
                goToSlide(0);
            }
        }

        setInterval(nextSlide, 3000);
        });

        </script>
        </body>
        </html>


## **Q-4.** Event bubbling tickling example

**Ans.**

    ==> Event Bubbling is a behavior in the Document Object Model (DOM) where an element receives an event, and that event propagates or “bubbles up” to its parent and ancestor elements in the DOM tree until it reaches the root element. In other words, when an event occurs on a child element, it also triggers the same event on its parent and ancestor elements.

    => Event bubbling allows you to handle an event in a parent element instead of the actual element that received the event. This pattern is called Event Delegation.
    
    => For instance, you can attach an event listener to a parent element that contains a list of items. When an item within the list is clicked, the event bubbles up to the parent, allowing you to handle it efficiently.

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

