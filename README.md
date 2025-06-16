```markdown
# 🧠 Parallel Sudoku Solver & Verifier

This project provides a fully functional Sudoku solver that uses constraint propagation and depth-first search with backtracking. It also includes multiprocessing support to verify multiple puzzles in parallel.

---

## 📦 Features

- Solves standard 9x9 Sudoku puzzles
- Uses solving strategies:
  - Elimination
  - Only Choice
  - Naked Twins
- Applies backtracking search when constraints aren't enough
- Verifies puzzles against known solutions
- Utilizes Python multiprocessing for faster verification

---

## 📁 File Structure

```

sudoku\_solver/
│
├── sudoku\_solver.py         # Main script to solve & verify puzzles
├── sudoku\_sample.csv        # CSV file with quizzes and their solutions
└── README.md                # This file

```

---

## 📜 CSV File Format

The script expects a CSV file (`sudoku_sample.csv`) with the following columns:

- `quizzes`: 81-character string of a Sudoku puzzle  
  - Use `'0'` or `'.'` to represent empty cells
- `solutions`: 81-character string of the correct solution

Example:
```

quizzes,solutions
530070000600195000098000060800060003400803001700020006060000280000419005000080079,534678912672195348198342567859761423426853791713924856961537284287419635345286179

````

---

## ⚙️ How It Works

1. Each puzzle is converted into a dictionary of possible values.
2. Solving strategies (`eliminate`, `only_choice`, `naked_twins`) are applied to reduce the puzzle.
3. If needed, a recursive backtracking search is used to complete the puzzle.
4. The results are compared against the provided solution.
5. Puzzles are processed in parallel using multiple CPU cores for speed.

---

## 🚀 How to Run

1. **Prepare the Environment**
   - Requires Python 3.6+
   - Install dependencies:
     ```bash
     pip install pandas numpy
     ```

2. **Edit File Path (if needed)**
   - Modify the `path` in `sudoku_solver.py` to point to your `sudoku_sample.csv`

3. **Run the Solver**
   ```bash
   python sudoku_solver.py
````

4. ✅ If all puzzles are solved correctly:

   ```
   ✅ All puzzles solved and verified successfully.
   ```

5. ❌ If there are mismatches:

   * You'll see detailed output showing which puzzles failed.

---

## 🧪 Customization

* Change `data.head(5)` to `data` to check the full dataset.
* Modify `num_partitions` and `num_cores` for your hardware.

---

## 📌 Notes

* This solver is designed for valid Sudoku puzzles only.
* Includes helpful error messages for malformed input.

---

## 📧 Contact

For questions or feedback, open an issue or contact the project maintainer.

```

Let me know if you'd like a version with screenshots or usage examples too!
```
