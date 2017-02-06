# How to save buffers on Emacs deactivation

I happily used *save files on frame deactivation option* on IntelliJ-based editors. I want to have the same setting on my spacemacs and found Emacs 24.4 adds [focus-hook](https://www.gnu.org/software/emacs/manual/html_node/elisp/Input-Focus.html#Input-Focus). 

To save active buffer when the Emacs frame deactivated, simply add following lines to your .emacs file:

```
(add-hook 'focus-out-hook 'save-buffer)
```

February 5, by deepblue
