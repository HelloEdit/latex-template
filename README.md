<h1 align="center">
    LaTeX Template
</h1>

<p align="center">
    <em>A basic template for writing my documents in LaTeX</em>
</p>

### Features

- Use cmake with [`UseLATEX.cmake`](https://gitlab.kitware.com/kmorel/UseLATEX)
- Out-of-the-box Multi-file LaTeX projects (with `subfiles`)
- Mathematical writing oriented (support of `asmmath`, `asmthm`, `mathtools`...)

### Structure

```
├── CMakeLists.txt
├── includes
│   └── UseLATEX.cmake
├── README.md
└── source
    ├── images
    ├── main.tex
    ├── packages
    │   └── preamble.sty
    └── partials
        └── sample.tex
```

- `CMakeLists.txt` file contains a set of directives and instructions for `cmake` describing the project's source files.
- `includes/` directory contains all the scripts necessary for the project.
- `source/` directory contains all LaTeX related files.
- `source/images` directory contains all the images of the project.
- `source/main.tex` file is the main LaTeX file of your project.
- `source/packages` directory contains all the packages provided by the user.
- `source/packages/preamble.sty` file is a LaTeX package that loads modules and basic configurations.
- `source/partials` directory contains all the LaTeX subfiles.

### Usage

`UseLatex.cmake` is a very powerful tool that allows to abstract the different commands to compile a latex file. Regarding features (enabling BibLaTeX...) or compatibility (especially for Windows users), please refer [to the manual](https://gitlab.kitware.com/kmorel/UseLATEX/-/blob/master/UseLATEX.pdf)

#### Requirements

- A distribution for the TeX typesetting system (`TeX Live` for example)
- `biber` - a bibtex replacement for users of biblatex (if you have to use BibLaTeX)
- `imagemagick` - a free software suite for the creation, modification and display of bitmap images
- `cmake` - cross-platform free and open-source software for build automation
- `make` - GNU make utility to maintain groups of programs

#### Get Started

First, you have to clone the repository on your computer

```shell
$ git clone https://github.com/HelloEdit/latex-template.git
```

After that you need to execute cmake in order to create the targets.

```shell
$ cmake -S . -B build
```

A new directory `build` will be created with all the required make files inside. To build the `pdf`, run the following commands

```shell
$ make -C build pdf --silent
```

You should see at the root of the project a new file `main.pdf`.
