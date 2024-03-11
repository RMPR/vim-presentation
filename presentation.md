# Vim Workshop
Use pageup and pagedown to go between slides


# Emergency exit - Nano
	If you want to revert to what I call "Nano mode" press ESC then i 
	You can move with arrow keys and do all the things that you are used to.
	Try it! Then press Ctrl-C


# Goals
	1. Enough Vim to not quit in frustration when dumped into it
	2. A bit of keystrokes golfing for advanced users


# Motivation
	A lot of interaction with code is manipulating existing code, not creating new.
	Vi is a Posix requirement (https://en.wikipedia.org/wiki/List_of_POSIX_commands)
	Ubiquity: You will interact with Vim in so many ways (git, ssh, containers, ctrl-x e, ...)
	Efficiency: Not having to use the mouse, understanding the Vim way


# Modes
	You don't need to memorize any of this, just doing it a couple of times will make it muscle memory
	- Insert mode** (the mode all regular editors are in)
	- Normal mode**
	- Visual mode*
	- Search mode
	- Replace mode
	- Ex mode
	- ...


# Basic movement
             ^
             k              Hint:  The h key is at the left and moves left.
       < h       l >               The l key is at the right and moves right.
             j                     The j key looks like a down arrow.
             v
	1. You can move the cursor around the screen until you are comfortable.
	2. SOURCE: vimtutor.


# Deletion
  ** Press  x  to delete the character under the cursor. **
  1. Move the cursor to the line below marked --->.
  2. To fix the errors, move the cursor until it is on top of the
     character to be deleted.
  3. Press the	x  key to delete the unwanted character.
  4. Repeat steps 2 through 4 until the sentence is correct.
---> The ccow jumpedd ovverr thhe mooon.


# Insertion
	** Press  i  to insert text. **
  1. Move the cursor to the first line below marked --->.
  2. To make the first line the same as the second, move the cursor on top
     of the character BEFORE which the text is to be inserted.
  3. Press  i  and type in the necessary additions.
  4. As each error is fixed press <ESC> to return to Normal mode.
     Repeat steps 2 through 4 to correct the sentence.
---> There is text misng this .
---> There is some text missing from this line.

# Undo/Redo
   ** Press  u	to undo the last commands **
  1. Move the cursor to the line below marked ---> and place it on the
     first error.
  2. Type  x  to delete the first unwanted character.
  3. Now type  u  to undo the last command executed.
  4. Now type CTRL-R (keeping CTRL key pressed while hitting R) a few times
     to redo the commands (undo the undo's).
---> Fiix the errors oon thhis line and reeplace them witth undo.


# That's it, you know enough VIM
	hjkl to move
	x to delete
	i to insert
	u to undo
	Ctrl-R to redo


# Advanced Undo/Redo
  1. Do any modification in this file
  2. Type :earlier 15m
  3. Type :later 20m
  4. Now you understand why I don't work, I just do :later 8h
  5. You may not like it, but this is what peak performance looks like


# I have a confession to make...
	I don't exit normal mode with ESC or any mapping... I use alt


# Appending
			** Press  A  to append text. **
  1. Move the cursor to the first line below marked --->.
     It does not matter on what character the cursor is in that line.
  2. Press  A  and type in the necessary additions.
  3. As the text has been appended press <ESC> to return to Normal mode.
  4. Move the cursor to the second line marked ---> and repeat
     steps 2 and 3 to correct this sentence.
---> There is some text missing from th
     There is some text missing from this line.
---> There is also some text miss
     There is also some text missing here.


# Deletion
		       ** Type  dw  to delete a word. **
  1. Press  <ESC>  to make sure you are in Normal mode.
  2. Move the cursor to the line below marked --->.
  3. Move the cursor to the beginning of a word that needs to be deleted.
  4. Type   dw	 to make the word disappear.
  NOTE: The letter  d  will appear on the last line of the screen as you type
	it.  Vim is waiting for you to type  w .  If you see another character
	than  d  you typed something wrong; press  <ESC>  and start over.
---> There are a some words fun that don't belong paper in this sentence.


# More deletion
	   ** Type  d$	to delete to the end of the line. **
  1. Press  <ESC>  to make sure you are in Normal mode.
  2. Move the cursor to the line below marked --->.
  3. Move the cursor to the end of the correct line (AFTER the first . ).
  4. Type    d$    to delete to the end of the line.
---> Somebody typed the end of this line twice. end of this line twice.


# Pause: VIM Grammar
	You can roughly summarize it as [operator]-[count]-motion


# Change
	   ** To change until the end of a word, type  ce . **
  1. Move the cursor to the first line below marked --->.
  2. Place the cursor on the  u  in  lubw.
  3. Type  ce  and the correct word (in this case, type  ine ).
  4. Press <ESC> and move to the next character that needs to be changed.
  5. Repeat steps 3 and 4 until the first sentence is the same as the second.
---> This lubw has a few wptfd that mrrf changing usf the change operator.
---> This line has a few words that need changing using the change operator.
Notice that  ce  deletes the word and places you in Insert mode.
             cc  does the same for the whole line.


# More efficient vertical navigation
	:set number
	:set relativenumber
	Those can be shortened:
	:set nu|set rnu


# Motion practice
   ** Typing a number before a motion repeats it that many times. **
  1. Move the cursor to the start of the line below marked --->.
  2. Type  2w  to move the cursor two words forward.
  3. Type  3e  to move the cursor to the end of the third word forward.
  4. Type  0  (zero) to move to the start of the line.
  4. Type  _  (underscore) to move to the first non blank character
  5. Repeat steps 2 and 3 with different numbers.
---> This is just a line with words you can move around in.


# Motion practice 2
   ** Using f or F you can search respectively forward and backward. **
   ** You can repeat the search with ; **
  1. Move the cursor to the start of the line below marked --->.
  2. Type fj to move the cursor to j
  3. Type  fw  to move the cursor to the beginning of with
  4. Type  ;  to move to words
  5. You can combine it with other motions too! ([c]hange, [d]elete)
---> This is just a line with words you can move around in.


# Commit message formatting
** Using gqq you can format a line of text. **
** Especially useful for commit message body **
The data pointers for `float3` and `int3` were being cast down to their `const` overloads, so the program silently didn't update the host buffer when the GPU code ran. In this commit, we fix this MISC

# Commit message formatting: visual
   ** Using v you can enter visual mode. **
   ** With motions you control the selection, with gq you format**
   1. Go ahead and select until the second "This commit"
   2. Format the first part
   3. Select from the second "This commit" to the end
   4. Format the second part
   5. Congrats you have passed the commit message formatter.
This commit adds arm64 to the supported architectures for camera tests, and adds L4T as a docker image option.  This commit also skips running nvida-smi on Jetson during compute device logging because nvidia-smi is not available on Jetson.


# Search command
     ** Type  /  followed by a phrase to search for the phrase. **
  1. In Normal mode type the  /  character.  Notice that it and the cursor appear at the bottom of the screen as with the  :	command.
  2. Now type 'errroor' <ENTER>.  This is the word you want to search for.
  3. To search for the same phrase again, simply type  n .
     To search for the same phrase in the opposite direction, type  N .
  4. To search for a phrase in the backward direction, use  ?  instead of  / .
  5. To go back to where you came from press  CTRL-O  (Keep Ctrl down while
     pressing the letter o).  Repeat to go back further.  CTRL-I goes forward.
--->  "errroor" is not the way to spell error;  errroor is an error.
NOTE: When the search reaches the end of the file it will continue at the
      start, unless the 'wrapscan' option has been reset.


# Golfing
Just small exercises to practice efficiency


# More change
Replace <ETHERNET_INTERFACE> with eth0
   network:
     version: 2
     renderer: networkd
     ethernets:
	 <ETHERNET_INTERFACE>:
         dhcp4: false
         addresses:
           - 172.28.60.1/24

# You forgot to run autosquash
** Can you correct this in as few keystrokes as possible?**
pick 2130fcb956 FPGA: Fix VMAX for 10-bit high speed mono readout
pick b7b58408c2 SDK: Make `CaptureDiagnosticsSystemTest` work for Kodachrome cameras
pick 3045369c4f SDK: Disable reflection filter tests on CUDA
pick 2d6d598ac7 Infra: revert no ci by default
pick 2d6d598ac7 fixup! FPGA: Fix VMAX for 10-bit high speed mono readout
pick 15a79cd3f2 Git LFS: Let's use .tar.zst instead of zip, add notes


# You forgot to run autosquash 2
** What about this one?**
pick 2130fcb956 FPGA: Fix VMAX for 10-bit high speed mono readout
pick b7b58408c2 SDK: Make `CaptureDiagnosticsSystemTest` work for Kodachrome cameras
pick 3045369c4f SDK: Disable reflection filter tests on CUDA
pick 2d6d598ac7 Infra: revert no ci by default
pick 2d6d598ac7 fixup! FPGA: Fix VMAX for 10-bit high speed mono readout
pick 15a79cd3f2 Git LFS: Let's use .tar.zst instead of zip, add notes
pick 43ca0d2e83 fixup! SDK: Disable reflection filter tests on CUDA
pick 0b590c406f fixup! fixup! SDK: Disable reflection filter tests on CUDA


# Writing sudo can be tricky
sduo apt update -y


# You can't avoid macros
** Reformat the YAML file by adding a hyphen before the "fpga" keys**
common_ignore_paths:
    fpga/build
    fpga/bin/python/pinning/exclude
    fpga/bin/python/zhit/docker/gitconfig
    fpga/m014_zhittest/scripts/illegal
    fpga/m014_zhittest/scripts/valid
    fpga/firmware/BoschBME280/LICENSE


# What about many sudos
* Prefix all the lines with sudo *
	apt update -y
	apt install git -y
	apt install build-essentials -y
	apt install docker -y


# There is more:
	- Macros
	- Splits
	- Sessions
	- CLI interactions (!read ls)


# Use this in your Editor of choice
	Visual Studio Code : Vscodevim
	Jetbrains family: Ideavim
	Emacs: Evil


# If you want to exit VIM...
	You can go here https://github.com/hakluke/how-to-exit-vim
	...Or just press ESC then ZZ
