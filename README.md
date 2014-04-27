## Synopsis

**Go Projectile** is a set of Go language related add-ons for
the Emacs [Projectile](http://batsov.com/projectile/) mode.

## Configuration

```lisp
(require 'go-projectile)
```

## Usage

After running `projectile-switch-project` (<kbd>C-c p s</kbd>) the features of
`go-projectile` will be (optionally) enabled.

### Managing GOPATH

Rather than have a global GOPATH set in your .bashrc or similar, go-projectile
makes it easier for each project to have their own GOPATH automatically
configured.  Upon switching to a projectile project, the GOPATH enviroment
variable will be set appropriately, see `go-projectile-switch-gopath`.
The `go-projectile-set-gopath` function can also be called directly, without
using `projectile-switch-project`.

### Importing projects

Create a new projectile project via `go-projectile-get` (<kbd>C-c p N</kbd>).
This function will 'go get' an existing repo and switch to the new project.

### Refactoring

Very basic refactoring is made available via `go-projectile-rewrite` (<kbd>C-c p W</kbd>).
It is just a wrapper around `gofmt -r`, where go-projectile tries to help
generate the rewrite pattern based on the cursor's location.  The rewrite rule
will only apply to '*.go' files in the current project, excluding patterns
listed in `go-project-files-ignore'.