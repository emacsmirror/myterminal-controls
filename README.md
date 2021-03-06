# myterminal-controls

[![MELPA-Stable](http://stable.melpa.org/packages/myterminal-controls-badge.svg)](http://stable.melpa.org/#/myterminal-controls)
[![MELPA](http://melpa.org/packages/myterminal-controls-badge.svg)](http://melpa.org/#/myterminal-controls)
[![Marmalade](https://img.shields.io/badge/marmalade-available-8A2A8B.svg)](https://marmalade-repo.org/packages/myterminal-controls)  
[![License](https://img.shields.io/badge/LICENSE-GPL%20v3.0-blue.svg)](https://www.gnu.org/licenses/gpl.html)

Quick toggle controls at a key-stroke.

![Demo](images/demo.gif)

You can use myterminal-controls to save a lot of key-bindings by grouping them into a single controls window. The controls window can be opened with a key-binding and the rest key-bindings are displayed within the controls window.

## Installation

### Manual

Save the file *myterminal-controls.el* to disk and add the directory containing it to `load-path` using a command in your *.emacs* file like:

    (add-to-list 'load-path "~/.emacs.d/")

The above line assumes that you've placed the file into the Emacs directory '.emacs.d'.

Start the package with:

    (require 'myterminal-controls)

### MELPA-Stable / MELPA / Marmalade

If you have MELPA-Stable, MELPA or Marmalade added as a repository to your Emacs, you can just install *myterminal-controls* with

    M-x package-install myterminal-controls RET

## Usage

Set a key-binding to open the quick-toggle controls window anytime

    (global-set-key (kbd "C-M-`") 'myterminal-controls-open-controls)

You can also set your custom list of quick-toggle controls

    (myterminal-controls-set-controls-data
        (list '("1" "Invert colors"
                (lambda ()
                  (invert-face 'default))
                t)
              '("2" "Invert mode-line"
                (lambda ()
                  (invert-face 'mode-line)))))

Each item in the list should contain 3 to 4 elements:

* Key combination information
* Text to be displayed in the controls window
* Function to be executed against the key combination
* [Optional] Whether the controls window should close after the command
