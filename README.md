# onscripter-jh-alpine
[WIP] My ONScripter-jh Alpine Linux musl libc port

## Alpine Linux version
* alpine-standard-3.22.1-x86_64.iso

## TODO
* Make a easy Makefile project for SDL1.2 and SDL2

## For SDL1.2
```
# apk add gcc g++ make lftp linux-headers automake autoconf nano

# cd SDL-1.2.15/
# CFLAGS=-DICONV_INBUF_NONCONST ./configure --enable-static --disable-shared 
# make
# make install
# cd ..

# cd bzip2-1.0.5/
# make
# make install
# cd ..

# cd zlib-1.2.3/
# ./configure
# make
# make install
# cd ..

# cd libpng-1.4.0/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd jpeg-8/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd freetype-2.3.12/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd libogg-1.1.4/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd libvorbis-1.2.3/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd SDL_image-1.2.10/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd SDL_ttf-2.0.9/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd SDL_mixer-1.2.11/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd smpeg-0.4.5/
# ./autogen
# CFLAGS=-Wno-narrowing ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd onscripter-jh/
# nano Makefile.Linux
(modify Makefile.Linux, remove lua, fontconfig, avifile, and add -DLINUX LIBS=...-lm -lfreetype -lpng -lz)
# make -f Makefile.Linux
# cd ..

# cd onscripter_cn_test
# ../onscripter-jh/onscripter
```

## For SDL2
```
# apk add gcc g++ make lftp linux-headers automake autoconf libtool nano perl gdb pkgconf
(SDL2 need pkgconf's pkg-config to detect DirectFB)

# tar xzf DirectFB-1.4.5.tar.gz
# upzip DirectFB-1.4.5_patch.zip
# cd DirectFB-1.4.5
# CFLAGS=-Wno-incompatible-pointer-types ./configure --disable-jpeg --disable-png --disable-x11 --disable-sdl --disable-freetype --with-inputdrivers=keyboard,ps2mouse
# make -j4
# make install
# cd ..

# cd SDL2-2.0.22/
# CFLAGS="-DICONV_INBUF_NONCONST -Wno-incompatible-pointer-types" ./configure --enable-static --disable-shared --enable-video-directfb 
# make -j4
# make install
# cd ..

# cd bzip2-1.0.4/
# make
# make install
# cd ..

# cd zlib-1.2.3/
# ./configure
# make
# make install
# cd ..

# cd libpng-1.2.24/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd jpeg-8/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd freetype-2.3.5/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd libogg-1.1.3/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd libvorbis-1.2.0/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd SDL2_image-2.0.5/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd SDL2_ttf-2.0.15/
# ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd SDL2_mixer-2.0.4/
# CFLAGS=-Wno-incompatible-pointer-types ./configure --enable-static --disable-shared
# make
# make install
# cd ..

# cd smpeg2-2.0.0/
# CFLAGS=-Wno-narrowing ./configure --enable-static --disable-shared
# make
# make install
# cd ..

???use jh10001-onscripter-jh-a11f51d5728f_norender_v2.tar.gz instead
???use jh10001-onscripter-jh-a11f51d5728f_norender_v5_screen_size.tar.gz instead
(x, not shown, black screen) # unzip jh10001-onscripter-jh-a11f51d5728f_patch.zip
# cd jh10001-onscripter-jh-a11f51d5728f/
# nano Makefile.Linux
(comment lua, fontconfig, mod Makefile.Linux)
# make -f Makefile.Linux
# cd ..

# cd onscripter_cn_test/
# SDL_AUDIODRIVER=dummy ../jh10001-onscripter-jh-a11f51d5728f/onscripter
```
