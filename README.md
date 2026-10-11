# Parallel Sum and Average of Dataset Using OpenMP

## Team Members

| Name | USN |
|---|---|
|Anupriya S  |01FE24BCI046 |
|Pavitra J |01FE24BCI049 |
|Anushree A  |01FE24BCI050  |
|Sahana A |01FE24BCI030  |

## Objective

To implement parallel sum and average calculation on a dataset using OpenMP and evaluate the effect of different dataset sizes and thread counts on execution time, speedup, and parallel efficiency.

## Project Description

This project compares sequential execution with OpenMP-based parallel execution for calculating the sum and arithmetic average of a dataset.

The dataset contains consecutive integer values from 1 to N. The program calculates the sum and average sequentially and then performs the sum calculation using different OpenMP thread counts.

## Technologies Used

- Programming language: C
- Parallel programming: OpenMP
- Compiler: GCC
- Operating environment: Ubuntu running in VMware
- Graph generation: Python and Matplotlib

## Experimental Configuration

**Dataset sizes**
- 100,000 elements
- 1,000,000 elements
- 10,000,000 elements

**Thread counts**
- 1, 2, 4, 8, 16, 32

## Repository Structure

- `src/` — C source code for sequential and parallel computation.
- `data/` — Dataset generation utilities.
- `results/` — Raw experimental results.
- `graphs/` — Execution-time, speedup, and efficiency graphs.
- `report/` — Experiment report and analysis.
- `presentation/` — Final lab evaluation PowerPoint presentation.

## Compilation

Install the required compiler:

```bash
sudo apt update
sudo apt install build-essential python3-matplotlib -y
```

Compile the program:

```bash
gcc -O2 -fopenmp src/sum_average.c -o sum_average
```

## Execution

Run the program:

```bash
./sum_average
```

Enter one of the supported dataset sizes when prompted.

## Performance Metrics

Speedup is calculated as:

Speedup = Sequential Execution Time / Parallel Execution Time

Parallel efficiency is calculated as:

Efficiency (%) = Speedup / Number of Threads × 100

## Current Experimental Observation

For the dataset of 10,000,000 elements, the best observed result in the recorded run was obtained using four OpenMP threads:

- Sequential time: 0.006908 seconds
- Parallel time: 0.002608 seconds
- Speedup: approximately 2.65×
- Efficiency: 66.21%

These are preliminary single-run measurements. Repeated measurements and averaged timings are recommended for more reliable performance conclusions.

## Expected Outcome

The project demonstrates the use of OpenMP to parallelize a dataset computation and evaluates how dataset size and thread count influence performance.

## Conclusion

The experiments show that OpenMP can improve the performance of sum calculation for sufficiently large datasets. However, increasing the number of threads does not always reduce execution time because of thread-management overhead, resource limitations, and timing variation.
