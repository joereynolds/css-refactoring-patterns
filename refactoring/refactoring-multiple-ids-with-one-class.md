# Replacing multiple ids with one class 

If you have multiple ids all exhibiting the same behaviour, they should be refactored into one class.
From there you can go on to further refactorings, but baby steps...

An example can be something such as:

```
#notes-table tr {
    height: 25px   
}


/* Loads more CSS */

#brand-settings-form-table th, #brand-settings-form-table td {
    height: 25px;
}
```

As you can see, there's no need for these to be in id's at all, the writers just didn't know (or think).

To combat this, I suggest the following which has served me well (though it can have 1 undesirable (but rare) effect)


##### Find all single rule selectors

Find all the selectors with the same single rule (In this case we're targeting `height: 25px`).
In my case I used a very naive vim search pattern.

```
/height.*25px
```

###### Group rules together

You then want to start consolidating these rules into one mega-rule.
It looks terrible but it's a step in refactoring so relax.

```
#notes-table tr,
.table-box-style tr,
#profile-table th, #brand-profile-table td,
#brand-settings-form-table th, #brand-settings-form-table td,
#new-event-bottom-right .end_c div, #new-admin-bottom-left .end_c div,
#global_setting_main_container th, #global_setting_main_container td,
.generic-table-display tr,
.tabs-wrapper {
    height: 25px;
}
```

###### Refactor to class

Rename the selector to something semantic and remove the old bunch of selectors.

```
.short {
    height: 25px;
}
```

###### Replace all old usages

At this point, you've refactored your many selectors into one and so you're ready to start  
refactoring the HTML and views that use it.

In some cases you don't want to remove all of the ids (javascript might be targeting it etc...).
However, if it's just static HTML, then you should have no problem just doing a search and replace.

Remember to confirm with `git add -p`!

## Caveats

As mentioned before, the caveat is that you're moving styles into one place in the sheet. 
This means the selectors precedence has now changed and could potentially be overriding more or is
being overridden itself.

You'll have to decide yourself if you want to take that risk (hint: I do).
