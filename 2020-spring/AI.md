# 智能技术

## Predicate calculus

- Knowledge 【L2-1p3】
    - Categories 【L2-1p7】
        - Procedural, declarative, tacit
    - Metaknowledge 【L2-1p9】
    - The core of knowledge-based systems 【L2-1p11】
    - The goal of knowledge-based systems 【L2-1p12】
    - Importance of knowledge representation 【L2-1p13】

- Logic and sets
    - Basic concept 【L2-1p17】
    - Syllogism (三段论) 【L2-1p19】
    - Venn diagram 【L2-1p20】
    - Sets 【L2-1p21】

### Propositional logic

- Basic concept 【L2-1p26】

- Logical connectives 【L2-1p27】
    - Material implication 【L2-1p29】
    - Biconditional
    - Tautology (重言式), Contradiction (矛盾式), Contingent (偶然式)
    - Implication, logical equivalence

- **Truth table**

- Well-formed formulas (**wff**, 合式公式) 【L2-1p33】
    - Proposition symbols, connectives, truth symbols

### First order predicate logic

- Limitation of propositional logic 【L2-2p2】

- Quantifiers 【L2-2p4】
    - Universal $\forall$
    - Existential $\exists$
    - Negated 【L2-2p15】

- Form of First order predicate logic
    - Simple predicate 【L2-2p7】 p(X, Y, Z)
    - Functions 
    - Compound: using logical connectives

- **wff** 【L2-2p10】
    - Predicate symbols
        - Letters, digits, underscore
    - Connectives
    - Quantifiers
    - Truth symbols
    - () , . 

- 根据自然语言写出wff，或根据wff翻译回自然语言

- Syllogistic logic can be completely described by predicate logic 【L2-2p18】

- Rules of Inference for Propositional Logic 【L2-2p21】

### Resolution Theorem Proving

- Requirements for resolution 【L2-3p4】

- Important feature:Resolution is a sound rule of inference, we can use this rule to reason or prove theorem. 

- Reductio ad absurdum (反证法) 【L2-3p7】

- **Resolution refutation** (归结反驳)
    - Try to prove the negated clause is a theorem. 
    - Through resolution process, the empty clause(nil,null,false) will always be the eventual result in a finite number of steps if there is a contradiction. 
    - The original non negated clause is a theorem. 

- **Converting** First Order Predicate wffs to Clausal Form 【L2-3p12】
    - Eliminate conditionals
    - When possible, eliminate negations or reduce the scope of negation to one atom
    - Standardize variables within a wff so that the bound(or dummy) variables of each quantifier have unique names
    - Eliminate existential quantifiers using Skolem functions
    - Convert wff to prenex form, which is a sequence of quantifiers $\forall$
    - Convert the matrix to conjunctive of clauses $\land$
    - Drop the universal quantifiers
    - Eliminate $\land$ signs by writing the wff as a set of clauses
    - Rename variables in clauses so that the same variable name is used in only one clause

- Unification 【L2-3p17】
    - Substitution
    - **Most general unifier** (mgu) 【L2-3p21】
    - Unification algorithm 【L2-3p24】

## State space search

- Graph

### State space search

- Data-driven

- Goal-driven

- Backtracking

- Breadth-first search

- Depth-first search

- Using State Space to Represent Reasoning with Predicate Logic

### Heuristic search 【L2-3p49】

### Hill-Climbing 【L2-3p58】

- It can not recover from failures, without backtracking because it keeps no history

- Major problem: local maxima

### Best-first search 【L2-3p62】

- General evaluation function 【L2-3p66】

- Algorithm A and A* 【L2-3p69】

- Effectiveness of a heuristic search algorithm 【L2-3p71】
    - Admissible
    - Monotone
    - Informedness

### Heuristics in games

- Minimax 【L2-3p76】
    - N-ply look-ahead 【L2-3p84】

- **$\alpha - \beta$ pruning** 【L2-3p93】

## Introduction to prolog

## Reasoning in uncertain situation




