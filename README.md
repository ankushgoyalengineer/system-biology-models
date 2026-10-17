# System Biology Models

Three small computational models in Python. Three small computational models in Python, each checked against an analytical solution or a convergence test rather than just plotted.

## Projects

| Folder | Question | Result |
| --- | --- | --- |
| `01-predator-prey` | How do predator–prey dynamics change with and without resource limits? | Validated convergence to carrying capacity; compared oscillating and stabilising behaviour |
| `02-Michaelis-Menten` | Where does the Michaelis–Menten approximation hold? | Agrees within 1.4% when substrate greatly exceeds enzyme; fails by two orders of magnitude when enzyme is in excess |
| `03-gene-expression` | How does repression steepness shape negative-feedback dynamics? | Steady states match analytical solutions; overshoot rises from 1.0 to 3.46-fold across Hill coefficients 1–10 |

## What each model does

**Population dynamics (`01-predator-prey`).** Simulates predator–prey systems with and without resource limits. Checks convergence to the carrying capacity and compares oscillating with stabilising behaviour.

**Enzyme kinetics (`02-Michaelis-Menten`).** A mass-action model of enzyme–substrate binding, used to test where the Michaelis–Menten approximation holds. The two agree within 1.4% when substrate greatly exceeds enzyme. When enzyme is in excess, the approximation fails by two orders of magnitude.

**Gene regulation with negative feedback (`03-gene-expression`).** Models mRNA and protein dynamics using literature-based *E. coli* parameters. Steady states are validated against analytical solutions, and numerical step-size checks confirm the simulations are stable. The model shows that steeper repression produces larger overshoot, from 1.0-fold to 3.46-fold across Hill coefficients 1 to 10.

## Related project

A fourth project, an independent reproduction of a published Boolean model of blood stem cell fate, lives in its own repository: [hsc-boolean-network-reproduction](https://github.com/ankushgoyalengineer/hsc-boolean-network-reproduction).

## Setup

You need Python 3 with NumPy, SciPy, Matplotlib and Jupyter.

```bash
git clone https://github.com/ankushgoyalengineer/system-biology-models.git
cd system-biology-models
pip install numpy scipy matplotlib jupyter
```

Each folder is self-contained. Open its notebook and choose Run All, or run its script with `python <file>.py`.

## Data and parameters

The models use published literature values only (*E. coli* parameters in folder 03). No proprietary or unpublished data is used.
