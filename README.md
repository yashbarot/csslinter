# Css linter using gulp-stylelint

following are the steps to getting started

```
npm init
```

```
npm install gulp --save-dev
```

```
npm install gulp-stylelint --save-dev
```

```
npm install stylelint-config-standard --save-dev
```

Sample gulp script `gulpfile.js`
```
const gulp = require('gulp');

gulp.task('lint-css', function lintCssTask() {
  const gulpStylelint = require('gulp-stylelint');

  return gulp
    .src('src/**/*.css')
    .pipe(gulpStylelint({
      failAfterError: true,
      reportOutputDir: 'reports/lint',
      reporters: [
        {formatter: 'verbose', console: true},
        {formatter: 'string', save: 'report'}
      ],
      debug: true
    }));
});
```
Following are the stylint standard rules with custom included `.stylelintrc`
```
{
  "extends": "stylelint-config-standard",
  "rules": {
    "color-hex-case": "lower",
    "color-named": "never" ,
    "color-no-invalid-hex": true,
    "font-weight-notation": "numeric",
    "function-calc-no-unspaced-operator": true,
    "function-comma-newline-after": "never-multi-line",
    "function-comma-space-after": "always",
    "function-comma-space-before": "never",
    "function-linear-gradient-no-nonstandard-direction": true,
    "function-name-case": "lower",
    "function-parentheses-newline-inside": "never-multi-line",
    "function-parentheses-space-inside": "never",
    "function-url-data-uris": "never",
    "function-url-no-scheme-relative": true,
    "function-url-quotes": "always",
    "function-whitespace-after": "always",
    "number-leading-zero": "never",
    "number-no-trailing-zeros": true,
    "string-no-newline": true,
    "string-quotes": "single",
    "time-no-imperceptible": true,
    "unit-case": "lower",
    "unit-no-unknown": true,
    "value-keyword-case": "lower",
    "shorthand-property-no-redundant-values": true,
    "property-case": "lower",
    "property-no-unknown": true,
    "declaration-bang-space-after": "never",
    "declaration-bang-space-before": "always",
    "declaration-colon-newline-after": "always-multi-line",
    "declaration-colon-space-after": "always",
    "declaration-colon-space-before": "never",
    "declaration-empty-line-before": "never",
    "declaration-no-important": true,
    "declaration-block-no-duplicate-properties": true,
    "declaration-block-no-ignored-properties": true,
    "declaration-block-no-redundant-longhand-properties": true,
    "declaration-block-no-shorthand-property-overrides": true,
    "declaration-block-semicolon-newline-after": "always",
    "declaration-block-single-line-max-declarations": 1,
    "declaration-block-trailing-semicolon": "always",
    "block-closing-brace-empty-line-before": "never",
    "block-no-empty": true,
    "block-no-single-line": true,
    "block-opening-brace-newline-after": "always"
  }
}
```

## References
- https://github.com/stylelint/stylelint
- https://github.com/olegskl/gulp-stylelint
- https://github.com/stylelint/stylelint-config-standard