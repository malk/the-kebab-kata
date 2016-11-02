# The Kebab Kata’s Facilitator’s guide 

## A Game to identify & fight the team’s systemic issues creating your legacy
Because we tend to believe this is only on the devs shoulders but everyone has a part creating that legacy!
Your interactions with your teammates and managers are as much of a burden to your code as you are.

### By [Romeu Moura](https://twitter.com/malk_zameth)
I have created this kata for [NewCrafts](https://twitter.com/ncraftsconf), done it at [DDDEurope](https://twitter.com/ddd_eu/status/781054838109069313) & [SoCraTes](https://twitter.com/socrates_fr).
The concept of using these patterns to do a Kebab I have taken from Matthias Felleisen & Dan Friedman.

### Pitching it as a facilitator

> Try to create a code you will not consider “legacy”.
>
> I’ll play the role of your client and use around 20 techniques to make you fail.
>
> You will fail.
>
> We’ll then discuss what techniques I have used, how they happen in real life, how to fight them in your project.
>
> All languages welcome. Bring your own laptop with your environment. We’ll split into small teams.

### From 4 to ∞ Participants
* A Facilitator (you, *right?* if not *stop reading* now and pass this to the facilitator)
 * You are also the time-keeper and the “client”
* At least 2 pairs of devs (Each group needs at least 2 devs and you need at least two groups)

### It takes about 2 hours
* around 75 minutes for the body of the kata, then a debrief
* you can do a quicker 90 minutes version in a hurry
* the debrief can get quite long tho, I have seen groups needing to talk afterwards for hours

## Playing the game
* 4 iterations where they code with a budget of time you give
 * they can negotiate for more, be open to *negotiate* but never open to *accept* giving more
 * You should always behave like it is too much and ask if they cannot do it in less
  * yes even though *you* decided on an arbitrary budget of time
* At the end of each iteration each team has 45 seconds to do a “client demo”
 * During the client demos other teams can cheat and keep developing
 * the team does not show code during the client demo; just tests (automatic or manual) of the code working
 * the team can sell vapourware at the client demo
* after the client demos we do code reviews
 * half of the teams review half of the others then reverse
 * each review goes for 1.5 to 2 minutes
 * encourage teams to be honest with the reviewers
  * and ask reviewers to try to give positive suggestions on improvements
* after four iterations (each with its own code round, demo and code reviews): do a final debrief

### tips:
* choose whether or not you will tell them how many iterations there are
 * but do not give the contents and time budget of any iterations before it starts.
* You may choose to announce one of the 4 iterations as being five minutes longer that indicated. Then, *during* the iteration, announce a budget cut and use the total indicated time.

### Iteration 1: “Kebabs & vegeterianism” (10 minutes)
#### Tell the devs:
* you are the owner of a kebab shop
* you need kebab object that you can create with any ingredient you want (salad, tomatoes, onions, meat, etc)
* you already have an user interface you only want the object
* it should have one method `isVegeterian`
 * Takes no argument, returns a boolean
 * true if all ingredients on the kebab are vegeterian (vegetables + cheese + eggs)
* you will be generous and give them ample amount of time to do such a *simple* task : 10 minutes.

##### Tips:
* Be vague!
 * do not give them your list of ingredients outright
  * behave like it should be obvious
* *be inconsistent* ! 
 * when they ask specifically for the ingredients list, keep forgetting and remembering ingredients
* Devalue their work
 * Treat the task like being trivial and 10 minutes like being more than double the time they need to do this
* Interrupt them to ask for opinions and lower estimates
 * anyone that accepts to do it in less has a reminder at the end of their estimate that they shoud be finished
* Insist that you think they should not invest too much of their time into quality and tests

### Iteration 2: “Just finish your work & clean!” (7 minutes)
#### Tell the devs:
* You understand that maybe they have not completely finished & need some extra budget
* They also need some time to refactor, test & clean
* You'll be generous and give them some time to do that now
* ALSO, by the way, you want `Kebab` to *just* have another method `isPesceterian`
 * Everything that `isVegeterian` is also `isPesceterian` *plus* fishs & shrimps
  * yes, it is the first time you talk about shrimps
   * deny it being the first time
   * tell them that you also want to submit a bug report regarding that they're not handling shrimp up until now
* insist that this is just a “cleaning sprint” you are giving as a gift, the `isPesceterian` demand being, obviously, just a tiny detail

##### Tips:
* keep the vagueness, inconsistencies and demands for estimations
* insist that *best is the enemy of good enough*
* go around team per team asking each team if they would not produce more if they split the team into several teams of one person each working together by splitting tasks

### Iteration 3: “A single urgent user story for this sprint!” (15 minutes)
#### Tell the devs:
* You want to submit a bug report: they do not handle sauces
 * tell them it's obvious you have sauces, of course you do !
* but anyway this is not the main issue with the sprint: you have a really urgent user story!
* insist that they should answer *your* problem, *not* a general version of it
* You want `Kebab` to do the two most common demands fo your clients: `removeOnions` & `doubleCheese`
* both return a `Kebab`, it can be a new one or the same changed, but the caller will just use the kebab returned
* `removeOnions` returns a kebab like this one, without any onions
 * `bread + cheese + onion + onion + cheese + onion` returns `bread + cheese + cheese`
* `doubleCheese` returns a kebab like this one, with the cheeses doubled in place
 * `bread + cheese + onion + cheese + onion` returns `bread + cheese + cheese + onion + cheese + cheese + onion`

##### Tips:
* keep the vagueness, inconsistencies and demands for estimations
* insist your two demands are a single one
* refuse to prioritize between them
* go around team asking them if they cannot finish it earlier, like 10 minutes in total

### intermission: “a new you”
#### Tell the devs:
* Thank you for your good work!
* Please high-five everyone in your team!
* you are all *fired*!
* you are a new version of yourselves, unrelated to the previous ones
* I hire you to inherit the codebase of your previous selves
* the *last* team *REALLY* did an awful job! They where awful!
* But your new you is really good, I can see that!
* please do a one minute audit of the code
 * no editing the code during the audit
 * each team should give a report of what they would want to change in that legacy codebase they just audited

### Iteration 4: “Cleaning that legacy codebase!” (20 minutes)
#### Tell the devs:
* If the code does not work, first make it work
* If the code does not have tests you should add them
* Then you can refactor as you see fit
* I have hired an *Architect* to help you with an idea of how to do that refactoring

#### Changing voice tone, Tell the devs:
* You are *The Architect*
* You will try to speak with them in terms *they* can understand
* You propose that they create a `Dish` `Kebab` that is  a **NullObject** pattern
* Then each one of the other types of `Kebab` should follow a **Composite** pattern
 * They will take another, inner, `Kebab` in their constructor & delegate to it
  * a `Beef` `Kebab` is not Vegeterian: its `isVegeterian` returns `false`
  * a `Salad` `Kebab` is Vegeterian: its `isVegeterian` calls the `isVegeterian` of its inner `Kebab`
* Defer any criticism of the idea by appealing to your own authority

### **The Debrief**
#### Tell the devs:
* have they created in their own personal definition a Legacy codebase?
* What is their definition?
* You have used at least 10 techniques to push them into creating shitty code (Note: those where my Tips)
* you offer them one for free : You instilled an artificial and arbitrary sense of urgency
 * with your deadlines
 * and you pression for them to finish before those arbitrary deadlines
* What else have you done? 
 * Make them list it
* Do they see this in their everyday lives?
* How can we fight each one of those?
 * This becomes a debate
