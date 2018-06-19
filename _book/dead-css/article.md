# Dead CSS  


## Removing
### What is safe to remove?


#### Children of unused selectors

If you know `#shiny-table` is unused, then you can also remove rules like

```
#shiny-table h3
```

or

```
#shiny-table.table
```

etc...

Since the class doesn't exist, there won't be any children either.
