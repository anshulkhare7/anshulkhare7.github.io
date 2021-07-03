[![Twitter](https://img.shields.io/twitter/follow/_anshulkhare?style=social)](https://twitter.com/_anshulkhare) 
## For the base version of Tiddlywiki

### Add new tab “Start Here”
1. Create a new tiddler named Start
2. Add a tag called **$:/tags/SideBar** to this tiddler
3. In the contents field for this tiddler add one of the following — 
    `<<toc-selective-expandable ‘Start’ sort[title]>>`
    `<<list-links "[tag[Start]]">>`
4. Add __Start__ tag to all the tiddlers that you want to get listed in the __Start__ tab.

### Add backlinks to each tiddler 
1. Create a new tiddler called “Note Ref”
2. Add a tag called **$:/tags/ViewTemplate** to this tiddler.
3. Add following content to the tiddler — 
    ```
    <$list filter='[is[current]backlinks[]limit[1]]' variable=dummy>
        <hr>
        <strong>Back Reference<strong><br/><$list filter='[<currentTiddler>backlinks[]butlast[]]'><$link><$view field="title"/></$link><br/></$list>
        <$list filter='[<currentTiddler>backlinks[]last[]]'><$link><$view field="title"/></$link></$list>
    </$list>
    ```

### Remove unwanted buttons from the published version
1. Create a new tiddler named **CustomCSS**. Add tag called **$:/tags/Stylesheet**.
2. Add following css in this custom tiddler
```
.tc-tags-wrapper,
.tc-subtitle{
    display: none;
}  

.tc-popup-handle{
	width: 50%
}

.tc-tab-buttons{
	font-size: 1.5em
}

button[title=“Save changesXYX”]{
	display:none;
}
```
3. Click on _control panel_ button in side bar.
4. Make sure the control panel tiddler remains open.
5. Go to `Appearance -> Toolbars -> Page Toolbar` — uncheck **new tiddler** and **control panel**. Keep **close all**, **save changes**, and **refresh** checked.
6. Click on _More_ tab in the side bar. Go to _Shadows_
7. Find **$:/core/ui/SideBar/Recent** Remove the tag and save.
8. Find **$:/core/ui/SideBar/Tools** Remove the tag and save.
9. Find **$:/core/ui/SideBar/More** Remove the tag and save.
10. Go to `Appearance -> Toolbars -> View Toolbar` — uncheck **more** and **edit**
11. Go to `Appearance -> Toolbars -> Edit Toolbar` — uncheck **delete**, **cancel** and **ok**
12. Add Google analytics and mailchimp
```
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-132755427-3"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-132755427-3');
</script>
<!-- Mailchimp -->
<script id="mcjs">!function(c,h,i,m,p){m=c.createElement(h),p=c.getElementsByTagName(h)[0],m.async=1,m.src=i,p.parentNode.insertBefore(m,p)}(document,"script","https://chimpstatic.com/mcjs-connected/js/users/d34ff0e5be5c185fb82da2048/92b6f8b74ef1a8775f865e0cc.js");</script>
```

### Adding last updated timestamp

Using [this plugin](https://tiddlywiki.com/static/How%2520to%2520put%2520the%2520last%2520modification%2520date%2520in%2520a%2520banner.html)
