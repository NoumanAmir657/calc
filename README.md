# Calc
Calc is an arithmetic expression language written using LLVM-17

## Build
```
mkdir build

cd build

cmake -GNinja -DCMAKE_C_COMPILER=clang -DCMAKE_CXX_COMPILER=clang++ -DLLVM_DIR=<path to llvm installation configuration> ../

ninja
```

## Run
```
cd build/src

calc "with a: a*3" | llc –filetype=obj -relocation-model=pic –o=expr.o

clang -o expr expr.o rtcalc.c

expr
```