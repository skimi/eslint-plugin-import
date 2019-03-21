Had to fork to hardcode `$core` alias as being internal.

Other solutions would be that `eslint` could successfully parse webpack 4 config.
We are not there yet.

Also was able to configure `import/order` so it thought `$core` was a type `builtin`.
It works with:

*.eslintrc*
```
{
  // rules and stuff above
  "settings": {
    "import/core-modules": ["$core"]
  }
}
```

The problem is that there is a bug with `prettier-eslint` that ignores the settings.
https://github.com/prettier/prettier-eslint/issues/181

