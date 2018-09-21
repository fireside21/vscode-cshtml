# HTML (C#)

[![][badge-version]][marketplace]
[![][badge-installs]][marketplace]

This extension is a port of the [HTML (C#)][st-package] extension for [Sublime Text][st]. It provides syntax highlighting for HTML files with embedded C#, such as `.aspx`, `.cshtml`, and `.master`.

## Features

### Highlighting

- Embedded C# (`<script runat="server">`)
    + The `runat="server"` must immediately follow the tag opening.

- Comment blocks (`<%-- foo --%>`)

- The `Response.Write` expressions (`<%=`, `<%#`, `<%:`, `<%$`)

### Functionality

- Toggle comment (<kbd>Ctrl</kbd>+<kbd>/</kbd> or <kbd>Cmd</kbd>+<kbd>/</kbd>)

- Snippets for `<%` expressions (Try typing `e=`.)
    + These are subject to change.

- Snippets for some directives (Try `page` or `import`.)
    + Default attributes are subject to change.

## Requirements

- An enabled language grammar for `text.html.basic`. (This is standard in VS Code. Unless you have disabled it, you are fine.)

<!--
## Extension Settings

There are currently no settings.
-->

## Known Issues

### Inline code blocks

Blocks of `<% %>` are not highlighted. They should not interfere with other sections of code. Highlighting _would_ work for self-contained blocks, but not for blocks containing unclosed braces (`<% if (condition) { %>`). Since those blocks are potentially destructive to highlighting for _the rest of the file,_ the C# syntax is not injected into those contexts. It is impossible to determine whether a certain block contains unbalanced braces when deciding whether to inject the C# syntax.

This behavior stems from [VS Code issue #20488][vscode-20488] wherein the syntax engine eagerly expects a closing brace that does not appear until after the `%>`. You can observe the same issue in the HTML syntax. Open a new VS Code tab, set it to the HTML syntax, and add this content:

``` html
<style>
    h1 {
</style>
<p>Still in CSS mode</p>
```

### Files use the "Plain Text" icon

Unless you use a custom icon theme, files highlighted by this package will use the Plain Text icon. [VS Code issue #14662][vscode-14662] would allow package authors to designate icons for their packages without releasing a comprehensive icon theme.

### Bracket matching

Because `<%=` and other constructs share the same closing sequence (`%>`) as `<%` has, when your cursor is on the closing sequence, the opening sequence will only mark the `<%` part, even if the next character is also part of the expression.

## Release Notes

See the [change log][changelog].

## To-Do

- Inject custom tag attribute for `runat="server"`
- Consider namespaced tags to be legitimate. Perhaps even specially identify `asp`-namespaced tags.

[marketplace]: https://marketplace.visualstudio.com/items?itemName=fireside21.cshtml

[badge-version]: https://vsmarketplacebadge.apphb.com/version-short/fireside21.cshtml.svg
[badge-installs]: https://vsmarketplacebadge.apphb.com/installs-short/fireside21.cshtml.svg
[badge-rating]: https://vsmarketplacebadge.apphb.com/rating-short/fireside21.cshtml.svg

[st-package]: https://packagecontrol.io/packages/HTML%20%28C%23%29
[st]: https://www.sublimetext.com/

[vscode-20488]: https://github.com/Microsoft/vscode/issues/20488
[vscode-14662]: https://github.com/Microsoft/vscode/issues/14662

[changelog]: https://github.com/fireside21/vscode-cshtml/blob/master/CHANGELOG.md
