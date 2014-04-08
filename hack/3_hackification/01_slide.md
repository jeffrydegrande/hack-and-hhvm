!SLIDE subsection

# Hackification #

!SLIDE code

# Hack Modes

    @@@ php

    <?hh // strict
    
    <?hh // partial
    <?hh

    <?hh // decl

    // UNSAFE

!SLIDE commandline

$ cd ~/Code/Engagor/engagor

$ hackification

... this takes forever

!SLIDE

* *hackification* script converts your project
* tries to apply the most restrictive mode that doesn't throw errors

!SLIDE

# Going forward

* files with <?php continue working
* manually convert them to <?hh, fix errors
* add annotations
* try to get to // strict 
* not always possible though (dynamic stuff, stuff that has a main())
