### Remove !important declarations

If you're using `!important` in places you shouldn't (which is most of the time),
consider increasing the specifity and removing the rule instead.

If possible, just remove `!important` altogether.

From:
```
.bordered {
  border: 1px solid red !important;
}
```

To:
```
.my-special-box .bordered {
  border: 1px solid red;
}
```

Why?

- `!important` is difficult to override and breaks the cascading nature of CSS.
