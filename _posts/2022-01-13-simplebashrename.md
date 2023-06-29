---
layout: post
title:  "Rename multiple files with BASH!"
tags: bash
mathjax: on
---
    # Change *.md with the specific file with the excat extensions like .md or .markdown, the one that would be renamed
    # change the date 2022...-$file to the what do you want to append to the renaming of the files.
    for file in *.md
     do
        mv "$file" "2022-01-12-$file"
     done

Copy the code above save as "rename.sh" 

    chmod +x rename.sh

So you can run the command example:

    ./rename.sh * 2022-01-12-*

EZ.
