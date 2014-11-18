# deft-turbo

deft-turbo is a fork of the Emacs package Deft, originally by Jason
Blevins. See http://jblevins.org/projects/deft/

This fork is by [http://charlbotha.com/](Charl P. Botha)

## Additional features

### Recursive directory listing

The original Deft searches for files with `deft-extension` only in the
top-level `deft-directory`. deft-turbo searches recursively, so that
you can nest your files in arbitrarily deep subdirectories.

### Multiple file extensions

My notes database contains a mix of Markdown .md and Emacs org-mode
.org files. Instead of a single filename extension, deft-turbo allows
you to configure a list of valid extensions.

## Obtaining deft-turbo

You can clone this repo somewhere, and point emacs to it by adding ti
to the load-path.

Alternatively, you can use the following el-get recipe (thanks
https://github.com/stefanv ):

``` emacs-lisp
(setq el-get-sources
      '(
        (:name deft-turbo
         :description "Deft Turbo mode"
         :website "https://github.com/cpbotha/deft-turbo"
         :type github
         :pkgname "cpbotha/deft-turbo"
         :features deft
         :compile "deft.el")
))
```


## Configuration

Add the following to your `init.el`:

``` emacs-lisp
(add-to-list 'load-path "~/where-you-put/deft")
(require 'deft)
(setq deft-extensions '("org" "md"))
(setq deft-default-extension "org")
(setq deft-directory "~/notes/")
(setq deft-use-filename-as-title t)
```
