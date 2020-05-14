# D Tips

## multiple assign like

```d
import std.meta : AliasSeq;
import std.typecons : tuple;

string x, y;
AliasSeq!(x, y) = tuple("x", "y");
assert(x == "x");
assert(y == "y");
```
