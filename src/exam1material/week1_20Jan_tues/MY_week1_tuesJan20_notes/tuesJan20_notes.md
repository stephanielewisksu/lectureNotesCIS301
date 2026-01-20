## CIS 301. 
### Logical Foundations of Programming. 
\eng building 1109\ Julie Thornton.

### What is this class?
- logical reasoning (basics, puzzles)
- writing **formal statements** (propositional and predicate logic)
- **proofs** (why? - certainty in logic)
- reasoning about code
    - analyzing what we know
    - identifying equivalent programs
    - simplifying programs
    - formally describing what programs do
- basics of **proving correctness** of programs (why? - ssecurity of software, untestable scenarios like medical)

### Syllabus
- grading leeway: drops + final can help with a midterm if better grade
- extra credit: find errors, help people
- important academic honesty note: cooperation allowed
- AI not allowed! YAY
- Ok also important, syntax matters because we're using a particular tool

### Canvas setup 
- weekly class material
- in-class quizzes aren't that important but check understanding / show attendance
- Ed-Discussion: intro assignment plus extra credit, good to ask Qs

### How to take notes
- forked repository (type into MY folder so merges don't conflict)

---

### HW 0 
- due Thursday, January 22
- ed-discussion plus tech check
- will be using an extension + repository clone for tech check
- submit link to commit like CIS200

### HW 1 
- due Tuesday, January 27

---

Taking a step back...what is logic?
- analysis of an argument according to a set of rules
- given a set of premises (and sometimes a conclusion
     - a VALID conclusion is one that is always true anytime all the premises are true
     - validity =/= truth, premises can be wrong and the logic is still **valid**

---

**Premise 1:** If a person wears a red shirt,
    then they don't like pizza.
**Premise 2:** Fred is wearing a red shirt.
**Conclusion:** Fred doesn't like pizza.


Is this a valid argument? 
- YES, because the logic follows our premises.

(is there a hidden assumption we're making about Fred?)
- Premise 1

---

## Logical Arguments with "OR"
- exclusive: a XOR b, only one can be true 
- inclusive: a OR b, either can be true

I order fries or I order chips.
- in casual English, this reads as an XOR
- in programming, OR is inclusive
- assume programming for the sake of class

---

**Premise 1:** I'll fold the laundry or I'll do the dishes.
**Premise 2:** I don't fold the laundry.
**Thus:** I do the dishes. 
(assuming premises are true, ala validity check)

---

num = 5;
if (num < 4 || x >= 10) {
    statement;
}

when is "statement" executed
- if x is greater/equal to 10.
  
---

x = 9;
if (num < 4 || x >= 10) {
    if (num > 2) {
        statement;
    }
}

"statement" is executed
- if num is less than 4 and greater than 2

---

What rule are we seeing with an "or" statement, where we know that one of the statements is NOT true?
- other must be true

---

Logical Arguments with "IF/THEN" (aka "implies" -> )

If it is raining, then I will get wet.
It is raining.
**Thus** I am wet.

### Contrapositive statement
if p then q == if !p then !q

---

When we have an "if/then" statement, and we know that the "if" part is true?
The "then" must also be true.

---

If I don't hear my alarm, then I will be late for class.
I am late for class.
(Unclear whether "if" is true.) 

---

If I don't hear my alarm, then I will be late for class.
I hear my alarm.
(Unclear what follows, there's no reason to assume the "then" condition can't be true in other situations.)

---

If I don't hear my alarm, then I will be late for class.
I'm not late for class.
(If cannot be true, since then would have to follow and our outcome contradicts this.) 

---

More if/then logic in programming.


if (num < 4 || x >= 10) {
    y = 17;
}

### Suppose y is 17 here. What do we know?
Unclear from given information. If *could* be true, but is not certainly true.

---

y = 10;
if (num < 4 || x >= 10) {
    y = 17;
}

### Suppose y is 17 here. Can we conclude anything now?
The if statement must be true, and thus at least one of num < 4 or x >= 10 is true. 
Importantly: programs run line-by-line, there's no real way for this to run and for y to become 17 by some other method.

---

if (num < 4 || x >= 10) {
    y = 17;
}

### Suppose y is NOT 17 here. What do we know?
Contrapositive: the if statement cannot be true.

Note: negation of an OR statement (a OR b) can be (!a AND !b), by name DeMorgan's Law

---

### Logic puzzles.

The puzzles in this lecture are from or inspired by: "What is the Name of This Book?", by Raymond Smullyan

**The island of Knights and Knaves.**
(seems like a specifc version of the liar's paradox)
Each inhabitant is either a knight or a knave.
Knights ALWAYS tell the truth, and knaves ALWAYS lie.
Who can say, "I'm a knave"?
Can a knight? 
- NO, knights cannot lie
Can a knave?
- NO, cannot tell the truth

You see two inhabitants on this island, Eve and Fred.
Eve says, "I am a knave or Fred is a knight."
- "I am a knave" cannot be true, thus Eve is NOT a knave
- Fred is a knight MUST be true

**What are Eve and Fred?**
- Eve is a knight, Fred is a knight.

(*what does the "or" mean?* as long as one part of the statement is true, the full statement is true)

You see two more inhabitants, Ava and Bob.
Ava says that Bob is a knave.
Bob says, "Neither Ava nor I are knaves."
**Rewrite Bob:** !(Ava knave) AND !(Bob knave), or both knights 

**What are Ava and Bob?** 
If what Bob says is true, Ava is false (which contradicts her being a knight).
If Ava is a knight, both statements are true.

What does "neither" mean?

---

**Homework 0:** due Thursday, January 22
    - get Sireum + GitHub ready (do this now!)
    - post something in Ed Discussion
    - come to office hours or post in Ed Discussion if
        you need software setup help!

**Homework 1:** due Tuesday, January 27
    - first page of homework is logical reasoning
        (what we did today)
    - second page is logic puzzles
