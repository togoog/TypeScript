# TypeScript
TypeScript is a superset of JavaScript that compiles to clean JavaScript output.  http://www.typescriptlang.org

**Beyond Handbook && Latest features**

* [元组类型 - Tuple Types](./doc/tuple_types.md) (TypeScript 1.3) 
* [受保护的成员 - Protected members](./doc/protected.md) (TypeScript 1.3) 

**TypeScript Handbook**

* Read [TypeScript Handbook (Recommended)](http://www.typescriptlang.org/Handbook)
* Read [TypeScript 手册 (翻译完成)](./doc/Handbook.md)

**TypeScript Language Specification**

* Read [TypeScript Language Specification (Recommended)](https://github.com/Microsoft/TypeScript/blob/master/doc/spec.md)
* Read [TypeScript 语言规范 (译完第一章)](./doc/TypeScript Language Specification.md)

I'd love for you to contribute to the translation:)

## Using Gulp with TypeScript

Install `gulp` and `gulp-typescript`. See [package.json](./package.json).

```sh
$ npm install --global gulp
$ npm install --save-dev gulp gulp-typescript
```

Config gulp. See [gulpfile.js](./gulpfile.js).

```js
gulp.task('typescript', function() {
  var tsResult = gulp.src('ts/*.ts')
    .pipe(ts({
      target: 'ES5',
      declarationFiles: false,
      noExternalResolve: true
    }));

  tsResult.dts.pipe(gulp.dest('dist/tsdefinitions'));

  return tsResult.js.pipe(gulp.dest('dist/typescript'));
});
```
