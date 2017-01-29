# SDL-3DS
SDL 1.2 for 3DS





   Simple DirectMedia Layer

                                  (SDL)

                                Version 1.2.15 Nintendo 3DS port
---

TOC
- Video
- Key input
- Joystick
- Audio

VIDEO

Any video size supported, the video device will be rendered centered on the HW screen. The default HW screen is the TOP screen

Four bpp values supported : 32 (RGBA), 24 (RGB), 16 (RGB565), 15 (RGB555_A1)

The SDL_FULLSCREEN option stretchs the video device on the HW screen.

The following custom option for the video device are defines:
- SDL_TOPSCR: select the top screen for rendering the video device (it's the default option, so you don't really need to set this flag)
- SDL_BOTTOMSCR: select the bottom screen for rendering the video device
- SDL_DUALSCR: draws the upper half of the video device on the top screeen and the lower half on the bottom screen
- SDL_FITWIDTH: resizes the video device to fit the selected screen width (if SDL_DUALSCR is set, its' resized to 400 pixel width)
- SDL_FITHEIGHT: resizes the video device to fit the screen/screens width
- SDL_CONSOLETOP: enables console output on the top screen (only if SDL_TOPSCR or SDL_FULLSCREEN are not set)  
- SDL_CONSOLEBOTTOM: enables console output on the bottom screen (only if SDL_BOTTOMSCR or SDL_FULLSCREEN are not set)

Note: using the SDL_FULLSCREEN flag is the same of using (SDL_TOPSCR | SDL_BOTTOMSCR) 

KEY INPUT

default key bindings are:

 KEY_A -> SDLK_a
 KEY_B -> SDLK_b
 KEY_X -> SDLK_x
 KEY_Y -> SDLK-y
 KEY_L -> SDLK_l
 KEY_R -> SDLK_r
 KEY_START -> SDLK_RETURN
 KEY_SELECT -> SDLK_ESCAPE  
 KEY_RIGHT -> SDLK_RIGHT
 KEY_LEFT -> SDLK_LEFT
 SDLK_UP -> KEY_UP
 KEY_DOWN -> SDLK_DOWN
 
a custom function is defined to bind one or more N3DS keys to a SDL key value:

 void SDL_N3DSKeyBind(unsigned int hidkey, SDLKey key)

NOTE: circle pad and C-Stick are not mapped to the direction key by default( circle pad is mapped to the default Joystick) but if someone wants to make this mapping can use the following code:
	
	SDL_N3DSKeyBind(KEY_CPAD_UP|KEY_CSTICK_UP, SDLK_UP);
	SDL_N3DSKeyBind(KEY_CPAD_DOWN|KEY_CSTICK_DOWN, SDLK_DOWN);
	SDL_N3DSKeyBind(KEY_CPAD_LEFT|KEY_CSTICK_LEFT, SDLK_LEFT);
	SDL_N3DSKeyBind(KEY_CPAD_DOWN|KEY_CSTICK_DOWN, SDLK_DOWN);

It's not possible to binf a N3DS key to two or more SDL Key values.

JOYSTICK

Joystick support is enabled but needs testin (and probably fixing)

AUDIO

Audio is disabled and starting and an Init Audio will stop the program



 

---
http://www.libsdl.org/