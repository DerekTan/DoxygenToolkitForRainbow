# DoxygenToolkitForRainbow
This is a customized version of the vim plugin "DoxygenToolkit".
*DoxygenToolkitForRainbow.txt* makes it easier to add Rainbow-style comments.

You could download the original plugin
from vim.org:  http://www.vim.org/scripts/script.php?script_id=987  
or from github:  https://github.com/vim-scripts/DoxygenToolkit.vim 

====================================================================
CONTENTS                                  *DoxygenToolkitForRainbow*

1\. Usage............................|DoxygenToolkitForRainbowUsage|
2\. Configuration............|DoxygenToolkitForRainbowConfiguration|
3\. Changelog....................|DoxygenToolkitForRainbowChangelog|


====================================================================
Section 1: Usage                     *DoxygenToolkitForRainbowUsage*

DoxygenToolkitForRainbow.vim could help you add Rainbow-style comments.
including:

Installation
------------
Put DoxygenToolkitForRainbow.vim in your vim plugin directory.

                                                          *DoxBlock*
In vim, execute the command :DoxBlock to insert a block comment on the
following line.
You will be prompted to input the block name.
If you input "block name", the block comments will be:
//==================================================================================================
//  B L O C K   N A M E
//==================================================================================================
  
                                                         *DoxAuthor*
In vim, place the cursor at the very begining of the source file, 
execute the command :DoxAuthor to insert a File comment.
You will be prompted to input the project name, author name and version
number if they have not been set.
The file comment will looks like this:
//==================================================================================================
//                                          PROJECT NAME
//==================================================================================================
//
//! \file        DoxygenToolkitForRainbow.txt
//! \ingroup     
//! \brief       
//! 
//! (c) Copyright 2004-2015 Mettler-Toledo. All Rights Reserved.
//! \author      Derek Tan
//
// $Date: 2017/11/15 14:14:29CCT $
// $Revision: 1.0 $
// 
//==================================================================================================

                                                               *Dox*
In vim, place the cursor on the line of the function header.  
Then execute the command :Dox.  This will generate the skeleton 
and leave the cursor after the \brief tag.
For example, for the following function:
static int func(int param1, const char* param2)
{
    return 0;
}

The comments generated would be as following:
//--------------------------------------------------------------------------------------------------
//  func
//--------------------------------------------------------------------------------------------------
//! \brief  
//!
//! \param param1
//! \param param2
//!
//! \return   
//--------------------------------------------------------------------------------------------------

====================================================================
Section 2: Configuration     *DoxygenToolkitForRainbowConfiguration*

For convenience, you can put the following lines in your .vimrc.
" For DoxygenToolkit
nnoremap <F10>a :DoxAuthor<CR>
nnoremap <F10>f :Dox<CR>
nnoremap <F10>b :DoxBlock<CR>
let g:DoxygenToolkit_commentType = "Rainbow"
let g:DoxygenToolkit_authorName = "Dake Tan"
let g:DoxygenToolkit_licenseTag = "(c) Copyright 2004-2017 Mettler-Toledo. All Rights Reserved."

The following 2 lines are optional.
"let g:DoxygenToolkit_timezoneString = "CCT"
"let g:DoxygenToolkit_projectString = "Rainbow"

====================================================================
Section 3: Changelog             *DoxygenToolkitForRainbowChangelog*
2017/11/15
    add the function to generate file comments and block comments
2017/11/14
    modify the original plugin to generate Rainbow-style function comments
