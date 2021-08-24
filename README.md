# Streaker

Be a soccer streaker as long as you can.

## engine

Based on [some](https://github.com/renehorstmann/some) engine

### Compiling for Web

Using Emscripten:

```sh
mkdir web && cd web

emcc -I../include/ -s USE_SDL=2 -s USE_SDL_IMAGE=2 -s FULL_ES3=1 -s SDL2_IMAGE_FORMATS='["png"]' --preload-file ../res -s ALLOW_MEMORY_GROWTH=1 -DOPTION_GLES -DOPTION_SDL ../src/e/*.c ../src/p/*.c ../src/r/*.c ../src/u/*.c ../src/*.c -o index.html
```

May / will not work on Apple, because of their poor WebGL2 support.

## Without Cmake

Instead of cmake, the following call to gcc should work, too.

```sh
mkdir build && cd build

cp -r ../res .

gcc ../src/e/*.c ../src/p/*.c ../src/r/*.c ../src/u/*.c ../src/*.c -I../include/ $(sdl2-config --cflags --libs) -lSDL2_image -lSDL2_ttf -lglew32 -lopengl32 -lglu32 -DOPTION_GLEW -DOPTION_SDL -o streaker
```


## Author
René Horstmann

## Licence
- The game and its assets are licenced under GPLv3, see LICENCE.
- The [some](https://github.com/renehorstmann/some) framework is under MIT licence, see someLICENCE.
