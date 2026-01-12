# convention of scps (CoS)

⚠️ warning : [read it (philosophy of convention)](./PhilosophyOfConvention) ⚠️

## 1. structure

CoS coding style (code form) has 3 part.

1. assignment-lterm
2. assignment-rterm's pettern
3. assignment-rterm's repl

code form is `basically` single-line and `espaily` multy-line

because, assignment-rterm's pettern is `basically` single-line and `espaily` multy-line

so, code form is `[1] = s/[2]/[3]/gm`

### 1. assignment-lterm

assignment-lterm is filename
it's function name of the only function of this file

### 2. assignment-rterm's pettern

it have 3 parts

1. function-assignment's normal functions
2. function-assignment's main functions
3. entrypoint-call

and it placed as `(?(DEFINED)[1]|[2]) [3]` (`basically`)

also
```
(
  ?(DEFINED)
    [1]
  |
    [2]
)

[3]
```
allowd (`espacially`)

explanation : `(` to `)` is can be coded as `{` to `}` style conventionally. and also, `|` can coded as `,` style conventionally.

#### 1. function-assignment's normal functions

0. subrootines splited by ` | ` *(blank ``)*

code form is : `(?|[0])`

also see : subrootine coded as `(?<[1]> [2])`  s.t. [1] is subrootine name, and [2] is subrootine src

#### 2. function-assignment's main functions

0. src *(blank ``)*

code form is : `(?<main> [0])`

#### 3. entrypoint-call 

source that `(?&main)`

### 3. assignment-rterm's repl

replace string.

-fin-