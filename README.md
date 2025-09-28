Divide-and-Conquer
How to Run

Open the folder in IntelliJ IDEA.

Set the SDK to Java 17+.

To run tests:
dnc.test.TestRunner

To run the app:
dnc.cli.Main with:

--algo mergesort|quicksort|select|closest|all

--n <size> — number of elements

--trials <t> — repetitions

--out metrics.csv — output CSV file

Project Notes

QuickSort: recurses into the smaller side, so memory stays ~log n.

MergeSort: uses a single reusable buffer; tiny ranges use insertion sort.

Select (Median of Medians): narrows to the side containing the k-th element.

Closest Pair: keeps points sorted and checks at most 7 neighbors in the strip.

Metrics

comparisons — number comparisons.

allocations — counted memory allocations.

max_depth — maximum recursion depth.

CSV schema:
algo,n,trial,time_ns,max_depth,comparisons,allocations,notes

Recurrence (Theory)

MergeSort: Θ(n log n)

QuickSort (randomized): Θ(n log n), depth ≈ log n

Select (MoM): Θ(n)

Closest Pair: Θ(n log n)

Plots

Build charts from the CSV file.

Summary

Compare measured results with theory.

Small gaps can come from cache effects, GC, and constant factors.