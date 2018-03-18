---
layout: post
title: Open XML - Interpreting Group and Shape Positions in Word
---

A group in a Word document creates the following heirarchy of nodes in document.xml.
```xml
<mc:AlternateContent ...>
  <mc:Choice ...>
    <w:drawing ...>
      <wp:anchor ...>
        <wp:positionH ...>
        <wp:positionV ...>
        <a:graphic ...>
          <a:graphicData ...>
            <wpg:wgp ...>
              ...
              <wpg:grpSpPr ...>
                <a:xfrm ...>
                  <a:off .../>
                  <a:ext .../>
                  <a:chOff .../>
                  <a:chExt .../>
              <wps:wsp ...>
                ...
                <wps:spPr ...>
                  <a:xfrm ...>
                    <a:off .../>
                    <a:ext .../>
              ...
```

To position a shape in a group

## Step 1

Use `wp:positionH` and `wp:positionV` to position the group.

_360000 emu_ = _1 cm_ from the edge of the margin is

```xml
<wp:positionH relativeFrom="margin">
  <wp:posOffset>360000</wp:posOffset>
</wp:positionH>
```

`relativeFrom="document"` makes it from the edge of the _document_.

## Step 2

`wpg:grpSpPr/a:xfrm/a:chOff` reversed and scaled by `a:ext/a.chExt`, positions shapes within the group.

_360000 emu * (100000 / 200000)_ = _0.5 cm_ from the top of the group is

```xml
<a:ext ... cy="100000"/>
<a:chExt ... cy="200000"/>
<a:chOff ... y="-360000"/>
```

## Step 3

`wps:spPr/a:xfrm/a:off` scaled, _repositions_ a shape within the group.

_(100000 / 200000) * 360000 emu_ = _0.5 cm_ from the left of the group is

```xml
<wpg:grpSpPr>
  <a:xfrm>
    <a:ext cx="100000" ... />
    <a:chExt cx="200000" ... />
    <a:chOff x="0" ... />
    ...
<wps:wsp>
  <wps:spPr>
    <a:xfrm>
      <a:chOff x="360000" ... />
      ...
```

Both `wpg:grpSpPr/a:xfrm/a:chOff` and `wps:spPr/a:xfrm/a:off` change shape position.

## Related ##

**Opening OpenXML documents**

1. Shift + Right click the .docx file
2. Open with... 
3. Browse and choose 7-Zip (or any archive tool)

**OpenXML Units**

1 Point = 20 DXAs  
1 inch = 914,400 EMUs  
1 cm = 360,000 EMUs

