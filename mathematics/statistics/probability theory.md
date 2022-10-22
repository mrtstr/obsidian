# Probability theory
- Formalities probability in a [[probability space]]
- provides a [[probability measure]] for [[set|sets]] of outcomes out of the [[sample space]]

#### basic axioms
- $0 \leq P(A) \leq 1$
- $P(\Omega) = 1$
- $P(\emptyset) = 0$
- $P(\overline{A}) = 1- P(A)$
- $A \subseteq B \Leftrightarrow P(A) \leq P(B)$

#### Probability of [[disjunct]] [[set|sets]]
[[disjunct]] sets $A,B \in \mathcal{F}$ in a [[event space]]  
- $P(A \cup B)=P(A) + P(B)$
- $P(A \cap B) = P(A) \cdot P(B)$


#### decomposition in [[disjunct]] [[set|sets]]
The [[union]] of two [[set|sets]] can be decomposed in tow [[disjunct]] [[set|sets]] 
$$A \cup B = B \cup (A \cap \overline{B}) = A \cup (B \cap \overline{A})$$

Proof:
$$
B \cup (A \cap \overline{B}) 
=(B \cup A) \cap (B \cup \overline{B}) = A \cup B
$$

#### Theorem $P(A \cap \overline{B}) = P(A) - P(A \cap B)$
Probability of A and not B is equal to the probability of A minus the probability of A and B.
Proof

$$
P(A)=P(A\cap B) + P(A\cap \overline{B})
\Leftrightarrow 
P(A \cap \overline{B}) = P(A) - P(A \cap B)
$$
#### Theorem $P(A \cup B) = P(A) + P(B) - P(A \cup B)$
The probability of A or B is equal the probability of A plus the probability of B minus the probability of A and B.
Proof
$$
P(A \cup B) 
= P(A \cap (A \cup \overline{B})) 
= P(A) + P(A \cup \overline{B})
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
Tags: mathematics, statistics
<!--ID: 1666457499357-->
END


START
Basic
probability of [[disjunct]] [[set|sets]]
Back: 
[[disjunct]] sets $A,B \in \mathcal{F}$ in a [[event space]]  
- $P(A \cup B)=P(A) + P(B)$
- $P(A \cap B) = P(A) \cdot P(B)$
Tags: mathematics, statistics
<!--ID: 1666457499359-->
END


START
Basic
probability:
decomposition of the [[union]] of two [[set|sets]] two in [[disjunct]] [[set|sets]]

Back: 
The [[union]] of two [[set|sets]] can be decomposed in tow [[disjunct]] [[set|sets]] 
$$A \cup B = B \cup (A \cap \overline{B}) = A \cup (B \cap \overline{A})$$
Proof:
$$
B \cup (A \cap \overline{B}) 
=(B \cup A) \cap (B \cup \overline{B}) = A \cup B
$$
Tags: mathematics, statistics
<!--ID: 1666457499361-->
END


START
Basic
probability:
Theorem $P(A \cap \overline{B})=$ ?
Back: 
Theorem $P(A \cap \overline{B}) = P(A) - P(A \cap B)$
Probability of A and not B is equal to the probability of A minus the probability of A and B.
Proof

$$
P(A)=P(A\cap B) + P(A\cap \overline{B})
\Leftrightarrow 
P(A \cap \overline{B}) = P(A) - P(A \cap B)
$$

Tags: mathematics, statistics
<!--ID: 1666457499364-->
END


START
Basic
probability:
Theorem: $P(A \cup B) =$ ?
Back: 
Theorem $P(A \cup B) = P(A) + P(B) - P(A \cup B)$
The probability of A or B is equal to the probability of A plus the probability of B minus the probability of A and B.
Proof
$$
P(A \cup B) 
= P(A \cap (A \cup \overline{B})) 
= P(A) + P(A \cup \overline{B})
= P(B) + P(A) - P(A \cap B)
$$

Tags: mathematics, statistics
<!--ID: 1666457499366-->
END


START
Basic
probability:
basic axioms
- $P(A) \in$ ?
- $P(\Omega) =$ ?
- $P(\emptyset) =$ ?
- $P(\overline{A}) =$ ?
- $A \subseteq B \Leftrightarrow$ ?
Back: 
- $0 \leq P(A) \leq 1$
- $P(\Omega) = 1$
- $P(\emptyset) = 0$
- $P(\overline{A}) = 1- P(A)$
- $A \subseteq B \Leftrightarrow P(A) \leq P(B)$
Tags: mathematics, statistics
<!--ID: 1666457499369-->
END