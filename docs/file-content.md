The content of files in the ark will mostly be rolons, 
but we should allow for other types of files as well.
The easiest way to do this is by either path name or file extension.

Now a rolon may have multiple items that we need to track over time.
By ensuring that each item within a rolon is on its own line,
we can easily filter the commits without having to recreate the entire 
file state for each change.
This also means that line order within a rolon file should not be significant.
However this can get ugly if we want to deal with multi-line text. 
