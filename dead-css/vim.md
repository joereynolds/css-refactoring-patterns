# Vim

When the CLI seems a bit too heavyweight, I like to go into Vim and do more fine-tuned refactoring.

#### Refactoring regexes

(Note: All these regexes assume CSS, not Less or Sass or any other thing that does weird stuff to your beautiful CSS.)


Sometimes people comment out code and then just forget to remove it.
Let's highlight them (The comments, not the people).
```

```

Or you can use a vim motion too!
The below will take you to the next 'c-style' comment.
See `:help ]/`
```
]/
```

Regex for empty rule goes here
```

```

Regex for duplicate rule in a selector goes here    
```

```

Regex for 0px|em etc... goes here   
```

```
