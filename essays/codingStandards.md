---
layout: essay
type: essay
title: "Are coding standards helpful?"
# All dates must be YYYY-MM-DD format!
date: 2022-09-22
published: true
labels:
  - Reflection
  - Coding Standards
  - Learning
---

<img class="img-fluid" src="../img/codingStandards1.png" alt="1">

## Can Coding Standards Help to Learn a Programming Language?
There is a wealth of literature that emphasizes the advantages of having consistent coding styles and standards. The majority of readers will undoubtedly agree with the following:

Inexperienced developers and cowboys who don't know any better will frequently oppose the requirement to adhere to standards.  They argue that if they do it their way, they can code quicker.  It's all nonsense.  They MAY be able to get code out the door faster, but I have my doubts.  Cowboy programmers are stuck during testing when multiple difficult-to-find issues appear, and when their code has to be improved, they frequently rewrite it since they are the only ones who understand it.  Is this how you want to go about things?  I most certainly do not.

Coding standards can definitely help us learn a programming language better. This is a way to improve the quality of our coding. In some cases, we have to share our work with others. Coding standards facilitate collaboration. If everyone writes code in their own way, we start thinking everyone is wrong. The quality and efficiency of coding can be effectively improved by a standard accepted by the public.

## Experience with Coding Standards
<img class="img-fluid" src="../img/codingStandards2.jpeg" alt="2">

After my first week of using ESLint and IntelliJ, I found that coding standards really helped me learn to code. It helps me modify the use of
`var`
and
`let`
 and it helps me check for spelling errors. This is a "magic tool" for non-native English speakers. One of the most common mistakes I make in coding is spelling mistakes, so I can't find the reason why my code does not work properly. And coding standards can also be effective in correcting our code.
For example：

```cpp
const zipListTheSimpleWay = (letter, num) => {
return _.flatten(_.zip(letter, num));
}

const zipListTheSimpleWay = (letter, num) => _.flatten(_.zip(letter, num));
```


This is a mistake I often make in coding. Coding standards enable me to learn a programming language more clearly and effectively improve the efficiency of programming.
