# PCREW Implementation

abstract : PCREW Implementations and Language Implementation loadmap and details

1. SCPS
2. PepCrew (perl env pcrew)  # perl + sh to pepcrew (SCPS) + perl
   * 1.1. pcrew (initial) (0.0.1a) # perl + sh
     * 1.1.1. pcrew::APP # perl
     * 1.1.2. pcrew::IO (not fIO function included) # perl
     * 1.1.3. pcrew::compile # perl
     * 1.1.4. pcrew::runtime # perl
     * 1.1.5. pcrewc.sh # sh
   * 1.2. pcrew (bootstrap start 0.0.1b) # perl
     * 1.2.1. pcrew::APP
     * 1.2.2. pcrew::IO (fIO function included)
     * 1.2.3. pcrew::compile
     * 1.2.4. pcrew::runtime
   * 1.3. pcrew (non-initial) (0.0.1c ~) #perl
     * 1.3.1. pcrew::APP
     * 1.3.2. pcrew::IO (fIO function included)
     * 1.3.3. pcrew::bootstrap
     * 1.3.4. pcrew::compile
     * 1.3.5. pcrew::runtime
3. CepCrew (C env pcrew) # pepcrew + perl + C + sh to pcrew + C to cepcrew + C
   * 2.1. cepcrew (perl to C machanism, for make initial) (0.0.1a) # pepcrew + perl + C + sh
     * 2.1.1. APP # pepcrew (before compile)
     * 2.1.2. cepcrew::APP # perl (after compile)
     * 2.1.3. cepcrewc.sh # sh
     * 2.1.4. cepcrew/runtime.h # C
     * 2.1.5. cepcrew/IO.h # C
   * 2.2. cepcrew (initial) (0.0.1b)  # pcrew + C
     * 2.2.1. cepcrew/compiler # pcrew
     * 2.2.2. cepcrew/APP.h #C
     * 2.2.3. cepcrew/compiler.h # C
     * 2.2.4. cepcrew/runtime.h # C
     * 2.2.5. cepcrew/IO.h # C
   * 2.3. cepcrew (0.0.1c ~) # cepcrew + C
     * 2.3.1. cepcrew/compiler # cepcrew
     * 2.3.2. cepcrew/bootstrap.h # C
     * 2.3.3. cepcrew/compiler.h # C
     * 2.3.4. cepcrew/APP.h # C
     * 2.3.5. cepcrew/runtime.h # C
     * 2.3.6. cepcrew/IO.h # C
3. LepCrew (LLVM env pcrew)

## SCPS : selfhosting compiler pcrew script

pcrew is compile language. and also it's bootstrap compiler. and actually bootstrap compiler is self-hosting compiler.

so, pcrew compiler is self-hosting compiler, and as you know self-hosting compiler is writed by it self, so.

pcrew compiler is writed by pcrew

SCPS is actually pcrew compiler's pcrew source code script file

and also it have some [convention for maintenance (actually not for maintenance. I like that form to programming. that's all)](./conventionOfscps)

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
