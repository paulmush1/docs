+++
title = "Table of contents"
description = ""
weight = 292
alwaysopen = true
+++

The simplest example of a table of contents:
```js
var docDefinition = {
  content: [
    {
      toc: {
        title: {text: 'INDEX', style: 'header'}
      }
    },
    {
      text: 'This is a header',
      style: 'header',
      tocItem: true
    }
  ]
}
```

If `id` is used in toc, the tocItem can target that id:
```js
var docDefinition = {
  content: [
    {
      toc: {
        id: 'mainToc',
        title: {text: 'INDEX', style: 'header'}
      }
    },
    {
      text: 'This is a header',
      style: 'header',
      tocItem: 'mainToc'
    }
  ]
}
```

If multiple Table of Contents are used, tocItem can be used to place the text in the correct toc:
```js
var docDefinition = {
  content: [
    {
      toc: {
        id: 'mainToc',
        title: {text: 'INDEX', style: 'header'}
      },
      toc: {
        id: 'subToc',
        title: {text: 'SUB INDEX', style: 'header'}
      }
    },
    {
      text: 'This is a header',
      style: 'header',
      tocItem: ['mainToc', 'subToc']
    }
  ]
}
```

You can also set table of contents style and indents using tocStyle and tocMargin
```js
var docDefinition = {
	content: [
		{
			toc: {
				title: {text: 'INDEX'},
			}
		},
		{
			text: 'Introduction',
			tocItem: true,
			tocStyle: {bold: true},
			pageBreak: 'before'
		},
		'Lorem ipsum dolor sit amet...',

		{
			text: 'Background',
			tocItem: true,
			tocMargin: [20, 0, 0, 0],
			pageBreak: 'before'
		},
		'Lorem ipsum dolor sit amet...',

		{
			text: 'About the project',
			tocItem: true,
			tocMargin: [20, 0, 0, 0],
			pageBreak: 'before'
		},
		'Lorem ipsum dolor sit amet...',

		{
			text: 'About the authors',
			tocItem: true,
			tocMargin: [20, 0, 0, 0],
			pageBreak: 'before'
		},
		'Lorem ipsum dolor sit amet...',

		{
			text: 'Abstract',
			tocItem: true,
			tocStyle: {bold: true},
			pageBreak: 'before'
		},
	]
}
```
