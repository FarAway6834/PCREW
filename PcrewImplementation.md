# PCREW Implementation

abstract : PCREW Implementations and Language Implementation loadmap and details

1. PepCrew (perl env pcrew)
2. CepCrew (C env pcrew)
3. LepCrew (LLVM env pcrew)

## PepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| perl | perl | pcrew::runtime 'pepcrew' | perl pcre s/$v1/$v2/gm |

### runtime

### bootstrap start compiler env

pure perl (pepcrew 0.0.1 compiler)

### bootstrap compiler env

#### pepcrew::FileIO

 * check by isFile(filename)
 * generate by fIO(filename, "")
 * write by fIO(filename, value)
 * read by fIO(filename)

#### pepcrew::compiler

 * load pepcrew::FileIO
 * compiler logic by pcrewc
 * compiler_main(fIO, pcrewc)(filename) : fIO read -> pcrewc -> `fIO filecheck` -> IF NOT EXIST, `fIO generate` -> fIO write

#### pepcrew 0.0.1 compiler : pepcrew::pepcrewcInitial
 * load pepcrew::compiler
 * run = compiler_main(fIO, pcrewc)

#### pepcrew compiler : pepcrew::APP's run

## CepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| C | pcrew + C (bootstrap compiler started by pcrew + perl) | cepcrew.h cepcrew | PCRE2 |

### runtime

### bootstrap start compiler env

cepcrew 0.0.1a compiler (file I/O by perl)

### bootstrap compiler env

## LepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| LLVM clang compiled starndard C | pcrew + LLVM clang compiled starndard C (bootstrap compiler started by cepcrew + C) | lepcrew.h lepcrew | To Be Confirmed (find out the way of PCRE2 VM Bytecode 2 LLVM IR JIT : not startad yet) |



### runtime

### bootstrap start compiler env

### bootstrap compiler env
