-----------------------------------------------------------------------------
  FlashDoom
 
  based on Linux DOOM 1.10
  Copyright (C) 1999 by
  id Software

  This program is free software; you can redistribute it and/or
  modify it under the terms of the GNU General Public License
  as published by the Free Software Foundation; either version 2
  of the License, or (at your option) any later version.

  This program is distributed in the hope that it will be useful,
  but WITHOUT ANY WARRANTY; without even the implied warranty of
  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
  GNU General Public License for more details.

  You should have received a copy of the GNU General Public License
  along with this program; if not, write to the Free Software
  Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA
  02111-1307, USA.
-----------------------------------------------------------------------------

  
Requires the Adobe Alchemy Toolkit preview.
Specifically, the ALCHEMY_HOME variable should point to your Alchemy directory.

A simple port of LinuxDoom to ActionScript bytecode via Alchemy,
with hooks in place to pass the frame and sound buffers to Flash.

TODO:
- Instead of reading the _ram ByteArray in the AS and setting the BitmapData there, would it be better to instead pass the BitmapData into C and use the AS3_ByteArray functions to draw the frame buffer?  Should avoid the allocation of the gameScreen array.
- Similarly for sound
- Configurable controls, some sort of mouse control
- Try turning singletics back off?  Properly implement I_GetTime using getTimer (or does Alchemy's time.h already do this?)
- Seems to be some slight input lag -- is it related to my stupid implementation of I_GetTime, or is it just the Flash lagging in general, or is everything fine?  I've looked through the game code and haven't found anything yet.
- Implementing music, using Timidity or some other software synthesizer
- Switch to prBoom or some other more advanced source port