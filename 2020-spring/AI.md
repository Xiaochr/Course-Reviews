# 智能技术

只记考试范围内的。Prolog编程不考，神经网络不考。

Slides Google Drive 链接：[智能技术-2020春](https://drive.google.com/drive/folders/1XzRjCxQk5NUCTm--DPcmiRDRP7dSbk5z?usp=sharing)

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
    - Simple predicate 【L2-2p7】 p(X, Y, Z) p: 可以多个字母，但一定要小写字母开始！而变量X要以大写字母开始
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

---

## State space search

- Graph

### State space search

- Data-driven

- Goal-driven

- Backtracking 【book p68】
    - SL, NSL, DE

- Breadth-first search
    - Closed, open 
    - 新的加在closed**右边**

- Depth-first search
    - Closed, open 
    - 新的加在closed**左边**

- Using State Space to Represent Reasoning with Predicate Logic

### Heuristic search 【L3p49】

#### Hill-Climbing 【L3p58】

- It can not recover from failures, without backtracking because it keeps no history

- Major problem: local maxima

#### Best-first search 【L3p62】

- Closed, open 在closed中要排序 【book p94】

- General evaluation function 【L3p66】

- Algorithm A and A* 【L3p69】
    - Best-first search: A
    - $h(n)$ is less than or equal to the cost of the min path from n to goal: A*

- Effectiveness of a heuristic search algorithm 【L3p71】
    - Admissible: A* is admissible
    - Monotone
    - Informedness

#### Heuristics in games

- Minimax 【L3p76】
    - N-ply look-ahead 【L3p84】

- **$\alpha - \beta$ pruning** 【L3p93】

---

## Introduction to prolog

- Representing facts, rules and goals

- Backtracking, recursion and prolog reasoning
    - 回溯
    - 修改clause的顺序来避免死循环

- List and recursion
    - Unification can be used to build list structure

- Use cut to control search

---

## Reasoning in uncertain situation

- Concept of uncertainty 【L6p3】
    - 证据/已知事实的不确定性
    - 规则/知识的不确定性
    - 结论的不确定性

- 不确定性度量、计算方法 【L6p6】

### Bayes theory

- 全概率公式、贝叶斯公式 【L6p13】

- 不同情形
    - 证据组合的不确定计算 【L6p17】
    - 顺序规则的不确定计算 【L6p19】
    - 并行规则的不确定计算
    - 其他情形
        - 多个证据支持一个结论
        - 一个证据支持多个结论
        - 多个证据支持多个结论

### Bayesian belief network

- D-seperation 【L6p32】
    - A path is blocked if there is an intermediate node V in the path with either the properties: 
        - The connection is serial or diverging and the state of V is known. 
        - The connection is converging and neither V nor any of V's children have evidence. 

- 联合概率分布 【L6p35】

### Certainty factors

- 信任增长度与不信任增长度 【L6p39】
    - MB(h, e), MD(h, e)

- 可信度 【L6p43】
    - CF(h, e) = MB(h, e) - MD(h, e)

- 带阈值的不确定推理
    - 组合证据的不确定计算
        - 证据的合取、析取 【L6p50】
    - 并行规则的不确定计算 【L6p51】
    - 顺序规则的不确定计算

- 加权的不确定推理 【L6p56】
    - 证据组合的不确定计算

---

[Back to top](#智能技术)

