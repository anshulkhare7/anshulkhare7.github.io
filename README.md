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
        Back Reference: <$list filter='[<currentTiddler>backlinks[]butlast[]]'><$link><$view field="title"/></$link>,</$list>
        <$list filter='[<currentTiddler>backlinks[]last[]]'><$link><$view field="title"/></$link></$list>
    </$list>
    ```

### Remove unwanted buttons from the published version
1. Click on _control panel_ button in side bar.
2. Make sure the control panel tiddler remains open.
3. Go to `Appearance -> Toolbars -> Page Toolbar` — uncheck new tiddler and control panel. Check close all, and refresh
4. Click on _More_ tab in the side bar. Go to _Shadows_
5. Find **$:/core/ui/SideBar/Recent** Remove the tag and save.
6. Find **$:/core/ui/SideBar/Tools** Remove the tag and save.
7. Find **$:/core/ui/SideBar/More** Remove the tag and save.
8. Go to `Appearance -> Toolbars -> View Toolbar` — uncheck **more** and **edit**
9. Go to `Appearance -> Toolbars -> Edit Toolbar` — uncheck **delete**, **cancel** and **ok**

## Steps to remove the edit buttons in Krystal theme

1. Create a new tiddler with name $:/customCSS
2. Add a tag to this tiddle $:/tags/Stylesheet
3. Add following css in this custom tiddler
```
.tc-page-controls{
    display: none;
}

.tc-tags-wrapper{ 
    display: none;
}

[title="More actions"]{ 
    display: none; 
}

[title="Edit this tiddler"]{ 
    display: none; 
}

h2[title="This is a system tiddler"]{ 
    display: none; 
}
```
4. Go to **More** ($:/core/ui/SideBar/More)
5. Go to **Shadows** 
6. Find _$:/plugins/rmnvsl/krystal/headertools_
7. In this shadow tiddler, add style="display:none" for all the buttons except **All**