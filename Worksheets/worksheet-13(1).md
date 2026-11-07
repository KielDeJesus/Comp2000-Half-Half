# COMP2000 Worksheet 2 — Final Submission

**Student name: Kiel Mendoza De Jesus**

**GitHub repo URL: https://github.com/KielDeJesus/Comp2000-Half-Half**
---

## 1. Design Patterns

Don't forget to submit a pdf file which shows a diagram of your pattern implementation to supplement this text description.

**1.1.** Which design pattern(s) did you implement? Name them and state where each appears in your codebase.

I implemented a Strategy Pattern, this can be found through BuildLogic, BuildStrategyManager and the x (e.g house, apartment, etc)Strategy.java files in our repository.



**1.2.** For each pattern, paste a code snippet showing the key interaction between participants.

in Main.java:
        
        BuildStrategyManager buildManager = new BuildStrategyManager();
        BuildLogic[] builds = {new houseStrategy(), new OfficeStrategy(), new SchoolStrategy(), new ShopStrategy(), new ApartmentStrategy(), new MallStrategy()};
       //creating main loop

       


        buildManager.SetStrategy(builds[0]);

        while (w.isDisplayable()){
        buildManager.executeStrategy(w);
            Thread.sleep(500);
            buildManager.SetStrategy(builds[(int)(Math.random() * builds.length)]);
            w.repaint();
       }

This is linked with the BuildStrategyManager class and BuildLogic interface to allow buildings to be placed on the grid interchangeably, this is seen through the line 'buildManager.SetStrategy(builds[(int)(Math.random() * builds.length)]);' which randomly selects a strategy from the events array and executes it.



**1.3.** For each pattern, explain why you chose it over an alternative. What trade-off did you make?

I chose the strategy pattern for our building system as I observed that our method for actually creating buildings on the grid was actually a shared method between all buildings, enabling this behavior interchangeably allows us to add more buildings more easily in the future.

The only trade off with this implementation was the exclusion of our originally planned events functionality and our mall and apartment merging functions, these were originally going to spawn when either 4 houses reach a threshold or if there were 4 shops in a given area. Events would see the modification of our population via a random choice of an element in an array, this would've been implemented via a strategy pattern (similar to how we setup the buildManager) and would cause decreases or increases in population.




---

## 2. Streams / Lambdas / Parallelism

**2.1.** List every file in your project that uses lambda expressions or the Streams API.

School.java



**2.2.** For the most sophisticated use, paste the code and explain: what does it do, and why was a stream/lambda better than a loop?

    public static School create(int x, int y, int students, int teachers) {
        return new Builder()
                .name("School #" + x + "-" + y)
                .students(students)
                .teachers(teachers)
                .at(x, y)
                .build();
    }

This stream helps return schools with a population greater than 500 in reverse alphabetical order. A stream was implemented here to refactor the program cleanly.



**2.3.** Did you use parallel streams, custom collectors, or the Fork/Join framework? If yes, how did you ensure thread safety? If no, where could parallelism be introduced?

No we didnt. We could've implemented parallelism through our population generation and calculation methods, joining the two would've reduced our program's length and would've increased efficiency.



---

## 3. Uniqueness and Creativity

**3.1.** What did you add to your simulation that went beyond the in-class activities? Describe the feature and what inspired it.

I added a randomness to our spawning mechanic by having our buildings spawn randomly through a strategy pattern. 



**3.2.** Paste a code snippet or describe a design decision that demonstrates emergent behavior, non-trivial complexity, or a genuinely surprising outcome.


        while (w.isDisplayable()){
        buildManager.executeStrategy(w);
            Thread.sleep(500);
            buildManager.SetStrategy(builds[(int)(Math.random() * builds.length)]);
            w.repaint();
       }

Although this works correctly, this displayed weird values for population, outputting 4 twice and then eventually doubling this value and doing the same thing. Previously this would output a population value that incremented overtime.




**3.3.** If you had another 6 weeks, what would you add or change?

I would definitely would've want to see more communication in my team, with each making clear what they changed in the program and how to modify/work with it in the future. 

But in regards to the codebase, I would've liked to implement actual events that affect our population (positively and negatively) to our simulation, affecting the grid when necessary and utilizing strategy patterns to interchange between these.



---

## 4. Log Book and Final Reflection

**4.1.** Attach or link your log book entries for Weeks 7–13.

[https://github.com/KielDeJesus/Comp2000-Half-Half/blob/edaa50480dc2a498c98dd07823c26a7371fcd1d7/LogBooks/Weeks%207-13.pdf](url)



**4.2.** Reflect on the semester:

- What was the most important concept you learned?

  Design patterns as they helped enable expand the scale of our program a bit.

- What design trade-off did you face, and how did you resolve it?

As mentioned earlier, there were some things in our scope that we weren't able to include within the time frame of the project. From here we opted to simplify our program and remove additions that we knew we couldn't implement in time (as seen with the disasters/events system), we would then brainstorm further and choose what we could modify/create with our existing codebase and work from there.

- If you started over, what would you do differently?

  I would try and encourage teammates to check in more often to avoid confusion, especially relating to the codebase.

- What feedback from the Week 7 submission did you act on?

We were told to implement any form of design patterns inside our program after Week 7, we would begin brainstorming ways to do so and eventually decided on a state pattern for weather, observer for population and strategy for buildings.
