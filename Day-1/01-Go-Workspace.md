# Key Concepts

## Go Workspace
- The *GO workspace* is a special folder where Go stores external tools and their source code.
- By default, the workspace is at `$HOME/go` on Unix-like systems, or `%USERPROFILE%\go` on windows.
- you are free to organize your own go projects as you like  there are no strict requirement anymore.

## Environment Variables
- **GOPATH :** Tells Go where the workspace is. Explicitly setting this variable helps avoid confusion about where tools and code are stored.
- **PATH :** Adding `$GOPATH/bin` or `%USERPROFILE%\go\bin` on windows to your `PATH` makes sure you can easily run Go tools from the command line.
- To Set these variables:
    * On Unix like systems, add two lines tou your `.profile` (or `.zshrc` for zsh users):
    ```bash
    export GOPATH=$HOME/go
    export PATH=$PATH:$GOPATH/bin
    ```
    Then run
    ```bash
    source $HOME/.profile
    ```

    * On Windows, use these commands in command prompt:
    ```
    setx GOPATH %USERPROFILE%\go
    setx path "%path%;%USERPROFILE%\go\bin"
    ```
    Afterward, close and reopen Command prompt.

## Getting Third party Tools
- tools installed via `go install` go into the workspace you specified.
- Putting the workspace's `bin` folder (where the binaries land) in your `PATH` means you can run theese tools from anywhere.

## Other Environment Variables
- The `go env` command lists all Go-related variables (most aren't important for beginners).
- You do not need to set the `GOROOT` variable; Go automatically finds this nowadays.


