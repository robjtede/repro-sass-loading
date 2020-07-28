# Reproduction Repo - Angular Sass Loading

## Expected Behavior
Run `npm run build`: build succeeds.


## Current Behavior
Run `npm run build`: error.

```
ERROR in ./src/styles.scss (./node_modules/css-loader/dist/cjs.js??ref--14-1!./node_modules/postcss-loader/src??embedded!./node_modules/resolve-url-loader??ref--14-3!./node_modules/sass-loader/dist/cjs.js??ref--14-4!./src/styles.scss)
Module build failed (from ./node_modules/sass-loader/dist/cjs.js):
SassError: Invalid CSS after "...@include sample": expected "}", was ".yellowBg;"
        on line 4 of .../repro-sass-loading/src/styles.scss
>>     @include sample.yellowBg;

   -------------^
```

## Notes
Running `npm uninstall ngx-markdown` and rebuilding, it works.

Using `npm ls sass-loader sass node-sass` shows the relevant packages installed.

As shown, `ngx-markdown` does not even have to be used. Simply the fact that it is installed and
has an indirect dependency on `node-sass` is enough for the build to fail.
