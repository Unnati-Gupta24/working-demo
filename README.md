# EA-Apokedro — Live Demo

A one-command demonstration of the Empirical-Agreement Apokedro index, extending
Papangelou, Christodoulou & Inglezakis (Blockchains 2025, 3, 4).

Running `demo.py` prints three results in order:

1. **Sanity** — with no data, the index reproduces the paper's 0.4375 exactly (it *extends*, not replaces).
2. **Compound** — the paper's assumed 0.5 agreement is really 0.835 → the index jumps ~42×.
3. **Proof** — a permutation test shows that alignment is Compound's *consensus culture*, not collusion.

Total run time: ~30 seconds.

---

## Files in this folder

| File | What it is |
|------|------------|
| `demo.py` | The demo. Run this. |
| `compound_delegates_active.jsonl` | 4,383 active Compound delegates (voting power) |
| `compound_votes.jsonl` | 23,769 individual on-chain votes |
| `requirements.txt` | The one dependency (numpy) |

---

## How to run it in VS Code (step by step)

**1. Install Python** (if you don't have it)
Download from https://python.org (3.9 or newer). During install on Windows, tick **"Add Python to PATH"**.

**2. Install VS Code** and the **Python extension**
Open VS Code → Extensions icon on the left (or Ctrl+Shift+X) → search **"Python"** (by Microsoft) → Install.

**3. Open this folder**
VS Code → File → Open Folder… → pick the folder that contains `demo.py`.

**4. Open a terminal inside VS Code**
Menu: Terminal → New Terminal (or Ctrl+`). It opens at the bottom, already in this folder.

**5. (Recommended) Create a virtual environment** so nothing else on your machine is touched:

```
python -m venv .venv
```
Then activate it:
- **Windows:** `.venv\Scripts\activate`
- **Mac/Linux:** `source .venv/bin/activate`

(If VS Code pops up "We noticed a new environment, select it?" → click Yes.)

**6. Install the dependency**

```
pip install -r requirements.txt
```

**7. Run the demo**

```
python demo.py
```

You'll see CHECK 1, CHECK 2, CHECK 3, and a SUMMARY print out. That's it.

> Tip for the live walkthrough: you can also just press the ▶ **Run** button
> in the top-right of VS Code while `demo.py` is open — it does the same thing.

---

## If something goes wrong

- **`python: command not found`** → try `python3` instead of `python` in every command.
- **`No module named numpy`** → you skipped step 6, or your virtual environment isn't active. Re-run `pip install -r requirements.txt`.
- **`FileNotFoundError: compound_votes.jsonl`** → you opened the wrong folder; make sure the terminal prompt shows the folder that contains the `.jsonl` files (`ls` on Mac/Linux or `dir` on Windows should list them).

---

## What to say while it runs

- CHECK 1: "First I prove it's a real extension — with no data it becomes your exact index, 0.4375."
- CHECK 2: "On real Compound data, your assumed 0.5 agreement is actually 0.835 — the index was understating alignment by 42×."
- CHECK 3: "But I test whether that's collusion or just consensus culture — and it's culture. The method can tell the difference."
