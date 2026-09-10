# AI Bootcamp — Foundations of AI

Repository containts the course materials of the AI Bootcamp - Foundations of AI, one week course held by [LARES](https://www.lares.fer.hr/lares), [Faculty of Electrical Engineering and Computing](https://www.fer.unizg.hr/en?), University of Zagreb.

Everything runs in **Google Colab**, in your browser. Nothing to install, no
GPU needed, no credit card. Data and notebooks are fetched automatically from
this repository.

---

## At the beginning of the course (cca. 10 minutes)

> **Use a personal Google account (`@gmail.com`), not a corporate one.**
> Managed Google Workspace accounts frequently have Colab or Google AI Studio
> blocked by an administrator, and that is not something we can usually fix in the duration of the course.

### 1. Check that Colab works

Open [**0_Test**](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/0_Test.ipynb),
sign in if prompted, and run the **first cell**. If it prints `23; 3.1415`,
everything works and you can close the tab.

**Do not request a GPU runtime.** The entire course runs on CPU. Free GPU quota
is limited and shared, and spending it changes nothing except that it will not
be there when we might actually need it for code execution.

### 2. Create a Gemini API key

Needed on day 4, for the language model and agent sessions. Create it now so
that any account problem surfaces while there is still time. Free, no payment
method required.

1. Open [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
2. Click **Create API key** and copy the result somewhere safe
3. If a project picker appears, choose any project or create a new one — it
   does not matter which

**Everyone needs their own key.** We do not share one, because the daily and
per-minute quotas are counted per account.

### 3. Store the key in Colab

Never paste an API key into a notebook cell. Colab has a dedicated place for
secrets.

1. In Colab, click the **key icon** in the left sidebar (Secrets)
2. **Add new secret** — name `GOOGLE_API_KEY`, value = your key
3. Turn on **Notebook access**

The notebooks read it from there. It never appears in the code, and it never
travels to GitHub with a saved copy.

**If any of the three steps fails, tell us as soon as possible.** 
---

## Notebooks

Every link opens the notebook directly in Colab.

### Day 1 - setup, data processing and initial model
| | Notebook | |
|---|---|---|
| 0 | [0_Test](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/0_Test.ipynb) | Test notebook, checking if everything works, with some Python basics. |
| 1 | [1_EDA_data_processing](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/1_EDA_data_processing.ipynb) | Data processing basics, regression and classification examples and differences. |

### Day 2 - supervised learning (regression and classification), unsupervised learning
| | Notebook | |
|---|---|---|
| 2a | [2a_Classification_Iris](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/2a_Classification_Iris.ipynb) |
| 2b | [2b_Regression_House_prices](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/2b_Regression_House_prices.ipynb) |
| 3a | [3a_Clustering_Mall_customers](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/3a_Clustering_Mall_customers.ipynb) |
| 3b | [3b_Clustering_Wheat](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/3b_Clustering_Wheat.ipynb) |
| 3c | [3c_Unsupervised_Iris](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/3c_Unsupervised_Iris.ipynb) |

### Day 3 — ensembles, hyperparameters tuning and interpretability

| | Notebook | |
|---|---|---|
| 5 | [5_Cross-Validation](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/5_Cross-Validation.ipynb) |
| 6 | [6_Ensemble_Learning_House_Prices](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/6_Ensemble_Learning_House_Prices.ipynb) |
| 7 | [7_Hyperparameters_Search](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/7_Hyperparameters_Search.ipynb) |

### Day 4 — ANN, generative AI and agents

Notebooks 9, 10 and 11 require the API key from step 2.

| | Notebook | |
|---|---|---|
| 4a | [4a_NN_House_prices](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/4a_NN_House_prices.ipynb) |
| 4b | [4b_NN_Iris](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/4b_NN_Iris.ipynb) |
| 4c | [4c_NN_Fashion_MNIST](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/4c_NN_Fashion_MNIST.ipynb) |
| 8 | [8_YOLO_object_detection](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/8_YOLO_object_detection.ipynb) | Object detection with a narrow model. Runs on CPU; no API key needed. |
| 9 | [9_LLM_first_call](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/9_LLM_first_call.ipynb) | The raw HTTP call, system prompts, temperature, structured output, conversations, tokenization and cost. |
| 10 | [10_Grounding_own_PDF](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/10_Grounding_own_PDF.ipynb) | Retrieval over a document of our own, and what happens when that document contains an instruction aimed at the model. |
| 11 | [11_Workflow_vs_Agent](https://colab.research.google.com/github/unizg-fer-lares/ai_bootcamp_foundations/blob/main/notebooks/11_Workflow_vs_Agent.ipynb) | The same task solved as a fixed pipeline and as an agent, and the case where only one of them works. |

Notebooks 9–11 import [`notebooks/lares_llm.py`](notebooks/lares_llm.py) — a
small shared module holding retries, token accounting and the model fallback
chain. Worth reading; it is about two hundred lines.

### Day 5 — private Kaggle competition

| | Notebook | |
|---|---|---|

---

## While you work

**Your work is not saved automatically.** A Colab link opens a *copy* of the
notebook. If you close the tab without saving, your edits are gone.

- **File → Save a copy in Drive** — keeps it in your Google Drive
- **File → Download → Download .ipynb** — keeps it locally and uses no Drive
  space, useful if your Drive is full

**Everything can be re-run from the top.** If the connection drops or the
session is recycled, run the first cell again. Nothing depends on state you
cannot rebuild, so **Runtime → Restart and run all** is always safe.

**The first cell is called SETUP and always comes first.** It clones this
repository into the session and moves into `notebooks/`, which is what makes
every relative path work. Safe to run more than once, and it works unchanged
if you run the notebooks locally.

**Working locally instead:** **Code → Download ZIP**, then `jupyter lab` from
inside `notebooks/`. The SETUP cell detects that it is not in Colab and does
nothing. You will need to install the packages the notebooks import, and set
`GOOGLE_API_KEY` as an environment variable rather than as a Colab secret.

---

## If something goes wrong

### Accounts and access

| Symptom | Likely cause |
|---|---|
| Colab asks for unusual permissions, or will not open | corporate account with restrictions — use a personal one |
| "Google AI Studio is not available", or no **Create API key** button | same cause, or the account's age has not been verified |

### Errors from the model

| Error | What it means |
|---|---|
| **HTTP 429** | a rate limit; the code retries on its own, so wait. The message says *which* limit was hit — if it mentions *per day*, your daily quota is gone and the notebook moves to the fallback model by itself |
| **HTTP 503** | the model is overloaded on Google's side, nothing to do with your key; the code waits and then switches models |
| **HTTP 400** with a model name | model names change often — run the *"which models does this key actually have"* cell in notebook 9 to list the exact names your key accepts |
| **HTTP 403** | the key is invalid, or AI Studio is blocked on that account |
| answer stops mid-sentence | the output token budget ran out; raise `max_tokens` — the notebooks flag this explicitly when it happens |

### Errors from Colab

| Symptom | Fix |
|---|---|
| "Restart runtime" after installing a package | restart, then **Runtime → Restart and run all**; the SETUP cell survives it |
| `FileNotFoundError` on a path starting with `../data/` | the SETUP cell has not been run in this session |
| `ModuleNotFoundError` | an installation cell was skipped; they are at the top of each notebook |
| everything disappeared | the session was recycled after inactivity — re-run from the first cell |

---

## Layout

```
notebooks/    notebooks, plus lares_llm.py
data/         datasets, images and documents — fetched automatically
docs/         setup guide (LaTeX source and PDF)
```

The material stays available after the course.
