# highlight-redux

Like highlight.js, but not including every single syntax highlighting grammar. Saving bytes for the browser!

##Sample usage.

Install _both_ highlight-redux and highlight.js (the latter, for the css themes you will need)

```bash
$ npm install highlight-redux highlight.js
```

Write some code in ```<code>``` blocks inside of ```<pre>``` blocks, per [spec](http://www.w3.org/html/wg/drafts/html/master/text-level-semantics.html#the-code-element).

```html
<pre class="highlight-js"><code class="js">var b = "hey";</code></pre>
...


Include the theme you want in your css precompiler language or in your html. Sass example:

```scss
@import 'node_modules/highlight.js/styles/sunburst.css';
```

Turn on highlight.js and have it highlight all code blocks once they load into the dom.

```js

var hljs = require('highlight-redux');
hljs.registerLanguage('javascript', require('highlight-redux/lib/languages/javascript'));
hljs.registerLanguage('css', require('highlight-redux/lib/languages/css'));

window.addEventListener('load', function(){

  //highlight all the highlight.js blocks
  [].slice.call( document.querySelectorAll('pre.highlight-js') ).forEach(function( block, i){

    hljs.highlightBlock( block );

  });

```
