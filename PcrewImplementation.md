# PCREW Implementation

abstract : PCREW Implementations and Language Implementation loadmap and details

1. PepCrew (perl env pcrew)
2. CepCrew (C env pcrew)
3. LepCrew (LLVM env pcrew)

## PepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| perl | perl | pcrew::runtime 'pepcrew' | perl pcre s/$v1/$v2/gm |

## CepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| C | pcrew + C (bootstrap compiler started by pcrew + perl) | cepcrew.h cepcrew | PCRE2 |

## LepCrew

| runtime lang | compiler lang | runtime by | pcre by |
| :---: | :---: | :---: | :---: |
| LLVM clang compiled starndard C | pcrew + LLVM clang compiled starndard C | lepcrew.h lepcrew | To Be Confirmed (find out the way of PCRE2 VM Bytecode 2 LLVM IR JIT : not startad yet) |
