### networkmask
- used for dividing an [[ip V4]] adress in [[network adress]] and [[host adress]]
- property of a [[network|subnet]]
- the [[network adress]] of a given [[internet protocol (IP)]] adress can calculcated by connection the [[internet protocol (IP)|ip adress]] and the [[networkmask]] with a bitwise and
- consits of $n$ times `1` followed by $32-n$ times `0`
$$
Networkadress = Adress \: \& \: Networkmask
$$