- World Map editing for SuperTux -
http://supertux.lethargik.org/

Last update: September 4, 2004

This document describes how to edit a world map.

EDITING WORLDMAP TILES
----------------------

To edit a World Map, please use FlexLay. Thought it might have problems with
the editing of level and special tiles, since it isn't sync with CVS.

INTRODUCTION
------------

These things are always changing, so if even 0.1.x has something like something
described here, it might have a different name or be used in a different way.

Stuff prefixed by a ';' are comments.

    ; This is a comment! :)

MAKING THE HOLE FOR A LEVEL
---------------------------

    ; Opening level group
    (level

    ; X and Y position [NECESSARY]
     (x 10)
     (y 14)

    ; Filename of the level [NECESSARY]
     (name "file_name.stl")

    ; Flip the level vertically - default: false
     (vertical-flip #t)

    ; Show this text file after completing this level
     (extro-filename "filename")

    ; Go to this world after completing this level
     (next-worldmap "worldmap.stwt)

    ; Exit world map after completing this level
     (quit-worldmap #t)

    ; Disable auto walking after completing the level - default: false
     (auto-path #f)

    ) ; end of level group

AVAILABLE SPECIAL TILES
-----------------------

    ; Opening special-tile group
    (special-tile

    ; X and Y position [NECESSARY]
     (x 10)
     (y 14)

    ; Add a message tile. You can also use this together with a teleporter.
     (map-message "Hello World!"

    ; Instead of showing a fix message, show while the player
    ; passes by [NEEDS: map-message]- default: false
     (passive-message #t)

    ; Apply action only in this/these direction(s) [WORKS FOR: passive-message] -
    ; default: true for all - possible values: north/south/east/west.
    ; More than one can be used with a separator or not
     (apply-to-direction "north-east")

    ; Add a teleporter tile to
     (teleport-to-x 20)
     (teleport-to-y 13)

    ; Don't show this tile [WORKS FOR: teleporter, map-message]
     (invisible-tile #t)

    ) ; end of special-tile group
