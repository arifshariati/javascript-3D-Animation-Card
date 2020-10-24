
# javascript-3D-Animation-Card

Working with Javascript and CSS is always fun. This repository demonstrates 3D effect with javascript and CSS. Here, I have used Card concept (key component of material ui and bootsrap), however, you can implement this effect on any component you want.


### Javascript Features Used

1. document.querySelector([document area you want to refer to])
2. Javascript Event Listener [addEventListener] for mousemove, mouseenter, mouseleave
3. Finding X and Y position of mouse and manipulating mouse event
4. Transforming CSS style with rotateX / rotateY to certain degrees

For detailed insight, have a look at code snipest bellow.

[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)


## index.html 

```jsx
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/css2?family=Poppins&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="./style.css">
    <title>Document</title>
</head>
<body>
    <div class="container">
        <div class="card">
            <div class="sneaker">
                <div class="circle"></div>
                <img src="./sneakers.png" alt="Sneakers">
            </div>
            <div class="info">
                <h1 class="title">Sneakers</h1>
                <h3>This is the most fantastic sneakers you will get around</h3>
                <div class="sizes">
                    <button>39</button>
                    <button>40</button>
                    <button class="active">42</button>
                    <button>44</button>
                </div>
                <div class="purchase">
                    <button>Purchase</button>
                </div>
            </div>
        </div>
    </div>
    <script src="./app.js"></script>
</body>
</html>
```

### style.css

```jsx
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  perspective: 1000px;
  font-family: "Poppins", sans-serif;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.container {
  width: 22%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card {
  transform-style: preserve-3d;
  min-height: 60vh;
  width: 25rem;
  box-shadow: 0 5px 5px rgba(0, 0, 0, 0.2), 0 10px 10px rgba(0, 0, 0, 0.2);
  border-radius: 30px;
  padding: 0rem 3rem;
}
.sneaker {
  min-height: 25vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.sneaker img {
  width: 15rem;
  z-index: 2;
  transition: all 0.75s ease-in-out;
}
.circle {
  width: 12rem;
  height: 12rem;
  background: khaki;
  position: absolute;
  border-radius: 50%;
  z-index: 1;
}
.info h1 {
  font-size: 2rem;
  transition: all 0.75s ease-in-out;
}
.info h3 {
  font-size: 1rem;
  padding: 2rem 0rem;
  color: #585858;
  font-weight: lighter;
  transition: all 0.75s ease-in-out;
}
.sizes {
  display: flex;
  justify-content: space-between;
  transition: all 0.75s ease-in-out;
}
button {
  padding: 0.5rem 1.5rem;
  background: none;
  border: none;
  box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.2);
  border-radius: 30px;
  font-weight: bolder;
  color: #585858;
  cursor: pointer;
  transition: all 0.75s ease-in-out;
}
button.active {
  background: #585858;
  color: white;
}
.purchase {
  margin-top: 2.5rem;
}

.purchase button {
  width: 100%;
  padding: 1rem 0rem;
  background: #f54642;
  border: none;
  color: white;
  cursor: pointer;
  border-radius: 30px;
  font-weight: bolder;
  transition: all 0.75s ease-in-out;
}

```

### app.js

```jsx
const card = document.querySelector(".card");
const container = document.querySelector(".container");

//items
const title = document.querySelector(".title");
const sneaker = document.querySelector(".sneaker img");
const purchase = document.querySelector(".purchase button");
const description = document.querySelector(".info h3");
const sizes = document.querySelector(".sizes");

// Moving animation event
container.addEventListener("mousemove", (e) => {
  let xAxis = (window.innerWidth / 2 - e.pageX) / 15;
  let yAxis = (window.innerHeight / 2 - e.pageY) / 15;
  card.style.transform = `rotateY(${xAxis}deg) rotateX(${yAxis}deg)`;
});

// Animate In
container.addEventListener("mouseenter", (e) => {
  card.style.transition = "none";

  // Popout Effect
  title.style.transform = `translateZ(150px)`;
  sneaker.style.transform = `translateZ(200px) rotateZ(-35deg)`;
  description.style.transform = `translateZ(125px)`;
  sizes.style.transform = `translateZ(100px)`;
  purchase.style.transform = `translateZ(75px)`;
});
// Animate Out
container.addEventListener("mouseleave", (e) => {
  card.style.transition = "all 0.5s ease";
  card.style.transform = `rotateY(0deg) rotateX(0deg)`;

  title.style.transform = `translateZ(0)`;
  sneaker.style.transform = `translateZ(0) rotateZ(0)`;
  purchase.style.transform = `translateZ(0)`;
  description.style.transform = `translateZ(0)`;
  sizes.style.transform = `translateZ(0)`;
});
```


### 🗒️.  NOTE 

In this example, 3D Animation is applied to every element of Card. You can play around with various values of transition, perspective, transform-style etc.

### 🔥 🔥  Future Plan  🔥 🔥
I am looking forward to implement this to Material UI and Bootstrap Card and release in npm package. I would love to hear if you want to help or be part of this fun !

### 👍   Comments & Suggestions
Do let me know if you have tough time in implementing 3D effect in your project. Or If you have suggestions, I would love to hear.

## License

MIT © [arifshariati](https://github.com/arifshariati)
0 comments on commit e97554b
@arifshariati
 
 
Leave a comment
No file chosen
Attach files by dragging & dropping, selecting or pasting them.
 You’re receiving notifications because you’re watching this repository.
© 2020 GitHub, Inc.
Terms
Privacy
Security
Status
Help
Contact GitHub
Pricing
API
Training
Blog
About
