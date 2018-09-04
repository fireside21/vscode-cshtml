# HTML (C#)

This extension is a port of the [HTML (C#)][hcs-st] for [Sublime Text][st] extension. It provides syntax highlighting for HTML files with embedded C#, such as `.aspx`, `.cshtml`, and `.master`.

## Features

### Highlighting

- Embedded C# (`<script runat="server">`)
    + The `runat="server"` must immediately follow the tag opening
- Comment blocks (`<%-- foo --%>`)
- The `Response.Write` expressions (`<%=`, `<%#`, `<%:`, `<%$`)

### Functionality

- Toggle comment (<kbd>Ctrl</kbd>+<kbd>/</kbd> or <kbd>Cmd</kbd>+<kbd>/</kbd>)
- Snippets for `<%` expressions (Try typing `e=`)
    + These are subject to change.
- Snippets for some directives (Try `page` or `import`)
    + Default attributes are subject to change.

## Requirements

- An enabled language grammar for `text.html.basic`. Unless your VS Code set-up is exceedingly novel, you should be fine.

## Extension Settings

There are currently no settings.

## Known Issues

Blocks of `<% %>` do not work. They are currently unhighlighted and should not interfere with other sections of code. This is due to [VS Code issue #20488][vscode-20488] wherein the syntax engine eagerly expects some content that does not appear until after the `%>`.

You can observe the same behavior in a new VS Code tab set to the HTML syntax, and this content:

``` html
<style>
    h1 {
</style>
```

## Release Notes

See [changelog][]

[hcs-st]: https://packagecontrol.io/packages/HTML%20(C%23)
[st]: https://www.sublimetext.com/
[vscode-20488]: https://github.com/Microsoft/vscode/issues/20488
[changelog]: CHANGELOG.md
