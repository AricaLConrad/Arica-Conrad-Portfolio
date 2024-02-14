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

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-1.png" alt="Screenshot of a PowerPoint slide. The heading says, What is Dynamic Programming? There are four bullet points beneath the heading, which have the following text: Different than what we have seen so far in class, as it is not an algorithm. It is a way of optimizing your code over just using plain recursion. The idea is to take a complex problem and break it down into simpler subproblems in a recursive manner. You then store the results of those subproblems so you do not have to recompute them when they are needed later." width="100%" height="100%"/>

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-2.png" alt="Screenshot of a PowerPoint slide. The heading says, Memoization versus Tabulation. The Memoization bullet points have the following text: Code is easy and less complicated. Slow due to a lot of recursive calls and return statements. A memoized solution has the advantage of solving only the subproblems that are definitely required. Unlike the Tabulated version, all entries of the lookup table are not necessarily filled in the Memoized version (the table is filled on demand). The Tabulation bullet points have the following text: Code gets complicated when a lot of conditions are required. Fast, as we directly access previous solutions from the table. If all subproblems must be solved at least once, a bottom-up DP approach usually outperforms a top-down memoized algorithm by a constant factor. In Tabulated version, starting from the first entry, all entries in the table are filled one by one." width="100%" height="100%"/>

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-3.png" alt="Screenshot of a PowerPoint slide. The heading says, What is the 0-1 Knapsack Problem? There is a picture of a backpack and various boxes with weight and dollar amounts labeled on each box. There are seven bullet points beneath the heading, which have the following text: One of the most common DP problems. You have a set amount of weight you can store in the knapsack. You have items with varying weights and values you want to store in the knapsack. What is the maximum value you can store in the knapsack? Important: The 0-1 part means you cannot break an item! You either pick the item or you don't. Different than the Fractional Knapsack Problem." width="100%" height="100%"/>

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-4.png" alt="Screenshot of a PowerPoint slide. The heading says, Types of Algorithmic Paradigms. There are three sections listed: Divide and Conquer, Greedy Algorithms, and Dynamic Programming. The Divide and Conquer section has the following bullet points: Divide a problem into small sub-instances of the same problem, solve these recursively, and then put the solutions together to be a solution of the given problem. Examples: Merge Sort and Quick Sort. The Greedy Algorithms section has the following bullet points: Finds solutions by always making the choice that looks optimal at the moment - do not look ahead, never go back. Examples: Prim's Minimum Spanning Tree and Kruskal's Minimum Spanning Tree. The Dynamic Programming section has the following bullet points: Recursively or iteratively solves subproblems and remembers the solutions to those subproblems. Example: Floyd-Warshall Algorithm for the All Pairs Shortest Path problem." width="100%" height="100%"/>

<img src="../assets/images/Conrad-Dynamic-Programming-Presentation-Sample-Slide-5.png" alt="Screenshot of a PowerPoint slide. The heading says, Conclusion. There are four bullet points beneath the heading, which have the following text: Dynamic programming (DP) is a way of optimizing your code by breaking down a problem into smaller subproblems and remembering what you did. A problem must have both optimal substructures and overlapping subproblems in order to be solved using DP. You can store the solutions to subproblems using memoization (top down) or tabulation (bottom up). A useful skill to know, but tricky to master." width="100%" height="100%"/>

# 0-1 Knapsack Problem - Recursive Solution

After I explained what the 0-1 Knapsack Problem was with my PowerPoint presentation, I switched to walking through code. The first code example I showed was the recursive solution to the Knapsack Problem. This recursive approach is not the most efficient solution to the Knapsack Problem, but it is still a solution that works.

You can view the code I used here:

```
// Arica Conrad
// Recursive Approach in C# to the 0-1 Knapsack Problem

// Source: https://www.geeksforgeeks.org/0-1-knapsack-problem-dp-10/
// This code is made by Sam007 from GeeksforGeeks.

using System;

namespace KnapsackRecursiveApproach
{
    class Program
    {
        // A utility function that returns the larger value of two given integers. 
        static int max(int a, int b)
        {
            return (a > b) ? a : b;     // If a is greater than b, return a, otherwise return b.
        }

        // Returns the maximum value that can be put in a knapsack of capacity W. 
        static int knapSack(int W, int[] wt,
                            int[] val, int n)
        {

            // Base Case 
            if (n == 0 || W == 0)               // If there are no more items left, or if the knapsack is full, return 0.
                return 0;

            // If the weight of the nth item is more than Knapsack capacity W, then this item cannot be included in the optimal solution. 
            if (wt[n - 1] > W)
                return knapSack(W, wt, val, n - 1);

            // Return the maximum of two cases: 
            // (1) nth item included 
            // (2) not included 
            else
                return max(
                    val[n - 1] + knapSack(W - wt[n - 1], wt, val, n - 1),       // This means we have included the item in the knapsack. 
                    knapSack(W, wt, val, n - 1));                               // This means we have not included the item in the knapsack.
        }

        // Driver function 
        public static void Main()
        {
            int[] val = new int[] { 60, 100, 120 };     // The values of three items we want to put in our knapsack (60, 100, 120, respectively).
            int[] wt = new int[] { 10, 20, 30 };        // The weights of those three items (10 lbs, 20 lbs, 30 lbs, respectively).
            int W = 50;                                 // The weight capacity of the knapsack (50 lbs).
            int n = val.Length;                         // The total amount of items we are working with AKA the array length (3 items).

            Console.WriteLine("The maximum value the knapsack can hold is: {0}", knapSack(W, wt, val, n));
            Console.ReadLine();
        }
    }
}
```

# 0-1 Knapsack Problem - Dynamic Programming Solution (Tabulation)

After I showed the code for the recursive solution to the 0-1 Knapsack Problem, I then showed the Dynamic Programming solution. This particular approach uses the tabulation method, as the table is being filled in a bottom-up approach. Using Dynamic Programming makes this solution more efficient.

You can view the code I used here:

```
// Arica Conrad
// Dynamic Programming Approach in C# to the 0-1 Knapsack Problem

// Source: https://www.geeksforgeeks.org/0-1-knapsack-problem-dp-10/
// This code is made by Sam007 from GeeksforGeeks.

using System;

namespace KnapsackDynamicProgrammingImplementation
{
    class Program
    {
        // A utility function that returns the larger value of two given integers. 
        static int max(int a, int b)
        {
            return (a > b) ? a : b;         // If a is greater than b, return a, otherwise return b.
        }

        // Returns the maximum value that can be put in a knapsack of capacity W.
        static int knapSack(int W, int[] wt,
                            int[] val, int n)
        {
            int i, w;
            int[,] K = new int[n + 1, W + 1];       // A new 2-D array.

            // Build table K[][] in bottom up manner (tabulation). 
            for (i = 0; i <= n; i++)
            {
                for (w = 0; w <= W; w++)
                {
                    if (i == 0 || w == 0)           // If there are no more items or space in the knapsack left, store 0 in the graph at that location.
                        K[i, w] = 0;
                    else if (wt[i - 1] <= w)        // If the weight of an item is less than or equal to the maximum weight of the knapsack...
                        K[i, w] = Math.Max(
                            val[i - 1] + K[i - 1, w - wt[i - 1]],       // This means we have included the item in the knapsack. 
                            K[i - 1, w]);                               // This means we have not included the item in the knapsack.
                    else                            // If the weight of an item is greater than the maximum weight of the knapsack, ignore adding the item's weight. 
                        K[i, w] = K[i - 1, w];
                }
            }

            return K[n, W];     // Return the maximum value when the knapsack is full.
        }

        // Driver code 
        static void Main()
        {
            int[] val = new int[] { 60, 100, 120 };     // The values of three items we want to put in our knapsack (60, 100, 120, respectively).
            int[] wt = new int[] { 10, 20, 30 };        // The weights of those three items (10 lbs, 20 lbs, 30 lbs, respectively).
            int W = 50;                                 // The weight capacity of the knapsack (50 lbs).
            int n = val.Length;                         // The total amount of items we are working with (3 items).

            Console.WriteLine("The maximum value the knapsack can hold is: {0}", knapSack(W, wt, val, n));
            Console.ReadLine();
        }
    }
}
```

<br> ---

[Home Page](../README.md) | [Technical Writing Samples Page](./technical-writing-samples.md)
