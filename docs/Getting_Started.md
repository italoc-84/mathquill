# Download and Load

Download [the latest release](https://github.com/mathquill/mathquill/releases/latest).
MathQuill depends on [jQuery 1.4.3+](http://jquery.com) and we recommend that you use the [Google CDN-hosted copy](http://code.google.com/apis/libraries/devguide.html#jquery).

Then you can load MathQuill with something like (order matters):
```html
<link rel="stylesheet" href="/path/to/mathquill.css"/>
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
<script src="/path/to/mathquill.js"></script>
```

To use the MathQuill API, load it with:
```javascript
var MQ = MathQuill.getInterface(2);
```

All [API methods](http://mathquill.readthedocs.org/en/latest/Api_Methods/) will be called on `MQ`.

You can also [build from the source code](http://mathquill.readthedocs.org/en/latest/Contributing/#building-and-testing).

# Basic Usage

MathQuill instances can be created on HTML elements. For the full list of constructors and API methods, see [API Methods](http://mathquill.readthedocs.org/en/latest/Api_Methods).

The below examples assume that MathQuill has been properly loaded and exposed as `MQ` as shown [above](http://mathquill.readthedocs.org/en/latest/Getting_Started/#download-and-load).

## Render Static Math

Call `MQ.StaticMath` on the HTML element.
```html
<p>Solve <span id="problem">ax^2 + bx + c = 0</span></p>

<script>
  var problemSpan = document.getElementById('problem');
  MQ.StaticMath(problemSpan);
</script>
```

## Editable Math

To create an editable math field, call `MQ.MathField` with the HTML element and the [config](http://mathquill.readthedocs.org/en/latest/Config/). The following example shows a mathfield created on the answer span with a handler to check the answer every time an edit may occur.
```html
<p><span id="answer">x=</span></p>

<script>
  var answerSpan = document.getElementById('answer');
  var answerMathField = MQ.MathField(answerSpan, {
    handlers: {
      edit: function() {
        var enteredMath = answerMathField.latex() // Retreive entered math in LaTeX format
        checkAnswer(enteredMath);
      }
    }
  });
</script>
```

## Get and Set Math

The recommended way to retrieve and store the contents of the math field is to call `mathField.latex()`. `mathField.html()` can be used to retreive the contents of the mathField as static HTML.

A mathField will be initiallized with the text that was in the span, interpreted as LaTex. This can be updated later by calling `mathField.latex(latexString)`. Content can be added as it would be by someone typing with [`typedText()`](http://mathquill.readthedocs.org/en/latest/Api_Methods/#typedtexttext), 

# Join the Community

<big>[<img alt="slackin.mathquill.com" src="http://slackin.mathquill.com/badge.svg" align="top">](http://slackin.mathquill.com)
[<img alt="freenode irc: #mathquill" src="https://img.shields.io/badge/%20freenode%20irc%20-%20%23mathquill%20-brightgreen.svg" align="top">](http://webchat.freenode.net/?channels=mathquill)</big>