# llwa: LLVM版本凹语言编译器

准备工作区：

```
% mkdir workarea
% cd workarea

// Sources
% git clone https://github.com/llvm/llvm-project.git
...
% cd llvm-project/llvm/tools
% git clone git@github.com:wa-lang/llwa.git gollvm
...
%
```

尝试构建:

```
% cd workarea
% mkdir build-debug
% cd build-debug
% cmake -DCMAKE_BUILD_TYPE=Debug -DLLVM_USE_LINKER=gold -G Ninja ../llvm-project/llvm
...
% ninja gollvm
...
%
```

安装程序:

```
% mkdir build.rel
% cd build.rel
% cmake -DCMAKE_INSTALL_PREFIX=/my/install/dir -DCMAKE_BUILD_TYPE=Release -DLLVM_USE_LINKER=gold -G Ninja ../llvm-project/llvm

// Build all of gollvm
% ninja gollvm
...

// Install gollvm to "/my/install/dir"
% ninja install-gollvm

```

使用:

```
// Root of Gollvm install is /tmp/gollvm-install
% export LD_LIBRARY_PATH=/tmp/gollvm-install/lib64
% export PATH=/tmp/gollvm-install/bin:$PATH
% go run himom.go
hi mom!
%
```

TODO
