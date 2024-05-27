# Probability theory
- Formalities probability in a [[probability space]]
- provides a [[probability measure]] for [[set|sets]] of outcomes out of the [[sample space]]

## basic axioms
### General [[event space|events]] $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $0 \leq P(A) \leq 1$
- $P(\Omega) = 1$
- $P(\emptyset) = 0$
- $P(\overline{A}) = 1- P(A)$
- $A \subseteq B \Leftrightarrow P(A) \leq P(B)$

### [[stochastic exclusive]] [[event space|events]] ([[mathematics/basics/disjoint]] [[set|sets]])  $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $P(A \cup B)=P(A) + P(B)$
- $P(A \cap B) = 0$
### [[stochastic independent]] [[event space|events]] $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $P(A \cap B) = P(A)P(B)$


## Theorems
### decomposition in [[mathematics/basics/disjoint]] [[set|sets]]
The [[union]] of two [[set|sets]] can be decomposed in tow [[mathematics/basics/disjoint]] [[set|sets]] 
$$A \cup B = B \cup (A \cap \overline{B}) = A \cup (B \cap \overline{A})$$

Proof:
$$
B \cup (A \cap \overline{B}) 
=(B \cup A) \cap (B \cup \overline{B}) = A \cup B
$$

### Theorem $P(A \cap \overline{B}) = P(A) - P(A \cap B)$
Probability of A and not B is equal to the probability of A minus the probability of A and B.
Proof

$$
P(A)=
P(A \cap (B \cup \overline{B}))
=P(A\cap B) + P(A\cap \overline{B})
\Leftrightarrow 
P(A \cap \overline{B}) = P(A) - P(A \cap B)
$$
### Theorem $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
The probability of A or B is equal to the probability of A plus the probability of B minus the probability of A and B.
Proof
$$
P(A \cup B) 
= P(A \cup (A \cap \overline{B})) 
= P(A) + P(A \cap \overline{B})
= P(B) + P(A) - P(A \cap B)
$$

## discrete probability 
→ in a [[probability space]] with a [[countable]] [[sample space]]


## continuous probability
→ in a [[probability space]] with a [[countable|non-countable]] [[sample space]]



START
Basic
probability theory: difference between continuous and discrete probability 
Back: 
continuous probability:
probability in a [[probability space]] with a [[countable|non-countable]] [[sample space]]

discrete probability: 
probability in a [[probability space]] with a [[countable]] [[sample space]]
Tags: mathematics statistics
<!--ID: 1666457499357-->
END





START
Basic
probability:
decomposition of the [[union]] of two [[set|sets]] two in [[mathematics/basics/disjoint]] [[set|sets]] (with proof)

Back: 
The [[union]] of two [[set|sets]] can be decomposed in tow [[mathematics/basics/disjoint]] [[set|sets]] 
$$A \cup B = B \cup (A \cap \overline{B}) = A \cup (B \cap \overline{A})$$
Proof:
$$
B \cup (A \cap \overline{B}) 
=(B \cup A) \cap (B \cup \overline{B}) = A \cup B
$$
Tags: mathematics statistics
<!--ID: 1666457499361-->
END


START
Basic
probability:
Theorem $P(A \cap \overline{B})=$ ?  (with proof)
Back: 
Theorem $P(A \cap \overline{B}) = P(A) - P(A \cap B)$
Probability of A and not B is equal to the probability of A minus the probability of A and B.
Proof

$$
P(A)=
P(A \cap (B \cup \overline{B}))
=P(A\cap B) + P(A\cap \overline{B})
\Leftrightarrow 
P(A \cap \overline{B}) = P(A) - P(A \cap B)
$$

Tags: mathematics statistics
<!--ID: 1666457499364-->
END


START
Basic
probability:
Theorem: $P(A \cup B) =$ ?  (with proof)
Back: 
Theorem $P(A \cup B) = P(B) + P(A) - P(A \cap B)$
The probability of A or B is equal to the probability of A plus the probability of B minus the probability of A and B.
Proof
$$
P(A \cup B) 
= P(A \cup (A \cap \overline{B})) 
= P(A) + P(A \cap \overline{B})
= P(B) + P(A) - P(A \cap B)
$$

Tags: mathematics statistics
<!--ID: 1666457499366-->
END


START
Basic
probability: basic axioms
General [[event space|events]] $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$:
- $P(A) \in$ ?
- $P(\Omega) =$ ?
- $P(\emptyset) =$ ?
- $P(\overline{A}) =$ ?
- $A \subseteq B \Leftrightarrow$ ?

[[stochastic exclusive]] [[event space|events]] ([[mathematics/basics/disjoint]] [[set|sets]])  $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $P(A \cup B)=$ ?
- $P(A \cap B) =$ ?
[[stochastic independent]] [[event space|events]] $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $P(A \cap B) =$ ?
Back: 

### General [[event space|events]] $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $0 \leq P(A) \leq 1$
- $P(\Omega) = 1$
- $P(\emptyset) = 0$
- $P(\overline{A}) = 1- P(A)$
- $A \subseteq B \Leftrightarrow P(A) \leq P(B)$

### [[stochastic exclusive]] [[event space|events]] ([[mathematics/basics/disjoint]] [[set|sets]])  $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $P(A \cup B)=P(A) + P(B)$
- $P(A \cap B) = 0$
### [[stochastic independent]] [[event space|events]] $A,B \in \mathcal{F}=\mathcal{P}(\Omega)$
- $P(A \cap B) = P(A)P(B)$

Tags: mathematics statistics
<!--ID: 1666457499369-->
END



START
Basic
probability:
can [[stochastic exclusive]] [[event space|events]] be [[stochastic independent]]?
Back: 
only if $P(A)=0$
Tags: mathematics statistics
<!--ID: 1666517556858-->
END


START
Basic
Suppose that 10,000 tickets are sold in one lottery and
5000 tickets are sold in another lottery. If a person owns
100 tickets in each lottery, what is the probability that she
will win at least one first prize?
Back: 
$P(A \cup B) = P(B) + P(A) - P(A \cap B)=0.01 + 0.02 − (0.01)(0.02) = 0.0298$
Tags: mathematics statistics
<!--ID: 1667051814880-->
END