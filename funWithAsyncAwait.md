<!-- @meta
Title: Fun with async/await
Author: Ryan K Harris
Keywords: javascript async
Created: 15Nov2017
Updated: 15Nov2017
Version: 0.3.2
-->


## Summary
I've been playing more with async/await recently as part of some job-hunting take-home exercises and today I incorporated some of what I've learned into [grokblarg](https://github.com/ryankharris/grokblarg) to clean up some of the async code. Still learning how to make it pretty and where and when to blend promises in, but I created [this gist](https://gist.github.com/ryankharris/bf5cd84d31f0ba547fb3e865058154ca) to display some of my personal example code.

To run it locally, I added the following files into the folder it lives in:
- read.md with read/write permission
- writeWithPermission.md with read/write permission
- writeNoPermission.md with (chmod 444) read-only permission

Here is the output I see in console when I `node ./index.js`:


    ------------------------------------------
    read: # Read.md
    Here is some content

    ------------------------------------------
    readFile-error: Error: ENOENT: no such file or directory, open 'fake.md'
    ------------------------------------------
    writeWithPermission: undefined
    ------------------------------------------
    writeFile-error: Error: EACCES: permission denied, open 'writeNoPermission.md'
    ------------------------------------------
    mkdir: undefined
    ------------------------------------------
    mkdir-error: Error: EEXIST: file already exists, mkdir './testDir'
    ------------------------------------------
    await asyncAccess returns undefined when permission checks successfully
    access: undefined
    ------------------------------------------
    await asyncAccess returns error when a tested permission fails or file doesn't exist
    access-error: Error: ENOENT: no such file or directory, access './fake.md'
    ------------------------------------------
    looks like it can be used within an if condition, but be clear on the expected result
    access succeeded in if condition
    ------------------------------------------
    also possible in ternary operator
    access succeeded in ternary operator: true
    ------------------------------------------
    careful not to mix 'async' with normal async-callback. your promise is resolved with undefined
    content: undefined

I haven't seriously explored using an `await` in any conditional and put those examples together quickly out of curiousity. I could easily have overlooked something so none of this is __TRUTH__, use at your own risk.
