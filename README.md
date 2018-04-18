# HumdrumCookbook
How-to recipes to use the Humdrum Toolkit


### Standardizing enharmonic spellings

__Problem__

You want to standardize enharmonic spellings.

__Solution__

```
semits -x melody.krn | kern
```

__Discussion__

Translating our melody to \*\*semits and then back to \*\*kern will standarize all of the enharmonic spellings. The `-x` option is used to eliminate any input data that do not pertain to pitch. As such, this option allows us to filter out durations, articulation marks, phrasing, and other non-pitch data. The `t` option can also be used to suppress printing of all but the first note of a group of tied \*\*ken notes.

__See Also__

The Humdrum User Guide, Chapter 4, pp. 39-40.
