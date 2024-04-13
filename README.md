
# Multi-threading using Python

Multiply 100 random matrices of size 1k x 1k with a constant matrix of size 1k x 1k and generate the result table and graph. 


## Methodology used in assignment:

"The aim is to parallelize matrix multiplication using multithreading in Python and analyze its performance with different numbers of threads.

1. **Matrix Multiplication Function:** The `matrix_multiply()` function is defined to perform matrix multiplication using NumPy's `np.dot()` function. The result of each multiplication operation is stored at a specific index in the `results` array.

2. **Multithreading Function:** The `run_with_threads()` function orchestrates the matrix multiplication process with a specified number of threads. It divides the list of matrices (`matrices`) into chunks based on the number of threads, assigns each chunk to a separate thread for multiplication, starts the threads, and then waits for all threads to finish execution. Finally, it calculates and returns the total time taken for the operation.

3. **Matrix Definitions:** We initialize a constant matrix `A` and generate a list containing 100 random matrices of the same dimensions.

4. **Execution:** The code iterates over a range of thread counts, from 1 to 8. For each thread count, it invokes the `run_with_threads()` function to perform matrix multiplication and records the time taken for each operation in the `time_taken` list.

5. **Results Presentation:** The results, showing the number of threads alongside the corresponding time taken, are presented in tabular format using the `tabulate()` function from the `tabulate` library.

6. **Plotting:** To visually analyze the relationship between the number of threads and the time taken, the code uses `matplotlib.pyplot.plot()` to create a line plot. The x-axis represents the number of threads, while the y-axis denotes the corresponding time taken. The resulting plot helps in understanding the performance characteristics of the matrix multiplication algorithm under different threading configurations.

**Observation:** Upon examining the results, it's noted that the time taken decreases as the number of threads increases, up to a certain point. However, beyond a certain number of threads, the performance gains diminish or even degrade due to overheads associated with thread creation and synchronization. This observation underscores the importance of selecting an optimal number of threads based on the available hardware and the nature of the computation."

## Results

| Threads | (T=1)  | (T=2)            | (T=3)            | (T=4)  | (T=5)            | [T=6]   | (T=7)            | (T=8)            |
|---|---|---|---|---|---|---|---|---|
| Time taken (sec) | 1.5454 | 1.1298            | 1.2076            | 1.1918 | 1.0669            | 1.1917 | 1.1288            | 1.1922            |


![graph](https://github.com/neelakshidob/Multithreading-102103766/assets/99609535/ed13e2b4-4597-4cbc-ab7c-dbe1281ff404)

The time taken is minimum when the number of threads is 5.
## Submitted By:
Neelakshi Gupta
102103766


