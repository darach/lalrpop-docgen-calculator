## EBNF Grammar

This EBNF grammar was generated from: "calculator.lalrpop"

```ebnf


rule Exprs ::=
    Comma!(Expr) 
  ;

macro Comma<T> ::=
    ( T  ',' ) *  T ?  
  ;

macro Tier<Op, NextTier> ::=
    Tier!(Op, NextTier) Op NextTier 
  | NextTier 
  ;

rule Expr ::=
    Tier!(ExprOp, Factor) 
  ;

rule Factor ::=
    Tier!(FactorOp, Term) 
  ;

rule ExprOp ::=
     '+' 
  |  '-' 
  ;

rule FactorOp ::=
     '*' 
  |  '/' 
  ;

rule Term ::=
    Num 
  |  '(' Expr  ')' 
  | 
  ;

rule Num ::=
     'r#[0-9]+#' 
  ;

```

