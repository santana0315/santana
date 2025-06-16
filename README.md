
---

```markdown
# 🧩 Parallel Sudoku Solver

This project is a parallelized Sudoku solver built in Python. It reads puzzles from a CSV file and solves them efficiently using constraint propagation, search algorithms, and multiprocessing.

## 📌 Features

- Solves standard 9x9 Sudoku puzzles
- Implements:
  - Elimination strategy
  - Only-choice strategy
  - Naked twins technique
  - Recursive depth-first search
- Uses Python's `multiprocessing` to solve puzzles in parallel
- Supports batch processing from a CSV file

## 📁 File Structure

```

sudoku\_solver.py         # Main script to solve Sudoku puzzles
sudoku\_sample.csv        # CSV file containing puzzles in 'quizzes' column
README.md                # This documentation

```

## 📥 Input

The input CSV file must contain a column named `quizzes` where each row is a Sudoku puzzle represented by an 81-character string. Use `.` or `0` for empty cells.

Example:
```

quizzes
"530070000600195000098000060800060003400803001700020006060000280000419005000080079"

```

## 📤 Output

For each puzzle, the script prints:
- Original Puzzle (in string format)
- Solved Puzzle (in grid format or `No solution`)

Example:
```

Original Puzzle:
530070000600195000098000060800060003400803001700020006060000280000419005000080079
Solved Puzzle:
534678912672195348198342567859761423426853791713924856961537284287419635345286179
✅ All puzzles processed.

````

## ⚙️ Requirements

- Python 3.6+
- pandas
- numpy

Install dependencies:
```bash
pip install pandas numpy
````

## 🚀 How to Run

1. Place your puzzles in a file named `sudoku_sample.csv` in the following format:

    * Column name: `quizzes`
    * One puzzle per row
2. Run the script:

```bash
python sudoku_solver.py
```

> ✅ You can modify the number of cores or partitions used in the script for performance tuning.

## 🧠 Algorithm Overview

* **Grid Parsing**: Converts an 81-character string into a 9x9 dictionary.
* **Constraint Propagation**: Applies:

    * Elimination of known digits from peers
    * Only-choice to assign digits that fit in one location only
    * Naked Twins to reduce ambiguity
* **Search**: Depth-first recursive search when constraint solving is insufficient
* **Parallelization**: Uses `multiprocessing.Pool` to divide the dataset into partitions and solve them concurrently.

## 👤 Author

Created by \[Yash Choudhary].

## 📄 Example csv to run the code.

````
quizzes,solutions
530070000600195000098000060800060003400803001700020006060000280000419005000080079,534678912672195348198342567859761423426853791713924856961537284287419635345286179
000000907000420180000705026100904000050000040000507009920108000034059000507000000,483621957765429183219735426176984532358192647294567819925148763634259871547316298
302609005000000000000000000000000000000000000000000000000000000000000000000000000,302609845145783269879124356683591427421376598957842613768935124214768935395412687
100920000524010000000000070050008102000000000402700090060000000000030945000071006,176923584524817639398645271657489132913256748482731596861594327729368415345172986
043080250600000000000001094900004070000608000010200003820500000000000005034090710,143986257698742531257351894986134572372658149415279683821597346769413825534862719

````
