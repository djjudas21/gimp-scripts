# gimp-scripts

Assorted GIMP scripts I have collected over the years.

At the moment, most of these are for GIMP 2.x but I have collected them in this repo
so I can begin work to port them to GIMP 3.x.

Documentation around [Filter Plugins](https://script-fu.github.io/funky/hub/tutorials/folder/filter-plug-in/filter-plug-ins/) shows a new syntax required to register the script.
It looks like registering the script into GIMP and registering a menu entry for the plugin are now two separate actions:

```scheme
;; Register the plug-in
(script-fu-register-filter 
  "script-fu-simple-filter-plug-in"        ;; Main procedure name
  "Simple Filter Plug-in Demo"             ;; The name as it appears in the GIMP menu
  "Tests a basic Script-Fu filter plug-in" ;; Tool-tip description
  "Author Name"                            ;; Give yourself some credit
  "License"                                ;; License
  "Date written"                           ;; Date written
  "*"                                      ;; Indicates this plug-in requires an image
  SF-ONE-OR-MORE-DRAWABLE)                 ;; Requires one or more selected drawables

;; Specify the menu location for the plug-in
(script-fu-menu-register 
  "script-fu-simple-filter-plug-in" 
  "<Image>/Plug-in")
```

[This example](https://github.com/tshatrov/scriptfu/compare/gimp-2.10...34785f708fde4915896d6bf1d1a4d77f4d825886) shows the changes needed to port a script