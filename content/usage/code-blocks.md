---
date: 2016-11-26T20:29:33-06:00
title: Code Blocks
tagline: <i class="fa fa-code" style="font-size:48px;margin-bottom:10px;"></i><br/>Show, don't tell.<br/>JustDocs features beautiful code formatting and syntax highlighting. It also supports tabbed code blocks for showing tasks in different langauges, and the ability to copy code blocks to the clipboard.
menu:
  main:
    parent: usage
weight: 25
prev: /usage/tagline
next: /usage/toc
---

JustDocs uses [highlight.js](https://highlightjs.org/) and Markdown [fenced code blocks](https://help.github.com/articles/creating-and-highlighting-code-blocks/) to show code examples.

## Usage

Simply surround code blocks with three back-ticks, followed by the (optional) language:

<pre>
```javascript
  $(document).ready(function() {
    console.log('Ready!');
  });
```
</pre>

Renders as:

```javascript
  $(document).ready(function() {
    console.log('Ready!');
  });
```

## Supported languages

JustDocs includes all of the standard languages supported by highlight.js, as well as Groovy, Go, and YAML.

If you need additional languages, simply [configure and download](https://highlightjs.org/download/) a custom version, and replace the `themes/hugo-pretty-docs/static/js/highlight.pack.js` file with your downloaded version.

## Tabbed code blocks

You can create tabs for code blocks by using the ``tabs`` and nested `tab` shortcodes.
These are useful for showing code examples in multiple languages.

Here's an example showing how to iterate over an array in different languages:

{{% tabs %}}

{{% tab "JavaScript" %}}
```javascript
var items = [1, 2, 3, 4, 5]
items.forEach(function(item) {
  console.log('item: ' + item);
})
```
{{% /tab %}}

{{% tab "Ruby" %}}
```ruby
array = [1, 2, 3, 4, 5, 6]
array.each {
  |x| puts x
}
```  
{{% /tab %}}

{{% tab "Groovy" %}}
```groovy
def items = [1, 2, 3, 4, 5]
items.each {item ->
  println "item is $item"
}
println "extra line"
```
{{% /tab %}}

{{% /tabs %}}

To use, simply use the `tabs` shortcode with nested `tabs`.
Note that each tab should specify a title for the tab.

```go
{{%/* tabs */%}}
{{%/* tab "Groovy" */%}}
 standard fenced code block here
{{%/* /tab */%}}

{{%/* tab "JavaScript" */%}}
 standard fenced code block here
{{%/* /tab */%}}

{{%/* tab "Ruby" */%}}
 standard fenced code block here
{{%/* /tab */%}}

{{%/* /tabs */%}}
```

## Copy code blocks

As seen in the examples above, the contents of every code block can be copied to the reader's clipboard.
When reading developer documentation, code samples may serve as a jumping-off point, or even as a solution to a specific problem.
Instead of having to manually select and copy the code, readers can just click the Copy button!

## Dark or light theme

By default, JustDocs uses the dark monokai theme.
If you prefer a lighter theme, just change it in your `config.toml`:

```toml
[params]
    # supported values: "monokai", "github"
    codeTheme = "monokai"
```
