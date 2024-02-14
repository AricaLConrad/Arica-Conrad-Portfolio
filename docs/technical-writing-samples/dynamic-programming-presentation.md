# Dynamic Programming Presentation 💻

# About This Assignment

This presentation about Dynamic Programming was an assignment for my Data Structures and Algorithms class. We were each assigned to do a presentation in pairs about a specific data structure/algorithm. My partner ended up dropping out of the class, so I did this presentation on my own. Each presentation had to be 20-30 minutes long and have both a technical explanation about the data structure/algorithm and a code walkthrough (we could use code we found online as long as we cited them and understood what the code did). These presentations were very important, as our peers would be using these presentations to complete their homework for that week, so the quality of our presentations could affect how well our peers understood the material. In essence, we were teachers for a week.

# Process

This type of assignment required a vast amount of research to complete. I had to learn the material myself first, and I had to know it well enough so I could teach it to the rest of the class. I spent many days reading about Dynamic Programming on websites, writing pages worth of notes in the process.

Once I felt comfortable enough with the material, I started drafting my PowerPoint presentation. I quickly learned during this process that having two different code examples of Dynamic Programming could be useful (my peers only used one code example for their presentations). Most beginning programmers are exposed to the Fibonacci Sequence, as it is an easy coding problem to solve. I thought that showing the Fibonacci Sequence being solved using Dynamic Programming first could help bridge the gap between my technical explanation and the more complex solutions of the 0-1 Knapsack Problem.

After my PowerPoint was completed and my code was written, I recorded myself presenting the material and walking through the code. This recording was then uploaded to Slack so it could be viewed by my peers.

# Sample Slides

If you would like to see the full PowerPoint presentation, you can view the PDF file [here](../assets/files/Conrad-Dynamic-Programming-Presentation.pdf).

Here are some sample slides from my presentation:

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-1.png" alt="Screenshot of a PowerPoint slide. The heading says, What is Dynamic Programming? There are four bullet points beneath the heading, which have the following text: Different than what we have seen so far in class, as it is not an algorithm. It is a way of optimizing your code over just using plain recursion. The idea is to take a complex problem and break it down into simpler subproblems in a recursive manner. You then store the results of those subproblems so you do not have to recompute them when they are needed later." width="75%" height="75%"/>

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-2.png" alt="Screenshot of a PowerPoint slide. The heading says, Memoization versus Tabulation. The Memoization bullet points have the following text: Code is easy and less complicated. Slow due to a lot of recursive calls and return statements. A memoized solution has the advantage of solving only the subproblems that are definitely required. Unlike the Tabulated version, all entries of the lookup table are not necessarily filled in the Memoized version (the table is filled on demand). The Tabulation bullet points have the following text: Code gets complicated when a lot of conditions are required. Fast, as we directly access previous solutions from the table. If all subproblems must be solved at least once, a bottom-up DP approach usually outperforms a top-down memoized algorithm by a constant factor. In Tabulated version, starting from the first entry, all entires in the table are filled one by one." width="75%" height="75%"/>

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-3.png" alt="Screenshot of a PowerPoint slide. The heading says, What is the 0-1 Knapsack Problem? There is a picture of a backpack and various boxes with weight and dollar amounts labeled on each box. There are seven bullet points beneath the heading, which have the following text: One of the most common DP problems. You have a set amount of weight you can store in the knapsack. You have items with varying weights and values you want to store in the knapsack. What is the maximum value you can store in the knapsack? Important: The 0-1 part means you cannot break an item! You either pick the item or you don't. Different than the Fractional Knapsack Problem." width="75%" height="75%"/>


# 0-1 Knapsack Problem - Recursive Solution

After I explained what the 0-1 Knapsack Problem was with my PowerPoint presentation, I switched to walking through code. The first code example I showed was the recursive solution to the Knapsack Problem. This recursive approach is not the most efficient solution to the Knapsack Problem, but it is still a solution that works.

You can view the code I used here:

```
Insert code here!
```

# 0-1 Knapsack Problem - Dynamic Programming Solution (Tabulation)

After I showed the code for the recursive solution to the 0-1 Knapsack Problem, I then showed the Dynamic Programming solution. This particular approach uses the tabulation method, as the table is being filled in a bottom-up approach. Using Dynamic Programming makes this solution more efficient.

You can view the code I used here:

```
Insert code here!
```

<br> ---

[Home Page](../README.md) | [Technical Writing Samples Page](./technical-writing-samples.md)
