This is a collection of mock projects that use each some specific feature of
the Haskell ecosystem.

I'd expect language tools to handle all such cases gracefully.

# What do I test?

For each project, I try to open the files in each subdirectory, and make sure
that they type-check (making sure that the proper libraries are loaded for the
proper targets).  I make sure to break the type-checking, because some
type-checkers just say "everything is fine" when they are broken.

Finally, I also like to make sure that my editor is aware of scoping.  So I try
to "jump to the definition" of some variables, either from the same file, from
another file in thi project, or from some external library that we don't have
the code of.

# What to take out of this?

This is not meant to point fingers at "worse" plugins.  Rather, I hope to point
fingers at plugins that do particularly great things, so that the other plugins
can integrate such features.

As such, I don't want any rating, so I use some silly emojis to indicate my
feeling when using the inspected editor tool.  Please open an issue if you feel
like I've missed an important point or am misrepresenting some tool.  I'd love
to be proven wrong!

# Mock projects

01: A simple project
--------------------

Nothing special about this.  One library, most simple project structure.

02: Haskell project in project's subdirectory
---------------------------------------------

This time around, the cabal file is not at the root of the Git repository.  I
thought this would never be a problem, but sometimes dante could not handle
this correctly, so apparently it is a valid concern.

03: Project with multiple targets
---------------------------------

For the sake of testing, a project with both a library and an executable.
Ideally, the editor plugin would know which target to load in what context.

04: Project with multiple library components
--------------------------------------------

A project with an internal, named library, and a main anonymous library.
Again, the editor plugin should know what to load.

05: Project in a Git submodule
------------------------------

An actual complication, the project contains a copy of another project as a
submodule.  Ideally, one could jump from occurrences of a definition in the
outer module, to its definition site in the submodule.  Additionally, the
submodule should load with its proper context.

06: Project with default extensions
-----------------------------------

A project with default extensions should be loaded properly, so that those
extensions are enabled in all files.

