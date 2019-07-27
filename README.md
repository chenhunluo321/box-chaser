<p align="center">
    <a href="" rel="noopener">
 <img height= 210 width = 280 src="https://user-images.githubusercontent.com/32112516/61998159-3fe67c80-b09b-11e9-83ca-e4091389fb68.png" alt="Project logo"></a>

<h3 align="center">Box Chaser</h3>

<div align="center">

  <img src="https://img.shields.io/badge/license-MIT-yellow.svg?style=flat-square">
  <img src="https://img.shields.io/badge/downloads-0k-yellow.svg?style=flat-square">
  <img src="https://img.shields.io/badge/build-passing-yellow.svg?style=flat-square">

</div>

---

<p align="center">
    <br> 
</p>

## 🧐 About 
This game is mainly about JavaScript element selection and manipulation. The grid size will be dynamically builded with JavaScript and the key event listeners will be handling the key press and moving element. User will be able to move the red box around with arror keys, once it overlap with the green box, the score variable will be increment by one and the green box will be randomly placed in a new position within the grid

## 🏁 Installing

Open box_.html with any web browser. If you are using Microsoft Internet Explorer, it need to be after version 2.0

## 🦄 Demo

![ezgif com-crop](https://user-images.githubusercontent.com/32112516/61998951-fef46500-b0a6-11e9-9509-51fd2d2f7058.gif)

## 🎈 Code Walk Through

The style section is the CSS defining the size of the grid and how the elements in the game will looks like


In `build()` we are using objects and Arrays to contain element content and creating elements and adding them to the html dynamically based on the grid size defined in `.gameArea`.

```html
        function build() {
            box = document.createElement("div");
            box.classList.add("box");
            box.x = gameArea.top;
            box.y = gameArea.left;
            box.style.top = box.y + "px";
            box.style.left = box.x + "px";
            gameAreaEle.appendChild(box);
            let counter = 1;
            for (let y = 0; y < gamebox.y; y++) {
                for (let x = 0; x < gamebox.x; x++) {
                    squares[counter] = document.createElement("div");
                    squares[counter].innerHTML = counter;
                    squares[counter].classList.add("square");
                    gameAreaEle.appendChild(squares[counter]);
                    counter++;
                }
            }
            makeActive();
        }
```


In `handleKeyPress(key)`, we are validating user's keyboard input. Only arrow keys will be count as valid inputs. Once the valid keyboard received, new position will be updated and displayed on the game grid. For each arrow key press, we are also check whether the current position is about of the grid boundary
```html
        function handleKeyPress(key) {
            console.log(key);
            if (key === "left" && box.x > gameArea.left) {
                box.x -= player.speed;
                player.square--;
            }
            if (key === "right" && box.x < gameArea.right - box.offsetWidth) {
                box.x += player.speed;
                player.square++;
            }
            if (key === "down" && box.y < (gameArea.bottom - box.offsetHeight)) {
                box.y += player.speed;
                player.square += gamebox.x;
            }
            if (key === "up" && box.y > gameArea.top) {
                box.y -= player.speed;
                player.square -= gamebox.x;
            }
            box.style.left = box.x + "px";
            box.style.top = box.y + "px";
            console.log(player.square);
            if (squares[player.square].classList.contains("active")) {
                console.log("FOUND");
                squares[player.square].classList.remove("active");
                makeActive();
                player.score++;
                score.innerHTML = player.score;
            }
        }
```
In `makeActive()`, we are selecting a random box within the grid and applying the class of active to that.
```html
        function makeActive() {
            let randomIndex = Math.floor(Math.random() * squares.length);
            if (randomIndex != 0 && player.square != randomIndex) {
                squares[randomIndex].classList.add("active");
            }
            else {
                makeActive();
            }
        }
```


## ⛏️ Built Using <a name = "built_using"></a>
- [HTML] - Programming Language
- [CSS] - Programming Language
- [JavaScript] - Programming Language
- [Atom] - Text Editor

## License

🌱 MIT 🌱
