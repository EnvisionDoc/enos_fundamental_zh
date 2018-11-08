# Heading 1

## Heading 2

### Heading 3

#### Heading 4

**bold**

_italic_

`monospace`

```
paragraph of code
```

> cite

![描述图中内容](/url/to/image.svg)


**Warning警告**: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
**Notice注意**: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
**Tip提示**: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

# Lists
Depending on your needs, you can use Markdown or HTML for lists.

Ordered
1. step 1
2. step 2
3. step 3

Un-Ordered
- Item 1
- Item 2
- Item 3

## Definition lists
Definition lists and parameter lists are two cases where you might want to pass in HTML. If you are migrating from DITA, ensure that you are passing in HTML and not DITA. One tip is to transform your DITA content into HTML and then borrow from the IDWB transform output. But, keep it as simple as possible.

Example definition list:
<dl>
<dt><strong>term</strong></dt>
<dd>definition</dd>
<dt><strong>term</strong></dt>
<dd>definition</dd>
<dt><strong>term</strong></dt>
<dd>definition</dd>
</dl>


## Nested lists
You can nest ordered lists within ordered lists, and bulleted lists within bulleted lists in markdown. But you cannot nest an ordered list within a bulleted list or vice versa. Therefore, for the nested list, you'll need to pass through HTML. Once you are nesting html, all tagging within the HTML must be HTML tags. You can't start using markdown, for example for bolding or italics.

### Example 1
* bullet item

<ol>
<li>item 1</li>
<li>item 2</li>
</ol>

* another bullet item

### Example 2
1. item 1

<ul>
<li>bullet item</li>
<li>another bullet item</li>
</ul>

2. item 2

## Nested ordered lists
To nest an <ol> within an <ol> and get the nested <ol> to use alphabetic numbering, use type="a".
For example:
* bullet

<ol>
<li>step 1
<ol type="a">
<li>substep a</li>
<li>substep b</li>
</ol>
</li>
<li>step2</li>
</ol>
