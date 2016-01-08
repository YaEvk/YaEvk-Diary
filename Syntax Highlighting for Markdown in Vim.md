#Syntax Highlighting for Markdown in Vim
*Attributed by Brooke Lester, http://www.brookelester.net/blog/2014/9/23/syntax-highlighting-for-markdown-in-vim*

When I first learned Vim, I was excited to begin writing in Markdown while composing in Vim. Some things didn't work like I hoped. Opening and creating files with my favorite Markdown filename suffix (name.md), I found that the syntax highlighting was a nightmare: weird choices, and color changes after every use of a quote mark (as with contractions like "don't" or "isn't").

Scouting around, I found a solution. I repeat it here for clarity and so that other people Googling around with the same problem have another, more recently published, chance at the answer.

You first need to create a Vim resource file, or edit it if it already exists. In Terminal (Mac or Linux), navigate to your User directory:

```cd ~/```

There, check to see if you have an invisible file named .vimrc by listing all files, including invisibles:

```ls -a```

Now, create (or open) that file:

```vim .vimrc```

Finally, edit that file to include the following:

" set sytax highlighting on.
```syntax on```

" set files with extension .md to be recognized as markdown.
```filetype on
au BufNewFile,BufRead *.{md,mdown,mkd,mkdn,markdown,mdwn} set     filetype=markdown```

The double quotes simply turn the rest of that line into a comment line.

My own .vimrc file also includes the following, though I don't mind saying I can't quite remember why, off hand. If you know, please feel free to remind me in the comments.

```
set autoindent
set nu
```

" set not compatible mode to enable Vim features.
```set nocp```

Save the file and quit Vim. Navigate back to whatever directory you wish to be composing in. Create or open a "name.md" (or "name.mdown," or whatever) file, and voila! Lovely, correct Markdown sytax highlighting in Vim!

I have successfully done this in MacOS and in Linux Ubuntu. I think I once did it in Windows 7 as well.

I hope somebody finds this useful. If so, let me know.
