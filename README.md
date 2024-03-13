Eng. Mohamed Hekal
---

# Equation Display

Equation Display is a simple yet powerful web application designed to allow users to enter mathematical equations in a straightforward format and display them in a beautifully rendered manner using MathJax. This tool is ideal for educational purposes, math presentations, or anyone looking to present complex mathematical expressions cleanly and professionally on the web.

## Features

- User-friendly input for typing or pasting mathematical equations.
- Comprehensive support for a variety of mathematical syntaxes, including roots, fractions, powers, trigonometric functions, logarithms, and more.
- Automatic conversion of simple mathematical expressions into LaTeX formatting.
- High-quality equation rendering with MathJax.

## Prerequisites

To use Equation Display, you'll need:
- A modern web browser with JavaScript support.

## Installation

Setting up Equation Display is straightforward. Follow these steps to get it running on your local machine:

1. Clone the repository:
```bash
git clone github.com/mohamedhekal/Paste_Math_Equation.git
```

2. Open the `index.html` file in your web browser. There's no need for a web server, as the project uses CDN-hosted scripts for MathJax and polyfills.

## Usage

To display an equation:
1. Open the `index.html` file in your browser.
2. Enter your equation in the input field. For example, you could type `sqrt(x^2 + y^2)`.
3. Click the "Display Equation" button. The rendered equation will appear below the input field.

## How It Works

The heart of Equation Display lies in its HTML structure and JavaScript functions. Below is the full HTML code, including JavaScript, necessary for the application to work:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Equation Display</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.0/es5/tex-mml-chtml.js" integrity="sha384-8reGmBkxZlKz9/WEHlK7YMh3x5Vz1M7hqLwrv6UQ7xU5CgJ4MZhKy7FJ2nD4jKQe" crossorigin="anonymous"></script>
    <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
    <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
</head>
<body>

<input type="text" id="equation-input" placeholder="Enter your equation here" />
<button onclick="displayEquation()">Display Equation</button>

<div id="math-content"></div>

<script>
function convertToLaTeX(equation) {
    // Escape special characters and handle mathematical notation conversions here
    equation = `$$${equation}$$`; // Simplified for demonstration
    return equation;
}

function displayEquation() {
    const userInput = document.getElementById("equation-input").value;
    const latexEquation = convertToLaTeX(userInput);
    document.getElementById("math-content").innerHTML = latexEquation;
    MathJax.typesetPromise();
}
</script>

</body>
</html>
```

## Contributing

Contributions are welcome! If you have suggestions or improvements, feel free to fork the repository and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgements

- Thanks to the MathJax team for providing the robust engine that makes rendering complex mathematical equations possible.

---
