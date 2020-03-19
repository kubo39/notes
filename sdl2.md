# sdl2

## dub.sdl

```sdl
(...)
versions "BindSDL_Static"
libs "SDL2"
```

## Initialization

```d
shared static this()
{
    assert(SDL_Init(0) == 0);
    assert(SDL_InitSubSystem(SDL_INIT_VIDEO) == 0);
    assert(SDL_InitSubSystem(SDL_INIT_EVENTS) == 0);
}

shared static ~this()
{
    SDL_QuitSubSystem(SDL_INIT_EVENTS);
    SDL_QuitSubSystem(SDL_INIT_VIDEO);
    SDL_Quit();
}
```
