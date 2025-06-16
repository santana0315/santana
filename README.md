# Sudoku Solver (Parallelized with Multiprocessing)

This project provides a complete Sudoku puzzle solver with support for batch processing multiple puzzles in parallel using Python's `multiprocessing` module.

## Features

* Solves standard 9x9 Sudoku puzzles using constraint propagation and depth-first search
* Implements Sudoku strategies including:

  * Elimination
  * Only Choice
  * Naked Twins
* Parses grid-style puzzles (string of 81 characters)
* Processes multiple puzzles in parallel
* Displays original and solved puzzles

## File Structure

* `sudoku_parallel_solver.py`: Main implementation script
* `sudoku_sample.csv`: Input CSV containing Sudoku puzzles with at least a `quizzes` column
* `README.md`: Documentation file (this)

## Requirements

* Python 3.6+
* pandas
* numpy

Install required packages:

```bash
pip install pandas numpy
```

## Input Format

The input CSV file must contain a column named `quizzes` with each entry being an 81-character Sudoku string. Example:

```
quizzes
530070000600195000098000060800060003400803001700020006060000280000419005000080079
...
```

## How to Run

Update the CSV path in the script if necessary:

```python
path = r"C:\\Users\\santa\\IdeaProjects\\kaggle\\sudoku_sample.csv"
```

The script will:

1. Load the top 5 puzzles from the CSV
2. Solve them in parallel
3. Print original and solved puzzles

## Output Example

```
Original Puzzle:
530070000600195000098000060...
Solved Puzzle:
534678912672195348198342567...
```

## Notes

* Solving uses recursive search, which may be slow for large batches
* You can increase `data.head(5)` to process more puzzles
* Adjust `num_partitions` and `num_cores` based on your CPU

## License

MIT
