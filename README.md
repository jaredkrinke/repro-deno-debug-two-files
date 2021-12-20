# Steps to reproduce
1. Open in VS Code
1. Put breakpoints on the `console.log` lines in *both* `one.test.ts` and `two.test.ts`
1. Fit F5 to start debugging with the provided `launch.json`
1. Hit the first breakpoint
1. Hit F5 to continue to the next breakpoint

# Expected
The next breakpoint should be hit.

# Actual
Debug session ends.

Note: I always hit the same breakpoint, and it's in the file that comes first alphabetically, so I suspect Deno is enumerating the files and running them sequentially in separate contexts, but for whatever reason, I can only debug the first context.

# Workaround
To debug a particular test, just add that test's file name to the arguments in `launch.json`.
