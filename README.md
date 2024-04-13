
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


![Graph](data:image/png;base64,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)


The time taken is minimum when the number of threads is 5.
## Submitted By:
Akshita Gupta
102103741


