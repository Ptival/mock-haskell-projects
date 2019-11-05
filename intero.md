# Setup (November 2019)

- MacOS
- nix
- Using DOOM emacs w/ intero

# Results

01: A simple project
--------------------

👏😊
Works great! Even "jumping to definition" on library identifiers lets us know
which file from what Hackage package the symbol comes from.

02: Haskell project in project's subdirectory
---------------------------------------------

👏😊
Equally good.

03: Project with multiple targets
---------------------------------

👏😊
Equally good.

04: Project with multiple library components
--------------------------------------------

😩
Sadly, whenever the project is not-yet-built, or currently not type-checking,
intero won't be able to load properly:

<command line>: cannot satisfy -package z-project-z-internal
    (use -v for more information)

It works otherwise, and as long as it's loaded, it will stay loaded, but it
does not handle library components nicely in the absence of an existing build.

05: Project in a Git submodule
------------------------------

👏😊
Excellent work.  One can jump to definition from the outer module to the
submodule, it works seamlessly!

06: Project with default extensions
-----------------------------------

👏😊
Works great!
