# Contents
- [Contents](#contents)
- [Topics in the Module](#topics-in-the-module)
- [Functional Dependency](#functional-dependency)
  - [Armstrong number](#armstrong-number)
- [2 NF](#2-nf)
- [3 NF](#3-nf)
- [BCNF ( Boyce-Codd )](#bcnf--boyce-codd-)

# Topics in the Module 
- Database Design and Normal Forms
  - An Example
- Problems with bad schema
- Update Anomalies
- Normal Forms
- Functional Dependencies
  - Functional Dependencies – Examples
- Trivial / Non-Trivial FDs and Notation
  - FDs – Examples
- Deriving new FDs
- Entailment Relation
- Armstrong’s Inference Rules
- Sound and Complete Inference Rules
  - Proving Soundness
  - Proving Completeness of Armstrong’s Axioms 
  - Completeness of Armstrong’s Axioms
  - Completeness Proof 
  - Consequence of Completeness of AA
- Computing closures
  - Computing X+F
  - Attribute Closures – An Example
- Normal Forms – 2NF
  - Example 1: 2NF
  - Example 2: 2NF
- Transitive Dependencies
- Normal Forms – 3NF
  - Another definition of 3NF
- Motivating example for BCNF
- Boyce - Codd Normal Form (BCNF)
  - Decomposition of a relation schema
  - Desirable Properties of Decompositions
  - Lossless join property
  - Dependency Preserving Decompositions
    - An example
  - Testing for lossless decomposition property
  - A property of lossless joins
  - Algorithm for BCNF decomposition


# Functional Dependency
- Non trivial (+ Completely NT) and Trivial
- full functional dependency : No subset of X can give Y
- Notation : A,B,C -> single attributes AND X,Y,Z -> Sets of Attributes
- Unless all FDs are known, a relation schema is not fully specified

## Armstrong number
1.	Reflexivity 	 :  If Y ⊆ X ⇒ X → Y	        Obvious self-contained FD
2.	Augmentation	 :  If X → Y ⇒ XZ → YZ	        Add same attributes to both sides
3.	Transitivity	 :  If X → Y and Y → Z ⇒ X → Z	Like a chain reaction
4.	Decomposition	 :  If X → YZ ⇒ X → Y, X → Z	Break multi-attributes
5.	Union	         :  If X → Y, X → Z ⇒ X → YZ	Combine dependencies
6.	Pseudo-transitive:	If X → Y, WY → Z ⇒ WX → Z	Combine indirect inferences
- 1,2,3 -> Axioms : Soundness and Completeness 
 
# 2 NF
- Composite key : Candidate Keys with >1 attributes
- Full dependency of non-prime attributes on Candidate keys 
- No (partial dependency of non-prime attributes on PART of composite keys)

# 3 NF
- It has no transitive dependency from non-prime attributes on a key
- For any nontrivial FD X → A,
Either X is a superkey,
Or A is a prime attribute (part of some candidate key) <br>
i.e. Make sure non-prime attributes are not transitively dependent on anything that isn't a superkey

# BCNF ( Boyce-Codd )
- Make sure that in all non trivial FD , **X must be Super key** 