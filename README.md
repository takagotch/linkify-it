### linkify-it
---
https://github.com/markdown-it/linkify-it

```
npm install linkify-it --save
```

```js
var linkify = require('linkify-it')();
linkify
  .tlds(require('tlds'))
  .tlds('onion', true)
  .add('git:', 'http')
  .add('ftp:', null)
  .set({ fuzzyIP: true });
console.log(linkify.test('Site github.com!'));
console.log(linkify.match('Site github.com!'));
```

```ja
linkidy.add('@', {
  validate: function (text, pos, self){
    var tail = text.slice(pos);
    if(!self.re.twitter){
      self.re.twitter = new RegExp(
        '^([a-zA-Z0-9_]){1,15}(?!_)(?=$|' + self.re.src_ZPCc + ')'
      );
    }
    if(self.re.twitter.test(tail)){
      if(pos >= 2 && tail[pos - 2] === '@'){
        return false;
      }
      return tail.match(self.re.twitter)[0].length;
    }
    return 0;
  },
  normalize: function (match){
    match.url = 'https://twitter.com/' + match.url.replace(/^@/, '');
  }
});
```


