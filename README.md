basic-lens
=====

Necessary type and functions for basic lens work.

Handy to depend on for libraries and general light-weight use, for
people happy with regular Haskell who *sometimes* want to do composable/first-class
update, but mostly don't need it.

Provides only:

``` haskell
type Lens s t a b
view :: Lens s t a b -> s -> a
set :: Lens s t a b -> b -> s -> t
over :: Lens s t a b -> (a -> b) -> s -> t
field :: Name -> Q Exp
```

Example:

``` haskell
λ> data Person = Person { personChar :: Char, personAge :: Int } deriving Show
λ> view $(field 'personChar) (Person 'a' 10)
'a'
λ> over $(field 'personAge) (*2) (Person 'a' 10)
Person {personChar = 'a', personAge = 20}
λ>
```
