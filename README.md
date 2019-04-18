# openc2e

openc2e is an open-source game engine intended to run all the games in the
[_Creatures_](https://creatures.wiki) series.

# Games

openc2e is intended to support:

* Creatures (1996)
* Creatures 2 (1998)
* Creatures 3 (1999)
* Docking Station (2001)
* Creatures Playground (1999)
* Creatures Adventures (2000)

# Status

## Working

* Agents (COBs) work
* Imperfect physics
* Creatures biochemestry
* Sound effects

## Todo

* Actual creatures (C3+ creatures work somewhat, C1 and C2 ones don't work at all)
* Physics improvements (Especially C3+)
* Network ability (the Docking Station warp)
* Serialization (world saving, creature exporting, ...)
* Music

There are lots of [open issues on the old Google Code issue tracker](https://code.google.com/archive/p/openc2e/issues) that still need solving.

# Building

## Dependencies

openc2e depends on:

* SDL 1.2
  * SDL_gfx
  * SDL_mixer
  * SDL_ttf
  * SDL_net
* OpenAL
* re2c
* Perl
  * The YAML module
* Qt4
* boost
* CMake

### Linux

On Ubuntu 18.10 you'll need these packages:

```bash
sudo apt-get install \
  build-essential \
  qt4-qmake \
  libqt4-dev \
  libsdl-gfx1.2-dev \
  libsdl-net1.2-dev \
  libsdl-mixer1.2-dev \
  libsdl-ttf2.0-dev \
  libyaml-perl \
  re2c \
  libalut-dev \
  libboost-all-dev
```

### macOS

Install dependencies using [Homebrew](https://brew.sh):

```bash
brew install sdl sdl_mixer sdl_gfx sdl_net sdl_ttf re2c cmake boost
brew tap cartr/qt4
brew tap-pin cartr/qt4
brew install qt@4
```

Getting the YAML module is a little trickier, you'll have to set up CPAN. Doing
so is beyond the scope of this README, but you might find some help
[here](https://docs.brew.sh/Gems,-Eggs-and-Perl-Modules#perl-cpan-modules-without-sudo).

### Windows

Good luck! Open a PR if you get a good process for building on Windows.

## Compiling

Create a new build directory and compile:

```bash
cmake -B build .
make -C build openc2e -j4
```

## Running

You need to provide openc2e with the path to the game's data, for example:

```bash
./build/openc2e -d /path/to/Creatures2
```
