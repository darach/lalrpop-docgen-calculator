# Full Grammar

## Rule Exprs

A comma delimited set of expressions




<img src="svg/Exprs.svg" alt="Exprs" width="220" height="86"/>

```ebnf
rule Exprs ::=
    Comma!(Expr) 
  ;

```



## Rule Comma

A comma delimited set of rules.

No trailing comma permitted.

There may be zero or many rules.



<img src="svg/Comma.svg" alt="Comma" width="267" height="79"/>

```ebnf
macro Comma<T> ::=
    ( T  ',' ) *  T ?  
  ;

```



## Rule Tier

<img src="svg/Tier.svg" alt="Tier" width="409" height="119"/>

```ebnf
macro Tier<Op, NextTier> ::=
    Tier!(Op, NextTier) Op NextTier 
  | NextTier 
  ;

```



## Rule Expr

<img src="svg/Expr.svg" alt="Expr" width="237" height="86"/>

```ebnf
rule Expr ::=
    Tier!(ExprOp, Factor) 
  ;

```



## Rule Factor

<img src="svg/Factor.svg" alt="Factor" width="237" height="86"/>

```ebnf
rule Factor ::=
    Tier!(FactorOp, Term) 
  ;

```



## Rule ExprOp

<img src="svg/ExprOp.svg" alt="ExprOp" width="167" height="75"/>

```ebnf
rule ExprOp ::=
     '+' 
  |  '-' 
  ;

```



## Rule FactorOp

<img src="svg/FactorOp.svg" alt="FactorOp" width="167" height="75"/>

```ebnf
rule FactorOp ::=
     '*' 
  |  '/' 
  ;

```



## Rule Term

<img src="svg/Term.svg" alt="Term" width="283" height="97"/>

```ebnf
rule Term ::=
    Num 
  |  '(' Expr  ')' 
  | 
  ;

```



## Rule Num

One or many decimal digits.



<img src="svg/Num.svg" alt="Num" width="183" height="42"/>

```ebnf
rule Num ::=
     'r#[0-9]+#' 
  ;

```



##

Well, that was fun wasn't it.



