# PCREW Implementation

abstract : PCREW Implementations and Language Implementation loadmap and details

1. PepCrew (perl env pcrew)  # perl + sh to pepcrew + perl
1. 1. pcrew (initial) (0.0.1a) # perl + sh
1. 1. 1. pcrew::APP # perl
1. 1. 2. pcrew::IO (not fIO function included) # perl
1. 1. 3. pcrew::compile # perl
1. 1. 4. pcrew::runtime # perl
1. 1. 5. pcrewc.sh # sh
1. 2. pcrew (non-initial) (0.0.1b ~) # perl
1. 2. 1. pcrew::APP
1. 2. 2. pcrew::IO (fIO function included)
1. 2. 3. pcrew::bootstrap (add at 0.0.1c)
1. 2. 4. pcrew::compile
1. 2. 5. pcrew::runtime
2. CepCrew (C env pcrew) # pepcrew + perl + C to pcrew + perl + C to pcrew + C
2. 1. cepcrew (initial) (0.0.1a) # pepcrew + perl + C
2. 1. 1. compiler # pepcrew (before compile)
2. 1. 2. 
2. 1. cepcrew (initial) (0.0.1b)  # pcrew + perl + C to pcrew + C to cepcrew + C
2. 1. 1. compiler # pcrew (before compile)
2. 1. 2. cepcrewc::compiler # pcrew (after compile)
2. 1. 2. cepcrec::APP # perl
2. 1. 3. cepcrew/runtime.h
2. 1. 4. cepcrew/IO.h
2. 2. cepcrew (bootstrap start 0.0.1c) # pcrew + C
2. 2. 1. compiler # pcrew (before compile)
2. 2. 2. cepcrewc/compiler.h # pcrew (after compile)
2. 2. 3. cepcrewc/APP.h # C
2. 2. 4. cepcrew/runtime.h # C
2. 2. 5. cepcrew/IO.h # C
2. 3. cepcrew (0.0.1d ~) # cepcrew + C
2. 3. 1. cepcrew/compiler # cepcrew
2. 3. 2. cepcrew/bootstrap.h # C
2. 3. 3. cepcrew/compiler.h # C
2. 3. 4. cepcrew/APP.h # C
2. 3. 5. cepcrew/runtime.h # C
2. 3. 6. cepcrew/IO.h # C
3. LepCrew (LLVM env pcrew)

## PepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| perl | perl | pcrew::runtime 'pepcrew' | perl pcre s/$v1/$v2/gm |

### runtime

pepcrew::MyIO
pepcrew::runtime

### bootstrap start compiler env

pure perl (pepcrew 0.0.1 compiler)

pepcrew::pepcrewcInitial

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
