basic-lens
=====

Necessary type and functions for basic lens work.

Handy to depend on for libraries and general light-weight use,
including PITA environments, old GHCs and non-GHC implementations with
Rank-N type support. Depends only on base.

Provides only:

``` haskell
type Lens s t a b
view :: Lens s t a b -> s -> a
set :: Lens s t a b -> b -> s -> t
over :: Lens s t a b -> (a -> b) -> s -> t
```
