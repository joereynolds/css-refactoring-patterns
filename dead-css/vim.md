# Vim

When the CLI seems a bit too heavyweight, I like to go into Vim and do more fine-tuned refactoring.

#### Refactoring regexes

Note: All these regexes assume CSS, not Less or Sass or any other thing that does weird stuff to your beautiful CSS.

Also note that all of these regexes are being used in a search `/`.

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

Occasionally you'll come across empty selectors.

The rule below will help highlight any.

```
/{\(\s\|\n\)*\}
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

#### Plugins

##### Quickfix Reflector
There are very few plugins I use in Vim but one that's especially useful for refactoring is the [quickfix reflector](https://github.com/stefandtw/quickfix-reflector.vim)
Allowing you to edit and save the changes of the content in the quickfix list.

For a language that does not have a language server (or any intelligence), this is a perfect fit.
