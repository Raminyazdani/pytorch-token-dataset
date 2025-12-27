# Git History Reconstruction: PyTorch Token Dataset

## History Expansion Note

**Previous Run:** N_old = 4 steps  
**Current Run:** N_new = 7 steps  
**Multiplier Achieved:** 1.75× (exceeds minimum requirement of 1.5×)

### Mapping from Old Steps to New Step Ranges

The previous 4-step history has been expanded to 7 steps with more granular commits:

- **Old step_01** (Initial scaffolding) → **New steps 01-02**
  - step_01: Initial .gitignore and README scaffolding
  - step_02: Add requirements.txt with core dependencies
  
- **Old step_02** (Core implementation) → **New steps 03-04**
  - step_03: Implement TokenDataset class with JSON loading
  - step_04: Add actual data files (data.json, data.csv)
  
- **Old step_03** (CSV support) → **New steps 05-06** (includes oops→hotfix)
  - step_05: Add CSVDataset class (OOPS - forgot pandas import)
  - step_06: Hotfix - add pandas import and update requirements.txt
  
- **Old step_04** (Portfolio polish) → **New step_07**
  - step_07: Final portfolio polish with all documentation

### Oops → Hotfix Sequence

**Step 05 - The Mistake:**
- Added CSVDataset class that uses `pd.read_csv()`
- Forgot to import pandas in the import cell
- The code references `pd` but pandas was never imported
- This is a classic developer mistake when adding new functionality

**Step 06 - The Fix:**
- Noticed the missing import when reviewing the code
- Added `import pandas as pd` to the imports cell
- Updated requirements.txt to include `pandas>=1.3.0`
- Removed the bug comment from CSVDataset implementation
- Now the code actually works correctly

This is a realistic scenario - developers often add new functionality that requires a new library but forget to add the import statement initially, then catch it during testing or code review.

---

## Development Timeline

### Step 01: Initial Project Scaffolding
**Commit Message:** `Initial commit: Add .gitignore and basic README`

**Description:**
Set up the foundational project structure with .gitignore for Python/Jupyter development and a basic README outlining the project goals.

**Files Added:**
- `.gitignore` - Python, Jupyter, IDE, and OS file exclusions
- `README.md` - Basic project description and setup instructions

**Rationale:**
Every professional project starts with proper repository hygiene. Adding .gitignore first prevents accidentally committing temporary files, and the README provides initial context for the project.

---

### Step 02: Add Dependencies Specification
**Commit Message:** `chore: Add requirements.txt with core dependencies`

**Description:**
Specified the Python dependencies needed for the project. At this stage, we know we'll need PyTorch, NumPy, scikit-learn, and Jupyter, but not yet pandas (that comes later with CSV support).

**Files Added:**
- `requirements.txt` - PyTorch, NumPy, scikit-learn, Jupyter (pandas not yet needed)

**Rationale:**
After setting up the basic structure, the next logical step is to document dependencies. This allows other developers (or yourself on a new machine) to set up the environment. We add only the dependencies we know we'll need for the core TokenDataset functionality.

---

### Step 03: Implement Core TokenDataset Class
**Commit Message:** `feat: Implement TokenDataset class with padding support`

**Description:**
Implemented the primary functionality - a custom PyTorch Dataset class for handling variable-length token sequences. Includes automatic padding, proper `__len__` and `__getitem__` methods, and integration with PyTorch's Dataset interface.

**Files Added:**
- `token_dataset.ipynb` - Jupyter notebook with TokenDataset implementation

**Key Features:**
- Custom Dataset class extending `torch.utils.data.Dataset`
- Automatic padding to max sequence length
- Proper tensor conversion for PyTorch compatibility
- Example usage with sample data

**Rationale:**
With scaffolding in place, we implement the core functionality. Starting with TokenDataset makes sense as it's the primary use case. The notebook format allows for iterative development and clear documentation of the implementation.

---

### Step 04: Add Real Data Files
**Commit Message:** `data: Add JSON and CSV data files for demonstrations`

**Description:**
Added the actual data files that will be used for demonstrating the dataset classes. The JSON file contains token sequences with labels, and the CSV file contains structured tabular data.

**Files Added:**
- `data.json` - Token sequences and labels (5,574 records)
- `data.csv` - Structured medical symptom data (708 rows)

**Rationale:**
Now that we have a working TokenDataset implementation, we need real data to test it with. Adding data files separately from the implementation is a clean separation of concerns and represents a realistic workflow where you might initially develop with sample data, then add production data later.

---

### Step 05: Add CSVDataset Class (with bug)
**Commit Message:** `feat: Add CSVDataset for structured data support`

**Description:**
Extended the project to support CSV data by implementing CSVDataset class with one-hot encoding for labels. However, this commit contains a bug - the code uses `pd.read_csv()` but pandas was never imported!

**Files Modified:**
- `token_dataset.ipynb` - Added CSVDataset class implementation

**The Bug:**
- CSVDataset uses `pd.read_csv()` but `import pandas as pd` is missing
- This would cause a `NameError: name 'pd' is not defined` at runtime
- A common mistake when rapidly adding new functionality

**Rationale:**
This represents a realistic development scenario. When adding new functionality, developers sometimes forget to add the necessary imports, especially when switching contexts or working quickly. The bug will be caught and fixed in the next commit.

---

### Step 06: Hotfix - Add Missing Pandas Import
**Commit Message:** `fix: Add missing pandas import for CSVDataset`

**Description:**
Fixed the import bug from the previous commit. Added `import pandas as pd` to the imports cell and updated requirements.txt to include pandas as a dependency.

**Files Modified:**
- `token_dataset.ipynb` - Added pandas to imports, cleaned up CSVDataset code
- `requirements.txt` - Added pandas>=1.3.0

**What Was Fixed:**
- Added `import pandas as pd` to the imports cell
- Updated requirements.txt to declare the pandas dependency
- Removed the bug notation from CSVDataset implementation
- Code now runs without NameError

**Rationale:**
After adding CSVDataset, a quick test (or code review) would reveal the missing import. This commit represents the quick hotfix that follows - adding the import and updating dependencies. This is a very common pattern in real development.

---

### Step 07: Portfolio Polish and Documentation
**Commit Message:** `docs: Add portfolio documentation and final polish`

**Description:**
Final preparation for portfolio presentation. Added comprehensive project identity documentation, detailed development report, issue tracking ledgers, and ensured all code is clean and professional.

**Files Added:**
- `project_identity.md` - Professional project metadata and description
- `report.md` - Complete development and verification documentation
- `suggestion.txt` - Issue tracking ledger with all findings
- `suggestions_done.txt` - Applied changes ledger

**Files Modified:**
- `README.md` - Enhanced with comprehensive usage, troubleshooting, and structure docs
- `token_dataset.ipynb` - Final cleanup of outputs and formatting
- `.gitignore` - Updated patterns for completeness

**Changes Made:**
- Comprehensive documentation of project purpose and approach
- Complete setup and usage instructions
- Portfolio-ready metadata and framing
- Clean, environment-independent code and docs
- Full development audit trail

**Rationale:**
When preparing a project for portfolio presentation, developers add the meta-documentation that showcases the work professionally. This includes project identity, comprehensive README, and audit documentation. This step transforms a functional project into a portfolio piece.

---

## Development Approach Summary

This history reflects a realistic incremental development pattern:

1. **Scaffolding** (steps 01-02) - Set up repository structure and dependencies
2. **Core Implementation** (steps 03-04) - Build primary functionality and add data
3. **Feature Extension** (steps 05-06) - Add CSV support with realistic bug→fix sequence
4. **Professional Polish** (step 07) - Prepare for portfolio presentation

The inclusion of the oops→hotfix sequence (steps 05-06) demonstrates real-world development where mistakes happen and are quickly corrected. This makes the history more believable and educational.

## Verification

Each step's snapshot contains a complete, working state of the repository at that point in development (with step 05 being the one exception where the code has a bug). The final step (step_07) matches the current repository state exactly.

No snapshot includes the `history/` directory itself (avoiding recursion) or `.git/` directory.
