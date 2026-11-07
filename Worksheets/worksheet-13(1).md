# COMP2000 Worksheet 2 — Final Submission

**Student name: Kiel Mendoza De Jesus**

**GitHub repo URL: https://github.com/KielDeJesus/Comp2000-Half-Half**
---

## 1. Design Patterns

Don't forget to submit a pdf file which shows a diagram of your pattern implemenation to supplement this text description.

**1.1.** Which design pattern(s) did you implement? Name them and state where each appears in your codebase.

I implemented a Strategy Pattern, this can be found through EventLogic, EventStrategyManager and the x (e.g house, apartment, etc)Strategy.java files in our repository.



**1.2.** For each pattern, paste a code snippet showing the key interaction between participants.





**1.3.** For each pattern, explain why you chose it over an alternative. What trade-off did you make?

I chose the strategy pattern for our building system as I observed that our method for actually creating buildings on the grid was actually a shared method between all buildings, enabling this behaviour interchangably allows us to add more buildings more easily in the future.

The only trade off with this implementation was the exclusion of our originally planned disasters functionality and our mall and apartment merging functions, these were originally going to spawn when either 4 houses reach a threshold or if there were 4 shops in a given area.




---

## 2. Streams / Lambdas / Parallelism

**2.1.** List every file in your project that uses lambda expressions or the Streams API.

School.java



**2.2.** For the most sophisticated use, paste the code and explain: what does it do, and why was a stream/lambda better than a loop?





**2.3.** Did you use parallel streams, custom collectors, or the Fork/Join framework? If yes, how did you ensure thread safety? If no, where could parallelism be introduced?

No we didnt, we could've 



---

## 3. Uniqueness and Creativity

**3.1.** What did you add to your simulation that went beyond the in-class activities? Describe the feature and what inspired it.





**3.2.** Paste a code snippet or describe a design decision that demonstrates emergent behaviour, non-trivial complexity, or a genuinely surprising outcome.

eventManager.SetStrategy(events[(int)(Math.random() * events.length)]);



**3.3.** If you had another 6 weeks, what would you add or change?

I would definetly want to see more communication in my team. 

But in regards to the codebase, I would've liked to implement actual events that affect our population (positively and negatively) to our simulation, affecting the grid when necessary and utilizing strategy patterns to interchange between these.



---

## 4. Log Book and Final Reflection

**4.1.** Attach or link your log book entries for Weeks 7–13.





**4.2.** Reflect on the semester:

- What was the most important concept you learned?

- What design trade-off did you face, and how did you resolve it?

- If you started over, what would you do differently?

- What feedback from the Week 7 submission did you act on?
