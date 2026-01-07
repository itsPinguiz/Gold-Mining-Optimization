## The Project Work Challenge

### Problem Specification
The final project involves a variation of the **Vehicle Routing Problem (VRP)** with dynamic costs.

* **Environment:** $N$ cities arranged on a grid.
* **Home Base:** City 0, located at the center (coordinates 0, 0).
* **Resource:** Each city contains a specific amount of **Gold** (float value, e.g., $1 + \text{random} \times 999$).
* **Goal:** Collect all gold from all cities and bring it back to base.
* **Partial Collection:** You are **not required** to collect all the gold in a city during a single visit. You may collect a portion of the gold, leave, and return later for the remainder, provided that eventually 100% of the gold is collected.
* **Graph:** Cities are not fully connected (variable edge density).

#### Cost Dynamics
The cost of travel increases with the weight (gold) you are carrying, not just distance.

$$ \text{Cost}(i, j) = d(i, j) + {(d(i, j) \cdot \text{CurrentGold} \cdot \alpha)}^{\beta} $$

* $\alpha, \beta$: Constants defining the weight penalty.
* **Strategic Implication:** The optimal strategy might involve **multiple trips** back to base to unload, or picking up only small amounts from specific cities to keep travel costs low.

---

### Implementation Requirements
Your submission must follow a strict structure for automated testing:

* **Repository Name:** `project-work`
* **Main File:** `s<studentID>.py` (e.g., `s123456.py`) containing a `solution` function.
* **Source Folder:** `src/` for all auxiliary code.
* **Entry Point:** The test script will dynamically import: `from s123456 import solution`.
* **Output:** The function must return a list of tuples representing the path and item choices.

**Project Structure Example:**

```python
# Folder: project-work/
#   |- src/
#       |- algorithm.py
#       |- utils.py
#   |- s123456.py

# Content of s123456.py
from src.algorithm import my_genetic_algorithm

def solution(problem_instance):
    # Setup problem
    # Run optimization
    path = my_genetic_algorithm(problem_instance)
    return path
```

---

### Submission Guidelines
* **Deadline:** 168 hours (7 days) before the exam date.
* **No Reports:** Do not upload PDFs or logs to the repository.