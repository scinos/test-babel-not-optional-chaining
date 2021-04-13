#  Optional chaining bug in @babel/preset-env

## To reproduce

Run

```
npm install
npm run build
```

## Expected result

`dist/index.js` contains `?.`

## Actual result

`dist/index.js` is transpiled down to not use `?.`

## Fixes

### Fix 1

Downgrading these packages produces the expected result:

    * `@babel/preset-env@7.13.15` to `@babel/preset-env@7.13.10`
    * `@babel/compat-data@7.13.15` to `@babel/compat-data@7.13.11`

### Fix 2

Changing `.browserslistrc` form `Chrome 88` to `Firefox 88` produces the expected result.
