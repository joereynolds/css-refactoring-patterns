# Removing a selector

If I'm refactoring CSS and my main focus is removing selectors, I go for the following workflow:

1) Run `mort` across the codebase

First I run `mort -f ./static/css/style.css` to get an idea of what **can** be removed.

2) Verify

`mort` isn't perfect, string concatenation will slip through but it's still superior to manually grepping.
Once I've found a selector I want to get rid of, I do a few different greps to make sure it's okay.

For example, if mort brings back

```
0 usages found. #brand-administration-tabs-container can probably be removed.
```

I'll grep for `brand-` and `brand-administration` just to make sure it's not being concatted (or other weird stuff) elsewhere.

3) Remove it 

At this point, it's safe to remove the selector from your stylesheet, delete it and move on.

4) Remove the children

If a dead selector (in our case `brand-administration-tabs-container`) has children, its children can be removed.


i.e.    

```
#brand-administration-tabs-container
{
	position: relative;
	margin-top: 20px;
	width: 1179px;
}

#brand-administration-tabs-container div
{
	width: 150px;
}

#brand-administration-tabs-container div:hover
{
	background-color: #5C8EB3;
	color: #FFF;
}
```

In the above example not only can we remove the main selector, but also the `div` and `div:hover`.
