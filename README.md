Remove Quora Modal Dialog
=========================

JavaScript bookmarklet to remove Quora's modal dialog box which they pop up to get more personal information from you.

## Background

If you click through a Quora digest email to a story, AND you haven't completed your Quora profile, they pop up a modal dialog on top of your story to get more info from you before letting you proceed.

It looks like this - https://www.evernote.com/shard/s27/sh/d2f8d5e7-da33-4905-a04a-17f5baa2d725/6ccd9b13fa8fde353912fb2af7c2fa3a

Very annoying.

## Bookmarklet Code

```
javascript:$('div').each(function(idx, elt) { if (elt.attributes['id'] && elt.attributes['id'].value.match(/modal_nux_wrapper/)) { console.log(idx, elt); elt.style['display'] = 'none'; } })
```

## How It Works

Quora's modal dialog has a random ID that always ends in `modal_nux_wrapper`. This code cycles through every DIV on their page and looks for that suffix. If found, sets its `display` style to `none`, which effectively removes it from view.
