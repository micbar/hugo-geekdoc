Include Shortcode can include files of different types. By specifying a language, the included file will have syntax highlighting.

## Shortcode

```tpl
{{</* include file="relative/path/from/hugo/root" language="go" markdown=[false|true] */>}}
```

Attributes:

| Name | Usage | default |
|---|---|---|
|  file | path to the included file relative to the hugo root | empty value |
| language* | language for [syntax highlighting](https://gohugo.io/content-management/syntax-highlighting/#list-of-chroma-highlighting-languages)  | empty value |
| markdown | included file is markdown | false |
| options | highlighting [options](https://gohugo.io/content-management/syntax-highlighting/#highlight-shortcode) | linenos=table |

\* if not set, the content will be rendered as plain html

### Include *.yml file with options

```tpl
{{</* include file="config.yaml" language="yaml" options="linenos=table,hl_lines=5-6,linenostart=100" */>}}
```

{{< include file="config.yaml" language="yaml" options="linenos=table,hl_lines=5-6,linenostart=100">}}

### Include *.md file

Included markdown files will be rendered using the `markdownify` filter.

{{< hint warning >}}
**Location of markdown files**\
If you include markdown files that should not get a menu entry, place them outside the content folder or exlude them otherwise.
{{< /hint >}}

```tpl
{{</* include file="static/table.md" markdown="true" */>}}
```

{{< include file="static/table.md" markdown="true" >}}

### Include *.html file

Html content will be filtered by the `safeHTML` filter and added to the rendered page output.

```tpl
{{</* include file="static/example.html" */>}}
```

{{< include file="static/example.html" >}}
