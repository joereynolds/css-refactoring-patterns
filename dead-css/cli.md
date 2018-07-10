# CLI

Using the CLI, you can get a huge reward for very little effort.


## Finding and replacing with `sed`

**Replacing 0px (and others) with 0**
(Note this replaces in place, run if you know what you're doing')
```
sed -ir 's/0(px|em)/0/g' file.css
```

**NOTE:**

While `sed` can't offer you a confirmation prompt before each change,
you can easily achieve similar functionality in your git repository with `git add -p`.

## Hunting down selectors with `git grep`

### In CSS

If you want to gather all classes and ids for a file, you can do something along the lines of

```
git grep -E '^#|^\.' yourcssfile.css
```

Save that somewhere before your refactoring so you can marvel at how much you've improved it afterwards.

### In HTML 

Since HTML is pretty dumb, 99% of the time, you can get away with an exact string search excluding the `#` or `.`.
For example, if we want to find all usages of the `.table-cell` selector, we would search for `table-cell`.

```
git grep table-cell
```

## Finding dead CSS with `mort`

Mort was written by yours truly and is capable of doing naive string searches to help detect dead CSS.

Check the [github repository](https://github.com/joereynolds/mort/) for examples of usages and installation but basically, you can do  

```
mort -f your/css/file.css
```

and it will display all dead css in that `file.css`

## Watch changes with `entr`

Made a change and now you want to run `grep`, `mort`, and `sed`?

Use `entr`, a file watcher built on top of `inotify` that triggers an action whenever the specificed file has changed.

It's very "unixy" and has a simple interface that we're all familiar with.

Examples:

**Rescan for dead css**

```
echo "static/css/base-style.css" | entr mort -vf /_
```

### Versioning your watchers

If you're hopping from machines often or you're just one of those cave-dwelling dotfile people (I am)
then you'll be pleased to know it's possible to version your `entr` watches.

If you download [entree](https://github.com/joereynolds/entree) and follow the instructions you'll be up and running (with tab-completion) in no time!
