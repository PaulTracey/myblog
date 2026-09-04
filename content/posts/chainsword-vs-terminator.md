+++
date = 2026-07-30T17:01:00+01:00
draft = false
title = "The Maths Behind a Space Marine Chainsword Attacking a Terminator"
description = "A probability breakdown of a Space Marine attacking a Terminator with an Astartes chainsword in Warhammer 40,000 11th edition."
tags = ["Warhammer 40,000", "Maths", "Probability", "Space Marines"]
categories = ["Tabletop Gaming"]
+++



How likely is an ordinary Space Marine to damage a Terminator with an Astartes chainsword?



Terminators are among the toughest infantry in Warhammer 40,000, while the chainsword is one of the most recognisable weapons carried by the Adeptus Astartes. This makes the matchup a useful example for understanding how hit rolls, wound rolls, saving throws, and probability work together.



This calculation uses the Warhammer 40,000 11th-edition rules and assumes there are no Stratagems, Detachment bonuses, rerolls, character abilities, or other modifiers.



## Profiles used



For this example, the Astartes chainsword has the following profile:



| Attacks | Weapon Skill | Strength | Armour Penetration | Damage |

| ------: | -----------: | -------: | -----------------: | -----: |

|       4 |           3+ |        4 |                 -1 |      1 |



The current Space Marine faction material lists the standard Astartes chainsword as four attacks, hitting on a 3+, at Strength 4, AP -1, and Damage 1.



The Terminator is assumed to have:



| Toughness | Save | Wounds |

| --------: | ---: | -----: |

|         5 |   2+ |      3 |



Terminators retain their 2+ armour save, Toughness 5, and three wounds, making them highly resistant to low-strength, low-damage attacks.



## Step 1: Probability of hitting



The Space Marine has a Weapon Skill of 3+, so each attack hits on a roll of:



```text

3, 4, 5, or 6

```



That gives four successful results from six possible results:



```text

Probability of hitting = 4 ÷ 6

&#x20;                      = 2 ÷ 3

&#x20;                      = 66.7%

```



With four attacks, the expected number of hits is:



```text

4 × 2/3 = 2.67 hits

```



This does not mean the Marine will always score 2.67 hits. It means that over many combats, the average will approach approximately 2.67 hits per attack sequence.



## Step 2: Probability of wounding



The chainsword has Strength 4, while the Terminator has Toughness 5.



Because the weapon's Strength is lower than the target's Toughness, the Marine wounds on a 5+.



The successful results are:



```text

5 or 6

```



Therefore:



```text

Probability of wounding = 2 ÷ 6

&#x20;                        = 1 ÷ 3

&#x20;                        = 33.3%

```



The expected number of successful wounds before saving throws is:



```text

2.67 × 1/3 = 0.89 wounds

```



## Step 3: Probability of failing the save



The Terminator normally has a 2+ armour save.



The chainsword has AP -1, which reduces the Terminator's effective armour save to 3+.



The Terminator therefore saves on:



```text

3, 4, 5, or 6

```



and fails on:



```text

1 or 2

```



The probability of failing the save is:



```text

Probability of failed save = 2 ÷ 6

&#x20;                          = 1 ÷ 3

&#x20;                          = 33.3%

```



## Probability of one attack causing damage



To cause damage, a single attack must:



1\. Hit.

2\. Wound.

3\. Pass through the Terminator's armour.



The probabilities are multiplied together:



```text

2/3 × 1/3 × 1/3 = 2/27

```



Therefore:



```text

Probability of one attack causing damage = 7.41%

```



Each successful attack inflicts one point of damage.



## Expected damage from one Space Marine



The Marine makes four attacks:



```text

4 × 2/27 = 8/27

```



This gives:



```text

Expected damage = 0.296

```



Rounded more simply:



> One Space Marine with an Astartes chainsword inflicts approximately 0.3 wounds on a Terminator per Fight phase.



In practical terms, one Marine will usually fail to damage the Terminator at all.



## Can one Marine kill the Terminator?



A Terminator has three wounds, so the Marine must cause at least three unsaved wounds from four attacks.



The probability of achieving three or four successful damaging attacks is approximately:



```text

0.154%

```



That is roughly:



```text

1 chance in 651

```



A lone Marine can technically kill a full-health Terminator with a chainsword, but it is extremely unlikely.



## What about a five-Marine squad?



Five Marines make:



```text

5 × 4 = 20 attacks

```



The expected damage is:



```text

20 × 2/27 = 1.48 wounds

```



The probability of causing at least three wounds and killing one full-health Terminator is approximately:



```text

18.1%

```



Therefore, a five-Marine squad is still unlikely to kill a Terminator in a single Fight phase using only standard chainswords.



## What about a ten-Marine squad?



Ten Marines make:



```text

10 × 4 = 40 attacks

```



The expected damage is:



```text

40 × 2/27 = 2.96 wounds

```



This is almost exactly the three wounds required to kill a Terminator.



However, expected damage is not the same as the probability of a kill. The probability that the unit causes at least three unsaved wounds is approximately:



```text

57.7%

```



A ten-Marine squad therefore has slightly better than even odds of killing one full-health Terminator.



## Summary



| Attacker     | Attacks | Expected damage | Chance of killing one Terminator |

| ------------ | ------: | --------------: | -------------------------------: |

| One Marine   |       4 |            0.30 |                            0.15% |

| Five Marines |      20 |            1.48 |                            18.1% |

| Ten Marines  |      40 |            2.96 |                            57.7% |



## Why Terminators are so resilient



The chainsword performs poorly against a Terminator because it must overcome three separate probability barriers:



\* The Marine hits 66.7% of the time.

\* The chainsword wounds only 33.3% of the time.

\* The Terminator fails its modified save only 33.3% of the time.



Even though each individual probability may not appear extremely low, multiplying them together reduces the chance of dealing damage to only 7.41% per attack.



This is why weapons with higher Strength, better Armour Penetration, and greater Damage are far more effective against elite infantry.



## Conclusion



An Astartes chainsword is effective against lightly armoured infantry, but a Terminator is a difficult target.



A single Space Marine causes only about 0.3 expected damage and has almost no realistic chance of killing a full-health Terminator. Even five Marines have less than a one-in-five chance of securing the kill.



It takes approximately ten ordinary chainsword-wielding Marines to achieve slightly better than even odds of bringing down one Terminator in a single Fight phase.



The example demonstrates an important probability lesson: in Warhammer 40,000, every additional roll in the attack sequence reduces the likelihood of damage. Strong armour and high Toughness do not merely make a target slightly harder to kill—their effects multiply.


