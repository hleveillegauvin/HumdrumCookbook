# HumdrumCookbook
How-to recipes to use the Humdrum Toolkit


Written by Hubert Léveillé Gauvin  
leveillegauvin.1@osu.edu

# <a name="table-of-contents"></a> Table of Contents
* [Getting Basic Statistics](#census)
* [Standardizing Enharmonic Spellings](#standard-enharmonic)

### <a name="census"></a> Getting Basic Statistics

__Problem__

You have a collection of kern files and you want a quick statistical summary of its features.

__Solution__

```
census *.krn
```

__Discussion__

Humdrum has a command called `census`, which provides statistical information about Humdrum files. The wildcard character `*` is used to get information about all the `.krn` files in the current directory. The `census` command also has a `-k` option (kern), which provides additional information about individual kern spines:

     census -k *.krn
     
The `census` command can also be used on a single file:

    census melody1.krn
    
But what if we wanted to get stats for every single kern file? We can create a `for loop` to run `census` on every single file. In the example below, We'll also use `echo` to print the name of the file at the beginning of the loop so we know which file the stats correspond to:

```
for i in *.krn; do
    echo
    echo "-----------"
    echo $i
    echo "-----------"
    census -k $i
    echo
done
```

__See Also__

The Humdrum User Guide, [Chapter 4, pp. 20.](http://www.humdrum.org/guide/ch03/#the-census-command)


### <a name="standard-enharmonic"></a> Standardizing Enharmonic Spellings

__Problem__

You want to standardize enharmonic spellings.

__Solution__

```
semits -x melody.krn | kern
```

__Discussion__

Translating our melody to \*\*semits and then back to \*\*kern will standarize all of the enharmonic spellings. The `-x` option is used to eliminate any input data that do not pertain to pitch. As such, this option allows us to filter out durations, articulation marks, phrasing, and other non-pitch data. The `t` option can also be used to suppress printing of all but the first note of a group of tied \*\*ken notes.

__See Also__

The Humdrum User Guide, [Chapter 4, pp. 39-40.](http://www.humdrum.org/guide/ch04/)
