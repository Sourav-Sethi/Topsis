# TOPSIS: Technique for Order of Preference by Similarity to Ideal Solution  

TOPSIS is a Python library designed to implement the Technique for Order of Preference by Similarity to Ideal Solution, a multi-criteria decision-making method. It enables users to rank alternatives based on specified criteria, weights, and impacts.  

# Installation  
Install the library via pip:  
```bash
pip install Topsis-102216078
```  

---
# Usage  

# Command-line Usage 
The library can be used directly from the command line.  

Syntax:  
```bash
python <program.py> <InputDataFile> <Weights> <Impacts> <ResultFileName>
```  

Example:  
1. Create an input file, `data.csv`:  
   ```csv
   Name,C1,C2,C3,C4
   A,250,16,12,5
   B,200,32,8,3
   C,300,24,10,4
   D,275,20,11,4
   E,225,28,9,2
   ```  

2. Run the command:  
   ```bash
   python topsis.py data.csv "0.25,0.25,0.25,0.25" "+,+,-,+" result.csv
   ```  

3. The output file `result.csv` will contain:  
   ```csv
   Name,C1,C2,C3,C4,Topsis Score,Rank
   A,250,16,12,5,0.64,2
   B,200,32,8,3,0.43,4
   C,300,24,10,4,0.78,1
   D,275,20,11,4,0.56,3
   E,225,28,9,2,0.36,5
   ```  

---

### Python Library Usage  
You can also use the library programmatically in Python.  

Example Code:  
```python
from topsis import Topsis

# Input data
data = "data.csv"
weights = [0.25, 0.25, 0.25, 0.25]
impacts = ["+", "+", "-", "+"]
result_file = "result.csv"

# Perform TOPSIS
Topsis(data, weights, impacts, result_file)
print(f"Results saved in {result_file}")
```  

---

## Parameters  

1. InputDataFile:  
   A CSV file where the first column contains the names of the alternatives and the remaining columns contain numeric criteria values.  

2. Weights:  
   A comma-separated string of numeric weights, e.g., `"0.25,0.25,0.25,0.25"`.  

3. Impacts:  
   A comma-separated string indicating the impact of each criterion:  
   - `+` for positive impacts.  
   - `-` for negative impacts.  

4. ResultFileName:  
   The name of the output CSV file where the results will be saved.  

---

# Features  
- **Input Validation**: Automatically validates the input file format and checks for invalid or missing values.  
- **Criteria Normalization**: Normalizes criteria values and applies the specified weights.  
- **Ranking**: Calculates TOPSIS scores and ranks the alternatives.  

---

# Limitations  
- All criteria values must be numeric.  
- The number of weights and impacts must match the number of criteria.  

---

# License  
This project is licensed under the **MIT License**. See the `LICENSE` file for details.  

---

# Contributing  
Contributions are welcome! Feel free to open issues or submit pull requests to improve the library.  

---

# Author  
Sourav Sethi  

---  
