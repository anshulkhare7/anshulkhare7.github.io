## Steps to remove the edit buttons

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

h2[title~="This is a system tiddler"]{ 
    display: none; 
}
```
4. Go to **More** ($:/core/ui/SideBar/More)
5. Go to **Shadows** 
6. Find _$:/plugins/rmnvsl/krystal/headertools_
7. In this shadow tiddler, add style="display:none" for all the buttons except **All**
