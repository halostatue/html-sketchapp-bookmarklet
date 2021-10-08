# html-sketchapp Bookmarklet

Based entirely on [html-sketchapp-example]. Use this bookmarklet to use
[html-sketchapp] to capture the HTML of a webpage as a Sketch.app page in the
clipboard.

## Code:

```javascript
d = document
s = d.createElement('script')
s.src = 'https://cdn.jsdelivr.net/gh/halostatue/html-sketchapp-bookmarklet@main/page2layers.bundle.js'
s.type = 'text/javascript'
s.onload = function() {
  navigator.clipboard
    .writeText(JSON.stringify(page2layers.run()))
    .then(function() {
      alert('asketch copied to clipboard')
    })
}
d.body.appendChild(s)
```


```html
<a
  href="javascript:d=document,s=d.createElement('script'),s.src='https://cdn.jsdelivr.net/gh/halostatue/html-sketchapp-bookmarklet@main/page2layers.bundle.js',s.type='text/javascript',s.onload=function(){navigator.clipboard.writeText(JSON.stringify(page2layers.run())).then(function(){alert('asketch copied to clipboard')})},d.body.appendChild(s)"
  >html-sketchapp bookmarklet</a
>
```

## Manually Add Bookmarklet

1. Create a bookmark in your browser.
2. Edit the bookmark so that the title is what you want (`html-sketchapp` is
   recommended).
3. Edit the bookmark so the URL reference is the following JavaScript line:

```javascript
javascript:d=document,s=d.createElement('script'),s.src='https://cdn.jsdelivr.net/gh/halostatue/html-sketchapp-bookmarklet@main/page2layers.bundle.js',s.type='text/javascript',s.onload=function(){navigator.clipboard.writeText(JSON.stringify(page2layers.run())).then(function(){alert('asketch copied to clipboard')})},d.body.appendChild(s)
```

## Build

1. Clone [html-sketchapp-example].
2. `npm i`
3. `npm run build`
4. Put `dist/build/page2layers.bundle.js` in this repository.
5. Commit.
6. Push.

[html-sketchapp-example]: https://github.com/html-sketchapp/html-sketchapp-example
[html-sketchapp]: https://github.com/html-sketchapp/html-sketchapp
