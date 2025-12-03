# test-duplicate-branch-names-lock-fail

Lock-fail errors on Windows due to NTFS is unable to create refs with such names:

- foobar
- Foobar

This happens when users fix the case.
  
- Feature/bugfix123
- feature/bugfix123



## Problem

IT is not possible to create different refs in file structure on Windows,
but this can be done in `.git/packed-refs`

### Source

```
# Following files can be created on Linux/Mac, but we can't do the same on Windows
.git/refs/remotes/origin/Feature/bugfix123
.git/refs/remotes/origin/Feature/bugfix123
```

### Workaround

```
# pack-refs with: peeled fully-peeled sorted 
53a95014dab4647bc2fdf22d1965cef3e827b676 refs/remotes/origin/Feature/bugfix123
327423ce86a119ae963dc3c426c18adecb914817 refs/remotes/origin/feature/bugfix123
327d813b211cf20cbf1b47afb1c7f471d6e61c1b refs/remotes/origin/main
```
