# ember-tailwind-postcss-scss

### Dependencies

- @csstools/postcss-sass  
- tailwindcss  
- postcss-import  
- postcss-scss  

### ember-cli-build.js

```javascript
module.exports = function(defaults) {
  let app = new EmberApp(defaults, {
    postcssOptions: {
      compile: {
        extension: 'scss',
        enabled: true,
        parser: require('postcss-scss'),
        plugins: [
          { module: require('@csstools/postcss-sass') },
          { module: require('postcss-import'), options: {
            path: ['node_modules']
          } },
          require('tailwindcss')('./app/styles/tailwind.js')
        ]
      }
    }
  });
```

### app.scss

```css
@import "tailwindcss/base.css";
@import "tailwindcss/components.css";
@import "tailwindcss/utilities.css";

//scss test
$green: #abc123;

.c-header {
  p {
    color: $green;
  }
}
```
