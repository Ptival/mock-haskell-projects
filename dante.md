# Setup (November 2019)

- MacOS
- nix
- Using DOOM emacs w/ dante

# Results

01: A simple project
--------------------

😊
Mostly happy, the project works.  However, jumping-to-definition on symbols
from non-local libraries (say, the Prelude) does nothing.

02: Haskell project in project's subdirectory
---------------------------------------------

😊
Same as above.

03: Project with multiple targets
---------------------------------

😩
Sadly, dante needs help figuring out what target to load.  One can specify
dante-target using an emacs directory local variable, it's a little bit
annoying but not a major issue.

04: Project with multiple library components
--------------------------------------------

😩
Same as above, needs help figuring out the target.

05: Project in a Git submodule
------------------------------

😩
Dante does a decent job at not confusing the two projects.  However, it does
not seem to let me jump from an occurrence in the outer project to its
definition in the submodule.

06: Project with default extensions
-----------------------------------

😢
Dante seems completely oblivious to default extensions.
