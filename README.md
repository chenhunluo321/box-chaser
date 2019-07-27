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

## 🎈 Code Walk Through
```html
        .gameArea {
            width: 800px;
            height: 600px;
        }

        .score {
            font-size: 3em;
        }

        .box {
            position: absolute;
            width: 100px;
            height: 100px;
            background-color: red;
        }

        .square {
            position: relative;
            border: 1px solid #ddd;
            width: 98px;
            height: 98px;
            display: inline-block;
            text-align: center;
            vertical-align: middle;
            line-height: 100px;
            font-size: 24px;
            color: #ddd;
        }

        .active {
            background-color: green;
            color: white;
        }

```

## ⛏️ Built Using <a name = "built_using"></a>
- [HTML] - Programming Language
- [CSS] - Programming Language
- [JavaScript] - Programming Language
- [Atom] - Text Editor

## License

🌱 MIT 🌱
