# GinvLabRegistry

Registry for the G⁻¹Lab suite.

## Add the registry to Julia

Go into package mode from the REPL with `]`, then 
```
pkg> registry add https://github.com/Ginvlab/GinvLabRegistry
```

## Register a package

Example with the package "MyPackage". First "MyPackage" **must live in a git working copy, e.g. having been cloned by Pkg.develop**, so that it appears in the `Pkg.status()` list. To register it using `LocalRegistry`, do 
```
using LocalRegistry
register("MyPackage", registry="LOCAL/PATH/TO/GinvLabRegistry/", repo="https://github.com/GinvLab/MyPackage.jl")
```

If the push phase fails, one can try 
```
register("MyPackage", registry="LOCAL/PATH/TO/GinvLabRegistry/", repo="https://github.com/GinvLab/MyPackage.jl", push=false)
```
and then perform the push from the local git repo containing the updated register.

## Update a package

Similar to registering a package:
```
using LocalRegistry
register("MyPackage", registry="LOCAL/PATH/TO/GinvLabRegistry/")
```
