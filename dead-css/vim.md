# Vim

When the CLI seems a bit too heavyweight, I like to go into Vim and do more fine-tuned refactoring.

#### Refactoring regexes

(Note: All these regexes assume CSS, not Less or Sass or any other thing that does weird stuff to your beautiful CSS.)


##### Commented out code

Sometimes people comment out code and then just forget to remove it.
Let's highlight them (The comments, not the people).
```
/\/\*
```

Or you can use a vim motion too!
The below will take you to the next 'c-style' comment.
See `:help ]/`
```
]/
```

##### Selectors with no rules   

Regex for empty rule goes here
```

```

##### Duplicate rules in selectors

Regex for duplicate rule in a selector goes here    
```

```

##### Selectors with one rule

```
/{.*\n.*\n}
```

Or more specifically
```
/{\n*\sbackground.*\n}
```



##### 0 unit detection

```
/\<0\(px\|em\|rem\)
```

Replacing with confirmation:
```
:%s/\<0\(px\|em\|rem\)/0/gc
```
