### Convert inline-block to flex

Flex is better suited to laying out columns compared to inline-block display properties.

From:
```
.columns {}

.column {
  width: 33.3%;
  display: inline-block;
}
```

To:
```
.columns {
  display: flex;
}

.column {
  flex: 1;
}
```

Why?

- Flex auto adjusts to any amount of columns.
- Flex is more (flex)ible, verticle layouts, rows, columns etc...
