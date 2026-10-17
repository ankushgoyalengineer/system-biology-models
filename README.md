# Systems Biology Models

Four small computational models in Python. Each is checked against an analytical solution or independent software rather than just plotted. Folder 04 is an independent reproduction of a published model.

| Folder | Question | Result |
| --- | --- | --- |
| `01-predator-prey` | How do predator–prey dynamics change with and without resource limits? | Validated convergence to carrying capacity; compared oscillating and stabilising behaviour |
| `02-Michaelis-Menten` | Where does the Michaelis–Menten approximation hold? | Agrees within 1.4% when substrate greatly exceeds enzyme; fails by two orders of magnitude when enzyme is in excess |
| `03-gene-expression` | How does repression steepness shape negative-feedback dynamics? | Steady states match analytical solutions; overshoot rises from 1.0 to 3.46-fold across Hill coefficients 1–10 |
| `04-gene_network_HSCs` | Can a published Boolean model of blood stem cell fate be reproduced from its rules alone? | Yes, exactly, with two issues found in the paper (below) |

## 04: Reproduction of a blood stem cell fate model

Reproduces the 21-gene regulatory network of Herrera et al. (2024), *npj Systems Biology and Applications* [add DOI link], from the published rules. Independent work, not affiliated with the authors.

- Searched all 2,097,152 network states and recovered the model's 13 stable cell states and 18 attractors.
- All 18 basin sizes match the authors' own software (BoolNet in R), state for state. Published cell-fate percentages and six mutant simulations also match.
- 14 automated tests (`pytest`).

### Findings

1. **Figure error.** Two progenitor states in [Figure X: confirm number] are drawn inconsistently with the model's rules. Confirmed by running the authors' rules file through BoolNet.
2. **Comparison inconsistency.** The paper compares wild-type and mutant results in a way that distorts fold changes by about 9%. Two published conclusions depend on how cyclic attractors are treated.

## How to run

[Confirm these match the repo before publishing.]

```bash
git clone https://github.com/ankushgoyalengineer/systems-bio-lab.git
cd systems-bio-lab
pip install -r requirements.txt
pytest
```

Python [version]. The BoolNet cross-check needs R with the `BoolNet` package.

## Data and parameters

Models use published rules and literature parameters only (E. coli parameters in folder 03: [add citation]). No proprietary or unpublished data.
