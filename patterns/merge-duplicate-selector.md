### Merge duplicate selectors

If a selector exists (unintentionally) in multiple places, combine them together.

From:
```
#my-selector {
  padding: 5px;
}

/* Lots more rules */

#my-selector {
  width: 25px;
}

```

To:
```
#my-selector {
  padding: 5px;
  width: 25px;
}
```

Why?

Duplicate selectors are very rarely intentional. In the case of an ID it's definitely a mistake.
Combine them so your rule sits in one place.
