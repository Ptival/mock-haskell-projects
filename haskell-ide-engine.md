# Setup (November 2019)

- MacOS
- nix
- Using all-hies (not bios)
- Using DOOM emacs w/ lsp and (haskell +lsp)

# Results

## MacOS + nix + emacs + haskell-ide-engine (November 2019)

01: A simple project
--------------------

😊
Mostly happy, the project works.  However, jumping-to-definition on symbols
from non-local libraries (say, the Prelude) does nothing.

02: Haskell project in project's subdirectory
---------------------------------------------

😢
LSP starts from the project root, so haskell-ide-engine cannot find the
project!

LSP :: Guessed project root is ~/[...]/02-in-subdirectory/
LSP :: Connected to [hie:22252 status:starting].
LSP :: hie has exited (exited abnormally with code 1)

03: Project with multiple targets
---------------------------------

😊
Seems to work fine!  One can jump to definition from a variable in the
executable directory to its definition in the lib directory.

04: Project with multiple library components
--------------------------------------------

😊
Seems to work fine!  One can jump to definition from a variable in the
executable directory to its definition in the lib or internal directory.

05: Project in a Git submodule
------------------------------

😢
When opening fiel from outer directory, the type-checker works fine, but one
cannot jump to the definitions from the submodule.

When opening file from subdirectory, LSP starts in the submodule directory, so
it cannot find the configuration in the outer package.

LSP :: Guessed project root is ~/[...]/05-in-submodule/submodules/mock-haskell-project-01/
LSP :: Connected to [hie:41067 status:starting].


06: Project with default extensions
-----------------------------------

😩
I get a transient error message about the GADT syntax in ExposedModule.  But
the message quickly goes away.
