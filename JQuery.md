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
            color: blue;
        }
        .blake{
            color: aqua;
        }
        .some{
            color: brown;
        }
    </style>
    </head>
    <body>
    <div class="box red">This is box</div>
    <button>Click here</button>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" integrity="sha512-v2CJ7UaYy4JwqLDIrZUI/4hqeoQieOmAZNXBeQyjo21dadnwR+8ZaIJVT8EE2iyI61OV8e6M8PP2/4hpQINQ/g==" crossorigin="anonymous" referrerpolicy="no-referrer">
    </script>

    <script>
        $('button').click (() =>{
            $('.box').removeClass('red');
            $('.box').addClass('blake');
            $('.box').toggleClass('some');
            $('.box').hasClass('red');
        });
    </script>
    </body>
    </html>


## **Q-3.** How to create slider with animation?

**Ans.**

    <!DOCTYPE html>
    <html>
    <head>
    <html lang="en">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js" integrity="sha512-v2CJ7UaYy4JwqLDIrZUI/4hqeoQieOmAZNXBeQyjo21dadnwR+8ZaIJVT8EE2iyI61OV8e6M8PP2/4hpQINQ/g==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <style>
    * {
        box-sizing: border-box;
    };

    body {
        font-family: Verdana, sans-serif;
        margin:0;
        };

    .mySlides {
        display: none;
    };

    img {
        vertical-align: middle;
        height: 100%;
        margin-top: 50px;
    };


    .slideshow-container {
    max-width: 1000px;
    position: relative;
    margin: auto;
    };

    .prev, .next {
    cursor: pointer;
    position: absolute;
    top: 50%;
    width: auto;
    padding: 16px;
    margin-top: -22px;
    color: white;
    font-weight: bold;
    font-size: 18px;
    transition: 0.6s ease;
    border-radius: 0 3px 3px 0;
    user-select: none;
    };

    .next {
    right: 0;
    border-radius: 3px 0 0 3px;
    };

    .prev:hover, .next:hover {
    background-color: rgba(44, 27, 27, 0.8);
    };

    .text {
    color: #f2f2f2;
    font-size: 15px;
    padding: 8px 12px;
    position: absolute;
    bottom: 8px;
    width: 100%;
    text-align: center;
    };

    .numbertext {
    color: #f2f2f2;
    font-size: 12px;
    padding: 8px 12px;
    position: absolute;
    top: 0;
    };

    .fade {
    animation-duration: 1.5s;
    };
    </style>
    </head>
    <body>

    <div class="slideshow-container">

    <div class="mySlides fade">
    <div class="numbertext">1 / 3</div>
    <img src="https://images.pexels.com/photos/18873395/pexels-photo-18873395/free-photo-of-tea-coffee-and-a-vase-with-blooming-flowers-on-a-table-standing-by-a-window.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" style="width:100%" height="500px">
    <div class="text">Caption One</div>
    </div>

    <div class="mySlides fade">
    <div class="numbertext">2 / 3</div>
    <img src="https://images.pexels.com/photos/14894306/pexels-photo-14894306.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" style="width:100%" height="500px">
    <div class="text">Caption Two</div>
    </div>

    <div class="mySlides fade">
    <div class="numbertext">3 / 3</div>
    <img src="https://images.pexels.com/photos/17363224/pexels-photo-17363224/free-photo-of-mountain-in-snow.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1" style="width:100%" height="500px">
    <div class="text">Caption Three</div>
    </div>

    <a class="prev" onclick="plusSlides(-1)">❮</a>
    <a class="next" onclick="plusSlides(1)">❯</a>

    </div>
    <br>

    <script>
    let slideIndex = 1;
    showSlides(slideIndex);

    function plusSlides(n) {
    showSlides(slideIndex += n);
    }

    function currentSlide(n) {
    showSlides(slideIndex = n);
    }

    function showSlides(n) {
    let i;
    let slides = document.getElementsByClassName("mySlides");
    if (n > slides.length) {slideIndex = 1}    
    if (n < 1) {slideIndex = slides.length}
    for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";  
    }

    slides[slideIndex-1].style.display = "block";  
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
        <div class="boss">
            <div class="Client">
                <div class="sub-client">
                    <button>Click here</button>
                </div>
            </div>
        </div>

        <script>
        let boss = document.getElementsByClassName('boss')[0];
        let Client = document.getElementsByClassName('Client')[0];
        let subClient = document.getElementsByClassName('sub-client')[0];
        let btn = document.getElementsByTagName('button')[0];


        boss.addEventListener('click', (event) => {
        // event.stopPropagation();
        console.log('boss is clicked');
        });

        Client.addEventListener('click', (event) => {
        // event.stopPropagation();
        console.log('Client is clicked');
        btn.style.color = 'red';
        Client.style.backgroundColor = 'blue';
        });

        subClient.addEventListener('click', (event) => {
        // event.stopPropagation();
        console.log('subClient is clicked');
        });

        btn.addEventListener('click', (event) => {
        // event.stopPropagation();
        console.log('Btn is clicked');
        });
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

