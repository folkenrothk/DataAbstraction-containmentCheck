# Containment Checking

### Kate Folkenroth

## Program Output

### Report at least five examples of program output to demonstrate that your `containmentcheck` program works correctly

Below are examples of the output from running the `containmentcheck` program. In each section, the output is labeled with the relevant research question (the parameter choices are described thoroughly in the [Experiment Design](#Experiment-Design) section below), the number of run (refer to the [data tables](#Data-Tables) below each respective question), the command inputted to the terminal, and the subsequent output.

#### 1. Output from running the `containmentcheck` program

RQ 1. *Run 1*

`poetry run containmentcheck --approach list --size 50000000 --maximum 5000000 --exceed`

```
✨ Conducting an experiment to measure the performance of containment checking!
         Type of the data container: list
         Size of the data container: 50000000
         Maximum value for a number in the data container: 5000000
         Should the value to search for exceed the maximum number? Yes
         The random number generated is: 5000001

⏱  Total time for running 10 runs in 3 benchmark campaigns: [7.323755500000004, 7.328123400000003, 7.340552000000002]

🧮 Average time for running  10 runs in 3 benchmark campaigns: [0.7323755500000004, 0.7328123400000003, 0.7340552000000002]        
```

#### 2. Output from running the `containmentcheck` program

RQ 1. *Run 4*

`poetry run containmentcheck --approach tuple --size 50000000 --maximum 50000000 --exceed`

```
✨ Conducting an experiment to measure the performance of containment checking!
         Type of the data container: tuple
         Size of the data container: 50000000
         Maximum value for a number in the data container: 5000000
         Should the value to search for exceed the maximum number? Yes
         The random number generated is: 5000001

⏱  Total time for running 10 runs in 3 benchmark campaigns: [7.130835699999999, 7.104918300000001, 7.079995099999998]

🧮 Average time for running  10 runs in 3 benchmark campaigns: [0.7130835699999999, 0.7104918300000002, 0.7079995099999998]
```

#### 3. Output from running the `containmentcheck` program

RQ 2. *Run 2*

`poetry run containmentcheck --approach list --size 100000000 --maximum 50000000`

```
✨ Conducting an experiment to measure the performance of containment checking!
         Type of the data container: list
         Size of the data container: 100000000
         Maximum value for a number in the data container: 50000000
         Should the value to search for exceed the maximum number? No
         The random number generated is: 38947767

⏱  Total time for running 10 runs in 3 benchmark campaigns: [3.8084400999999986, 3.7642792000000043, 3.761819200000005]

🧮 Average time for running  10 runs in 3 benchmark campaigns: [0.38084400999999984, 0.3764279200000004, 0.3761819200000005]
```

#### 4. Output from running the `containmentcheck` program

RQ 2. *Run 5*

`poetry run containmentcheck --approach tuple --size 100000000 --maximum 50000000`

```
✨ Conducting an experiment to measure the performance of containment checking!
         Type of the data container: tuple
         Size of the data container: 100000000
         Maximum value for a number in the data container: 50000000
         Should the value to search for exceed the maximum number? No
         The random number generated is: 49567538

⏱  Total time for running 10 runs in 3 benchmark campaigns: [0.28162279999999384, 0.28208070000000873, 0.2832293000000021]

🧮 Average time for running  10 runs in 3 benchmark campaigns: [0.028162279999999384, 0.028208070000000873, 0.02832293000000021]
```

#### 5. Output from running the `containmentcheck` program

RQ 3. *Run 1*

`poetry run containmentcheck --approach list --size 50000000 --maximum 500000000 --exceed`

```
✨ Conducting an experiment to measure the performance of containment checking!
         Type of the data container: list
         Size of the data container: 50000000
         Maximum value for a number in the data container: 500000000
         Should the value to search for exceed the maximum number? Yes
         The random number generated is: 500000001

⏱  Total time for running 10 runs in 3 benchmark campaigns: [7.175067999999996, 7.1365798, 7.1366093999999975]

🧮 Average time for running  10 runs in 3 benchmark campaigns: [0.7175067999999996, 0.71365798, 0.7136609399999998]
```

## Experiment Design

For my experiment with `containmentcheck`, I have three research questions that I designed this systemic testing around. For each of my questions, I had to adjust the parameters to address what the question specified. 
  
For the first research question, there were three varying sizes of containers. This meant that I ran three trials with the lists, three with the tuples, and three with the sets. Of the three tests for each, one was at the container size of 50000000, 100000000, and 200000000. These container sizes were chosen due to the concept of the doubling experiment. Everything else in these runs remained constant. Due to the question specification, the value exceed the container maximum and was thus not found within the container. The maximum value of item was designated as 50000000 to have a number large enough that the program would take time to iterate through the data containers but not too large that the experiment would not be completed in a timely fashion.

For the second research question, this was constructed very similarly to the first research question. The data container types, sizes, and maximum value are the same as the first question for the same reasonings. This questions then builds on the first by searching for a value within the container. This is seen by the exceed parameter as not being fulfilled. This then causes a random number to be generated and searched for within the container.

Lastly, the third question was constructed to look at the changes caused by a small or large maximum value specified. Since this question only has two options for a changing variable, I only ran each data container type twice. Each of these runs had the item that was being searched for exceed the maximum value so that the program would have to iterate through the complete data container. I chose to have the size of the container remain constant at the size of 50000000 as that was the smallest size of other trials.

## Research Questions

RQ1. When the value exceeds the container maximum and using the `in` operator for containment checking, which data container has the least time overhead at varying sizes (50000000, 100000000, 200000000)?

RQ2. When the value does not exceed the container maximum and using the `in` operator for containment checking, which data container has the least time overhead at varying sizes (50000000, 100000000, 200000000)?

RQ3. When the value exceeds the container maximum and using the `in` operator for containment checking, do all of the containers have the least time overhead with a maximum value of 500000000 or a maximum value of 1000000000?


## Data Tables

**RQ1 Data**

| Run Number | Approach | Container Size | Maximum Value | Exceed? | Number Generated | Average Time |
| ---------- | -------- | -------------- | ------------- | ------- | ---------------- | ------------ |
| 1 | List  | 50000000  | 50000000 | Yes | 5000001 | 0.7330810300000003 |
| 2 | List  | 100000000 | 50000000 | Yes | 5000001 | 1.45781217         |
| 3 | List  | 200000000 | 50000000 | Yes | 5000001 | 4.7324482833       |
| 4 | Tuple | 50000000  | 50000000 | Yes | 5000001 | 0.71052497         |
| 5 | Tuple | 100000000 | 50000000 | Yes | 5000001 | 1.487639496666666  |
| 6 | Tuple | 200000000 | 50000000 | Yes | 5000001 | 2.772335753333329  |
| 7 | Set   | 50000000  | 50000000 | Yes | 5000001 | 8.436690333333332  |
| 8 | Set   | 100000000 | 50000000 | Yes | 5000001 | 21.63500049666667  |
| 9 | Set   | 200000000 | 50000000 | Yes | 5000001 | 48.51392534666667  |

**RQ2 Data**

| Run Number | Approach | Container Size | Maximum Value | Exceed? | Number Generated | Average Time |
| ---------- | -------- | -------------- | ------------- | ------- | ---------------- | ------------ |
| 1 | List  | 50000000  | 50000000 | No | 4952099  | 0.1673123899966667 |
| 2 | List  | 100000000 | 50000000 | No | 38947767 | 0.3778179499999997 |
| 3 | List  | 200000000 | 50000000 | No | 15893154 | 0.100089613333334  |
| 4 | Tuple | 50000000  | 50000000 | No | 3090116  | 0.0374669233333333 |
| 5 | Tuple | 100000000 | 50000000 | No | 49567538 | 0.0282310933333334 |
| 6 | Tuple | 200000000 | 50000000 | No | 49962854 | 0.57804824333333   |
| 7 | Set   | 50000000  | 50000000 | No | 1529867  | 9.522051323333233  |
| 8 | Set   | 100000000 | 50000000 | No | 2067991  | 21.93860423999997  |
| 9 | Set   | 200000000 | 50000000 | No | 21588813 | 47.51411206666633  |

**RQ3 Data**

| Run Number | Approach | Container Size | Maximum Value | Exceed? | Number Generated | Average Time |
| ---------- | -------- | -------------- | ------------- | ------- | ---------------- | ------------ |
| 1 | List  | 50000000 | 500000000  | Yes | 500000001  | 0.7149419066666665 |
| 2 | List  | 50000000 | 1000000000 | Yes | 1000000001 | 0.7180023766666665 |
| 3 | Tuple | 50000000 | 500000000  | Yes | 500000001  | 0.7160524433333334 |
| 4 | Tuple | 50000000 | 1000000000 | Yes | 1000000001 | 0.7001302366666666 |
| 5 | Set   | 50000000 | 500000000  | Yes | 500000001  | 7.910954706666667  |
| 6 | Set   | 50000000 | 1000000000 | Yes | 1000000001 | 7.57319038         |


## Performance Analysis

### Empirical Evaluation

After completing the trials for this experiment and reviewing the results, there is some interesting trends across the questions. The first research question seemed to control for more variables in comparison to the second research question due to the exceed tag. The runs for the first research question assured that all of the containers would have to iterate all the way through. The second question allowed for the possiblity for the algorithm to find the item it was searching for and exit earlier. This has still pulled interesting results as the findings were still generally similar between the two runs. The third question also interestingly supported the following findings.

Overall, I would claim that the set, by far, was the slowest in this evalution. Looking at the data collected from the experimental runs, the tuple was 91.58% faster than the set and the list was 91.31% faster than the set at the smallest container size. This gap only increased as the container size increased. At the middle size, the list was 93.26% faster, and the tuple was 93.12% faster than the set. At the largest size tested, the tuple was 94.28% faster than the set, and the list was 90.25% faster than the set. This makes sense as the code in the set is actually converting a list into a set. I believe this is what caused such a dramatic difference between these algorithms.


When looking at the fastest, I would have to claim that the tuple was the fastest due to the data collected from this experiment. At the smallest and middle size containers, the list and tuple went back and forth of which was faster at very small percentages. At the smallest size, the uple was 03.07% faster than the list. However, the list was 2.00% faster than the tuple. The claim is swayed by the data collected with the largest size where the tuple was 41.41% faster than the list. The third research question also highlighted this event as the tuple or list were not always faster than its counterpart. I would ideally suggest rerunning these trials a couple times to confirm this finding before concluding officially. 


### Analytical Evaluation

The worst-case time complexity for the three containment check algorithms were all O(n), also reffered to as linear. I know this from the doubling experiment I conducted. When using the data from the runs for the first research question, I recieved a doubling ratio of   1.9886098675885793 for the list runs (calculated from run 1 & 2), 2.0937188128190143 for the tuple runs (calculated from run 4 & 5), and 2.5643942875545482 for the set runs (calculated from run 7 & 8). All of these ratios are about 2 which suggests the linear worse-case time complexity. This can also be evaluted by looking at the source code and counting the operators which all also suggest O(n).

## Source Code

### Describe in detail how the provided source code works

```python
number_runs = 10
number_repeats = 3
execution_times = timeit.Timer(containment_check_lambda).repeat(
    repeat=number_repeats, number=number_runs
)
```

This section of python source code begins by initalizing two variables. The first variable of `number_runs` is set as 10 and the `number_repeats` is set as 3. Stored in the variable `execution_times`, the code calls timeit to use Timer and repeat. The Timer takes the parameter containment_check_lambda which is timing the function running from start to end. The repeat takes in the two variables that were just initalized. This tells the program to run containmentcheck 10 times then repeat that 3 times. This cause us to have 3 sets of 10 runs of containmentcheck.

## Professional Development

### What is challenging about designing an experiment to evaluate an algorithm's performance?

The most challenging part about designing an experiment to evaluate an algorithm's performance is having a full enough understanding of the program. Having a decent understanding of the code you are using is critical in creating logical research questions. However, understanding a program completely leads to many experimental questions seemingly pointless to ask. This balance is important to conducting a worthwhile experiment and often requires a recursive process of developing research questions. 

### Why is it necessary to perform both an analytical and an empirical evaluation of an algorithm?

It is necessary to perform both analytical and empirical evaluations of an algorithm because they test different parts of algorithm. The analytical evalution looks at the quality and complexity of the code. This one is just analyzing the source code. Empirical evalutions use the algorithm with actual inputs. This type of evalution allows for us to excute the code and record values like runtime or space used. Doing both allows us to get a fuller picture of the algorithms we are evaluating.

### How do the empirical results suggest that you don't yet know the entire story about the performance of containment checking?

These empirical results suggest we do not yet know the entire story about containment checking because we saw that sets were the slowest throughout all of the runs. From other sources we discussed in class, sets are supposed to be the fastest. When looking at the source code through an analytical approach we can tell that the set function is actually working wiht a list that is then turned into a set. This operation is so slow that the quickness of working with the set does not outweigh the cost of making the data a set. In practice, the set is not fast enough to make up for the other necessary time costs.
