# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

Using the example in the slides, you have a 50% chance of picking a "good pivot"(an element in the middle $n/2$ elements). In median of 3 (first, median, last), there are $3^3$ or 27 possible permutations of: good pivots(G), less pivots(L - pivots that are less than the middle $n/2$ elements), and bigger pivots(B - pivots that are larger than the desired $n/2$ elements). These permutations are:

GGG,GGB,GBG,BGG,GBB,BGB,BBG,BBB,GGL,GLG,LGG,LGL,LLG,GLL,LLL,BBL,BLB,LBB,LBL,LLB,BLL,BLG,GBL,LBG,BGL,GLB,LGB

We now need to know how often the good pivot(G) can be cosen as a pivot. We have these permutations: GGG,BGB,BGG,GGB,GGL,LGL,LGG,BGL,LGB,GLB,LBG,GBL,BLG
GGG = $1/2^{3}$ = 1/8
GLL,LGL,LLG,BBG,BGB, and GBB all have a $1/4 * 1/2 * 1/4$ probability, so $6 * 1/32 = 6/32$
GGB,GBG,BGG,GGL,GLG, and LGG all have a $1/4 * 1/2 * 1/2$ probability, so $6 * 1/16 = 6/16$

adding these probabilities together, $1/8 + 6/32 + 6/16$ = $0.125 + 0.1875 + 0.0.375$ = $0.6875$ which is a %68.75 chance of choosing a good pivot, which is greater than the %50 chance you get with the leftmost method.

Help: I refered back to page 34, and also referenced Will-GreinerUWYO's repo which really helped me understand what each number(BGL) in these permutations represented, after I understood their respective probabilities, it was a lot easier to figure out the total probability of picking a good pivot.

“I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.”
