# conjugacy-separability

Conjugacy separability for free and orientable surface groups.

## Goals

Formalise conjugacy separability for finitely generated free groups and for fundamental groups of compact orientable surfaces of genus at least two, together with its interpretation in their profinite completions.

Develop the normaliser/centraliser consequences needed to control profinite conjugates of discrete subgroups, including the ingredients used in IUT I, Theorem 2.6 and Corollary 2.8.

Mathlib already provides free groups, residual finiteness, subgroup normalisers, and categorical profinite completion; this project builds on that base.

## Established sources

* P. F. Stebe, *A residual property of certain groups* (1970).
* P. F. Stebe, *Conjugacy separability of certain Fuchsian groups* (1972).
* Ribes–Zalesskii, *Profinite Groups*.
* Stillwell, *Classical Topology and Combinatorial Group Theory*.

## Related repositories

A foundational input to `tempered-fundamental-groups`.

## Layout

Lean 4 project pinned to `leanprover/lean4:v4.32.0` with Mathlib at `v4.32.0`.
Library sources live under `ConjugacySeparability/`, and every file must be imported from
the root module `ConjugacySeparability.lean`.

```bash
lake exe cache get                       # fetch the Mathlib build cache
lake build                               # build the library
lake exe mk_all --lib ConjugacySeparability --git   # regenerate the root module after adding files
```

## Validation

`.orchestra/` tells the agent harness how to prepare the environment and how to
check that a change is complete:

* `before.sh` warms the Mathlib build cache before work starts.
* `validation.sh` checks the worktree is clean, that every `.lean` file is
  imported (`mk_all --check`), and that everything builds with warnings as
  errors (`lake build --wfail`).

Run it locally with `bash .orchestra/validation.sh`.

## Tracker

Work is tracked in taxis: [#14](https://taxis.lana.merten.dev/issues/14)
