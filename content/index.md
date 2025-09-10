Title: Mathematical Modeling for Computational Science
Date: 2024-08-19
save_as: index.html


Mathematical modeling is the very heart of applied mathematics. Presented with a new problem, we need to figure out how to formulate it in mathematical terms; how to decide if the formulation is correct; and how to use the formulation to do something useful. Applied Mathematics has been described as a “no holds barred” competition to solve problems and get to the truth.  Recent events from the rise of chatbots to the management of the Covid pandemic have mathematical modeling at their core: In the case of chatbots, we finally have arrived at a model of language that is sufficiently robust that we can reliably generate it – this is fundamentally an advance of modeling, though its instantiation was enabled by incredible technology; in the case of covid, mathematical models presaged the intensity of the pandemic and helped to manage it – yet in many ways they also failed in making accurate enough predictions to be useful.

Mathematical modeling is hard. It requires that we creatively invent equations, and that the equations can be solvable and useful. Doing it well is an art form.  **Evaluating models** – testing  how well they work – is extremely important.

Arguably the major advances that have occurred in mathematical modeling <a href="https://arxiv.org/abs/2310.00865" target="_blank">over the last decade</a> are advances in systematic evaluation and iterative improvement of models.

The goal of this class is to make you into a mathematical modeler, using everything that you have learned to create models of things that are of interest to you. The mathematics that can be applied is vast, and so as part of becoming a modeler, you need to learn to be comfortable quickly assessing mathematics that you do not yet know – and then figuring out what you need for the problem at hand.  At the same time, sophisticated modeling in 2024 requires software engineering -- at a level that is beyond the AM undergraduate curriculum. To address this, we are now introducing a **hybrid undergraduate and graduate class** (Applied Math 115/215) where the undergrad component will focus on the essentials of mathematical modeling, and the graduate class will also build upon this to learn how to implement these models using modern software engineering skills (which we will teach in additional lecture each week to the graduate students).  Our hope is that this hybrid class will end up as a community where people with different skills can work together and make amazing models of interesting things.

To get us to this point, the class will survey examples of areas where mathematical models are important:  we will simultaneously focus on __interesting questions__ (what is the probability that the best team wins the world series? Should a fast food restaurant offer a discount to their customers? How many people can the earth support?), while at the same time learning mathematical ideas that are generally useful.  Fundamentally, this course approaches a number of problems __without the prejudice__ of trying to apply a particular method of solution. 

The examples we will study, along with associated questions we might address,include:

*   **Sports Analytics**: When do we expect a person to break the 2 hour mark in a marathon? What is the optimal pace to take at different parts of a race? Given the draw of a tournament (tennis, march madness, etc), and everything you know about the teams and players, please predict who will win.  Assign probabilities. Evaluate potential solutions in a mathematically same way.
* **Random Walks, Diffusion and Markov processes**: Models of stock and option pricing. Random walks on graphs: Page rank and web search. Diffusion in the atmosphere: Pollution forecasting, and attributing carbon emission.
* **Predicting elections**: Can we predict in advance the outcome of an election given the properties of the voters? Can we devise advertising strategies to affect the outcome?
* **Queuing problems**:  Design the algorithm for elevators in a large building with many people. Design the algorithms for traffic lights.  Design Amazon’s logistics chains. Should a fast food restaurant offer discounts to attract customers? 
* **Create a Hedge Fund**: Given the data for stock or other asset prices over time, create a mathematical model that powers a notional hedge fund. Evaluate this model against performance of similar funds in the past and assess how well are you doing.d
* **Simple models of climate**: Why is the climate of the earth what it is? Can we estimate in simple terms when and if and how it will change?  What do actual climate models do?
* **Prediction Markets**: Choose a question in a prediction market (e.g. <a href="https://www.predictit.org/" target="_blank">https://www.predictit.org/ </a>). Formulate a mathematical model to answer the question. Enter. Assess in advance how well you think you will do.

<a href="https://canvas.harvard.edu/courses/140625">The class syllabus can be found by following this link.</a>


## <a id="staff"></a><a class="anchor-link" href="#staff">Teaching Staff</a>

### <a id="instructor"></a><a class="anchor-link" href="#instructor">Instructors</a>

Michael  Brenner (<brenner@seas.harvard.edu>)
<!-- TODO: Fill  -->
* Office: 
* Office Hours: 


Ignacio Becker Troncoso (<iebecker@g.harvard.edu>)

* Office: SEC 1.312-05
* Office Hours: 

### <a id="tf"></a><a class="anchor-link" href="#tf">Teaching Fellows</a>
| Fellow                      | Email                                  |
|:----------------------------|:---------------------------------------|
|     Sarah Martinson         |        <sarahmartinson@g.harvard.edu>  |
|     Katya Ivshina           |         <eivshina@g.harvard.edu>       |
|     Livia Guttieres         |         <liviaguttieres@g.harvard.edu> |
|     Elle Weeks              |         <elleweeks@g.harvard.edu>      |



### <a id="tf"></a><a class="anchor-link" href="#tf">Course Calendar</a>
<center>
    <p>
        <iframe style="border: solid 1px #777;" src="https://calendar.google.com/calendar/embed?src=2932bf453e7fbe0f80ced8556492e9279da2369cf452f334c8af0e3cd2b98d0f%40group.calendar.google.com&ctz=America%2FNew_York" width="800" height="600">
        </iframe>
    </p>
</center>


<!-- SEC is the Science and Engineering Complex in Allston and MD is the Maxwell-Dworkin building in Cambridge. -->
<!-- TODO: Instructions to register lab times -->
<!-- > * **Labs:** <a href="https://docs.google.com/spreadsheets/d/1w9WryKCfZ--RGjEujGyqUGi36t-x5X79A_v0mTyAI64/edit?usp=sharing" target="_blank">Lab times signup sheet.</a> -->

## <a id="hours"></a><a class="anchor-link" href="#hours">Lecture Hours</a>

All lectures are of 75 minutes duration. Time is given in Eastern Standard Time (Boston). Friday lecture is aimed to AM215 students. Everyone is free to attend. 
> Lecture attendance is **expected**:
>
> |              | Time           | Room      |
> |--------------|----------------|-----------|
> | **Tuesday**  | 10:30 AM - 11:45 AM | Emerson 210 |
> | **Thursday** | 10:30 AM - 11:45 AM | Emerson 210 |
> | **Friday** | 10:30 AM - 11:45 PM | Science Center Hall E |


## <a id="important"></a><a class="anchor-link" href="#important">Important Information</a>

* **[Canvas](https://canvas.harvard.edu/courses/140625):** Is used for posting grades and other class sensitive content.
* **[Gradescope](https://www.gradescope.com/courses/821711):** Is used for homework and lab submissions.
* **[Class Git repository](https://code.harvard.edu/AM215/main_2024):** The handouts and other material are provided through the `main` repository hosted in the AM215 organization. You can clone this repository once you have joined the AM215 organization.

```
git clone git@code.harvard.edu:AM215/main_2024.git
```

Membership to the AM215 organization be updated daily once the semester starts. If for some reason you are not given access, please wait until the afternoon. If you cannot access the organization, please fill [this form](https://docs.google.com/forms/d/1TxncfkQD0EFG32qalEpsRYWcnoONKOfw6ThyAtsfmy0/edit). You  must use our `*.harvard.edu` email and include your [NetID](https://harvard.service-now.com/ithelp?id=kb_article&sys_id=507aca5a1b653700efd8a79b2d4bcb59), which is also your <https://code.harvard.edu> username (something similar to `abc123`).

### <a id="class-forum"></a><a class="anchor-link" href="#class-forum">Class Discussion</a>

We will use the [Ed Discussion forum](https://edstem.org/us/courses/61992/discussion/) on our Canvas page as our main communication platform. Questions regarding homework, sections or lecture material must be posted on this forum and you are encouraged to reply to questions if you know the answer or you can share a useful contribution.
