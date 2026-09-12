# COMP2000 Worksheet 1 — Mid-Semester Submission


**Kiel Mendoza De Jesus**


**Student ID: 49046020**


**GitHub repo URL: https://github.com/KielDeJesus/Comp2000-Half-Half**


---


## 1. Version Control


**1.1.** Paste the first 10 lines of the output of `git log --graph --oneline --all` from your repository:


```
* 776351d (HEAD -> main, origin/main, origin/HEAD) Removes obsolete
*   5678941 Merge branch 'main' of https://github.com/DarkOmen-455/Comp2000-Half-Half
|\  
| * e45b9d1 Fixed merged errors
| *   9268ca5 Merge branch 'main' of https://github.com/DarkOmen-455/Comp2000-Half-Half
| |\  
| * | 0827b2c - Fixed totalpeople had typo [z] [z]
* | | 64807e2 added functionality to disaster test builds
| |/  
|/|   




```


**1.2.** Describe your workflow. Did you use branches? Pull requests?


During this project, we primarily utilised push and pull requests, we did not use any branches. If we did, we only utilised the main branch and kept pushing to it.






**1.3.** Estimate the percentage of commits you contributed relative to the total in your repository.


I estimate that I was able to create at least 10-20 percent of commits during this project.








---


## 2. Program Design


**2.1.** List every class in your project and write 1–2 sentences describing its responsibility.


We have a total of 10 classes


They are:
- Building: this is the super-class of our project, it is responsible for housing all the internal logic that a building may need, these include population, variables     for position and a build function that enables the placing of these buildings on our grid.
- House: this is responsible for generating the population for our simulation. These are spawned in random positions over the course of the simulation to produce     people.
- Apartment: These are responsible for reducing the amount of houses that are on the grid. These are spawned when houses reach a certain population threshold, these     houses are then merged into one apartment.
- Office: These are responsible for generating income and spawn when the population reaches a certain threshold (60-70 people overall). 
- School: These are responsible for teaching any children that our house class produces, these will also produce workers for future offices that spawn.
- University: Responsible for educating adults that will work in offices later.
- Shop: These are responsible for producing more workers and generating income in the simulation.
- Mall: These are created when there are 4 shops on the grid, they are all merged together into one mall.
- Disaster: responsible for creating the disaster logic for the simulation. Implemented to add random chaos to the simulation and cause variations in population.
- EventManager: creates an array of events to load and execute during the simulation, this mainly relates to the disasters.










**2.2.** Identify any inheritance relationships. For each parent–child pair, list what the child inherits and what it overrides.


Most of the classes in our program are related to the Building super class, with Building being the parent and House, Apartment, Office, Shop, Mall, School and University being children of Building. The children of Building override the getPopulation() and build() methods of Building to modify the position of a building on the grid and to get the overall population that the building type has generated over time.










**2.3.** Pick the class that you think has the best design. Explain why.


I really liked the Building super class as it encompasses all the necessary logic needed to create all the other buildings we see on the grid of the simulation.








**2.4.** Paste one code snippet that demonstrates your use of polymorphism or encapsulation.  Include an explanation of _how_ this demonstrates polymorphism or encapsulation.  Give a reference to a provided reading that talks about this type of polymorphism or encapsulation.


    @Override
    public int getPopulation(){
        return workers;
    }

As seen _Learning Java 3rd Edition_, this is called **subtype polymorphism** as we are overriding methods to change the behaviour of objects. In this case, we are overriding the getPopulation method in Office as overtime it'll have a different population count from other buildings. This is why the override is there, to ensure that the correct population is returned and not the default one found in our building class.








---


## 3. Generics and Exceptions


**3.1.** List every place your code uses generics (e.g. `ArrayList<Actor>`, `Optional<Cell>`, `HashMap<String, Team>`). If you deliberately used none, explain why.


We mainly used ArrayLists as our primary form of generics in our simulation. This is mainly seen in Window.java’s incPopulation() method, which utilises an ArrayList of houses to increment the population.








**3.2.** List every place your code handles exceptions (try/catch, throws, custom exception classes). What error is each protecting against?


We utilise a throws keyword in Main:


```
    public static void main(String[] args) throws InterruptedException {
        System.out.println("Initializing program");
        Window w = new Window(800, 600);
        StatsWindow sw = new StatsWindow(300, 300);


```
As seen here, we use it to throw an InterruptedException, this is so we can utilize Thread.sleep in our program. 


Window.java also uses one in its incPopulation() method, this is primarily found in its for loop.






**3.3.** Paste a code snippet showing either a generic class/method or a try/catch block.


    for (int i = 0; i<step;i++){
            try{
                int index = (int)(Math.random() * total.size()-1) + 1;
                if (total.get(i).getAdults()<= 6){
                    total.get(index).setAdults(total.get(index).getAdults()+1);
                }
                else{
                    total.get(index).setAdults(total.get(index).getAdults()-1);
                }  
            }catch (IndexOutOfBoundsException e){
                System.out.println("ArrayList out of bounds at:"+i);
            }
        }
         
    }








---


## 4. Log Book


**4.1.** Attach or link your log book entries for Weeks 1–6.

[
https://github.com/KielDeJesus/Comp2000-Half-Half/tree/main/LogBooks](url)







**4.2.** Which week's activity taught you the most? What did you learn?


Week 4’s inheritance activity taught me the most as I was able to learn how we can implement inheritance in our own classes and ensure that the classes we create can derive from a superclass and borrow methods and variables from it to modify it.
---


## 5. Uniqueness and Creativity


**5.1.** List everything you added to the project that was not part of the in-class activities.


I added a main for loop responsible for handling the spawning of random houses over time. 


**5.2.** Which feature required the most independent research or problem-solving? What did you learn from it?


Drawing the grid took us a bit of time to figure out as we were all new to the JFrame/AWT library.


**5.3.** Paste one code snippet that you are especially proud of. Explain why it goes beyond what was done in class.


I’m really proud of the random spawning of classes over time. This took a bit of problem solving to get around as we weren’t necessarily taught how to create a grid or spawn items on said grid.



