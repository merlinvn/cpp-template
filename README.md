# C++ Template Project

This is a basic C++ template project for quickly starting new projects. It includes a basic file structure and CMake build configuration.

## Usage

There are two ways to use this template: creating a new project from scratch and using the "Use this template" function in GitHub.

### Creating a new project from scratch

To create a new project from scratch using this template, first you need to install `go-task` as described in [Installing `go-task`](#installing-go-task) session.
Then simply run the following script in a new folder and start adding your own source files.
```bash
curl https://raw.githubusercontent.com/merlinvn/cpp-template/master/Taskfile.yml -o Taskfile.yml
go-task new

# or `go-task new:vcpkg` to include vcpkg submodule
```
The existing files can be used as a reference for how to structure your project and how to use CMake.

### Using the "Use this template" function in GitHub

Another way to use the template is by clicking the "Use this template" button on the GitHub repository page. This will create a new repository based on the template, allowing you to quickly start a new project without the need to clone the repository and manually set up the files.

You can also choose to create the new repository in your personal account or in an organization where you have write access.

## Prerequisites

Before building the project, you will need to have the following packages installed on your system:

### Ubuntu/Debian
```bash
sudo apt-get install build-essential cmake pkg-config curl zip unzip tar
```

### Red Hat and Fedora derivatives:
```bash
sudo dnf install gcc-c++ cmake pkgconfig curl zip unzip tar
```

### On older Red Hat and Fedora derivatives:
```bash
sudo yum install gcc-c++ cmake pkgconfig curl zip unzip tar
```

### On SUSE Linux and derivatives:
```bash
  sudo zypper install pattern devel_C_C++ cmake pkgconfig curl zip unzip tar
```

### On Arch Linux and derivatives:
```bash
sudo pacman -S base-devel cmake pkg-config curl zip unzip tar cmake ninja
```

### On Alpine:
```bash
  apk add build-base cmake ninja zip unzip curl git
  (and export VCPKG_FORCE_SYSTEM_BINARIES=1)
```

## Installing `go-task`

In order to build the project using `go-task`, you will need to have go-task installed on your system.
The simplest way to install `go-task` is by using `curl`:

```bash
sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b ~/.local/bin
```

You can add an terminal aliases for your convinient:
```
alias t=go-task
```

For other ways to install `go-task` please refer to [go-task installation](https://taskfile.dev/installation/) page

## Building

The project can be built using either [go-task](https://github.com/go-task/task) or [CMake](https://cmake.org/).

### go-task

To build the project using go-task, you will need to have go-task installed on your system. Once go-task is installed, simply run the following command in the root directory of the project:

```bash
go-task build
```

The default generator is `Ninja`, to generate `Unix Makefiles` project, you can run

```bash
go-task build GENERATOR='"Unix Makefiles"'
```

Default build will build `Release`. To build `Debug`, run the following command:
```bash
go-task build:debug

# or

go-task build CONFIG=Debug
```
Other possible values for `CONFIG` are `RelWithDebInfo` and `MinSizeRel`

### CMake

To build the project using CMake, run the following commands in the root directory of the project:

```bash
mkdir build
cd build
cmake .. -DCMAKE_EXPORT_COMPILE_COMMANDS=1 -DCMAKE_BUILD_TYPE=Release
make
```

## Clean

To remove `build` folder, run the following command:
```bash
go-task clean

#or
rm -rf build
rm -f compile_commands.json
```

## TODO
- add .clang-format
- add .clang-tidy
- github actions??
