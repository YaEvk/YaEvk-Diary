Your vimrc can be located in a few different places. It's also important to understand the distinction between a user vimrc and the system vimrc. From :help vimrc:

    A file that contains initialization commands is called a "vimrc" file. Each line in a vimrc file is executed as an Ex command line. It is sometimes also referred to as "exrc" file. They are the same type of file, but "exrc" is what Vi always used, "vimrc" is a Vim specific name. Also see |vimrc-intro|.

    Places for your personal initializations:

        Unix            $HOME/.vimrc or $HOME/.vim/vimrc
        OS/2            $HOME/.vimrc, $HOME/vimfiles/vimrc
                        or $VIM/.vimrc (or _vimrc)
        MS-Windows      $HOME/_vimrc, $HOME/vimfiles/vimrc
                        or $VIM/_vimrc
        Amiga           s:.vimrc, home:.vimrc, home:vimfiles:vimrc
                        or $VIM/.vimrc

    The files are searched in the order specified above and only the first one that is found is read.

Mac OS X counts as Unix for the above.

There are essentially two kinds of vimrc: the user vimrc in $HOME and the system vimrc in $VIM (on Amiga systems, s:.vimrc is considered a user vimrc). The user vimrc file often does not exist until created by the user. If you cannot find $HOME/.vimrc (or $HOME/_vimrc on Windows) then you can, and probably should, just create it.

$VIM/.vimrc ($VIM/_vimrc on Windows) is the system vimrc, and is normally left unmodified. It is not a good place you keep your personal settings. If you modify this file your changes may be overwritten if you ever upgrade vim. Also, changes here will affect other users on a multi-user system.

Note that the mere existence of a user vimrc will change vim's behavior by turning off the compatible option. From :help compatible-default:

    When Vim starts, the 'compatible' option is on. This will be used when Vim starts its initializations. But as soon as a user vimrc file is found, or a vimrc file in the current directory, or the "VIMINIT" environment variable is set, it will be set to 'nocompatible'. This has the side effect of setting or resetting other options (see 'compatible'). But only the options that have not been set or reset will be changed.

tl;dr

To create your vimrc, start up vim and do one of the following:

:e $HOME/_vimrc  " on Windows

:e s:.vimrc      " on Amiga

:e $HOME/.vimrc  " on Unix, Mac or OS/2

Insert the settings you want, and save the file.

