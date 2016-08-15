# Emmet plugin for TextMate 2

This plugin adds [Emmet](http://emmet.io) support for [TextMate 2](http://macromates.com) editor (works on OSX 10.9+ only).

## How to install

* Download `EmmetTextMate.tmplugin.zip` file from [latest release](https://github.com/emmetio/textmate2/releases/latest).
* Unpack downloaded zip file.
* Double-click on `EmmetTextMate.tmplugin` file to install.
 
## Licensing 

Emmet plugin is completely free to use, but to make future development more sustainable, some useful features like Tab expander and Preferences UI are available after a paid upgrade.

## Notes on Tab expander

A lot of TextMate features are bound to Tab key. Unfortunately, current TextMate API does not provide opportunity to register custom Tab key handler (as [Sublime Text](http://www.sublimetext.com) or [Atom](https://atom.io) does). Which means that Emmet’s Tab key hanlder **works mostly as a hack** and may (not intentionally) break default behaviour. But it still tries to play nice with TM’s default handler:

* Emmet’s tab trigger works for limited scopes only since it overrides default snippets. Specifically, it works in HTML, XML, CSS, LESS, Sass/SCSS and Stylus. If you think that it could safely work in other syntaxes, please [create a new issue](https://github.com/emmetio/textmate2/issues) so I can support it.
* Compared to previous implementations, it tries to respect *editable fields* after abbreviation was expanded (e.g. use Tab key to quickly jump and edit different parts in abbreviation output).
* In JavaScript, where default TextMate snippets are more preferable, Tab expander works slightly different: it only handles either complex (nested or with attributes like `ul>li`, `.foo`) or single uppercased (like `Foo`, `Bar`) abbreviations that follow React components definition convention. Although inside string literals (e.g. inside `""` or `''`) it works as usual.
