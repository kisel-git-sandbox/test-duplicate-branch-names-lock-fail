# test-duplicate-branch-names-lock-fail

Lock-fail errors on Windows due to NTFS is unable to create refs with such names:

- foobar
- Foobar

This happens when users fix the case.
  
- Feature/bugfix123
- feature/bugfix123

