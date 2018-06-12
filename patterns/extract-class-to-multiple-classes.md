### Extract class to multiple classes

If you're finding a class is very rigid and hard to extend or modify, consider breaking out that
class into multiple classes.

From:
```
.profile-details {
  background-color: #ccc;
  padding: 5px;
  height: 200px;
}

```

To:
```
.faded-background {
  background-color: #ccc;
}

.profile-details {
  padding: 5px;
  height: 200px;
}
```

Why?

Multiple small classes encourage reusability and modularity.

(Beware of going to far and going into 'atomic CSS' territory. We don't use those words in this book.)
