# GateforQDs
This is a note for constructing quantum gate in quantum dots system

# Hamiltonian Terms in the Computational Basis

## Computational Basis
For 3 quantum dots, each with 1 electron, the basis is:
- \( |000\rangle = |\uparrow \uparrow \uparrow\rangle \), ..., \( |111\rangle = |\downarrow \downarrow \downarrow\rangle \)

## Tunneling Term
\[ H_t = -t (c_{1\sigma}^\dagger c_{2\sigma} + c_{2\sigma}^\dagger c_{1\sigma} + c_{2\sigma}^\dagger c_{3\sigma} + c_{3\sigma}^\dagger c_{2\sigma}) \]
- On \( |010\rangle \):
  - \( -t c_{2\uparrow}^\dagger c_{1\uparrow} |010\rangle = -t |\downarrow, \uparrow \downarrow, \uparrow\rangle \) (dot 1 empty, dot 2 doubly occupied)
  - Other terms zero or similar charge-excited states.
- Couples to states outside the subspace.

## On-Site Energy Term
\[ H_\varepsilon = \sum_i \varepsilon_i (n_{i\uparrow} + n_{i\downarrow}) \]
- \( H_\varepsilon | \sigma_1 \sigma_2 \sigma_3 \rangle = (\varepsilon_1 + \varepsilon_2 + \varepsilon_3) | \sigma_1 \sigma_2 \sigma_3 \rangle \)
- Constant shift (identity operation).

## Coulomb Term
\[ H_U = U \sum_i n_{i\uparrow} n_{i\downarrow} \]
- \( H_U | \sigma_1 \sigma_2 \sigma_3 \rangle = 0 \) (no double occupancy).

## Zeeman Term
\[ H_Z = \sum_i \frac{1}{2} g_i \mu_B B_z \hbar (n_{i\uparrow} - n_{i\downarrow}) \]
- \( H_Z |000\rangle = \frac{3}{2} g \mu_B B_z \hbar |000\rangle \)
- \( H_Z |111\rangle = -\frac{3}{2} g \mu_B B_z \hbar |111\rangle \)
- Diagonal in the basis, enables phase control.

## Gate Construction
- Use \( U = e^{-i H t / \hbar} \) over the full 20-state space.
- Optimize \( t, \varepsilon_i, B_z \) numerically to approximate the desired 8x8 unitary (e.g., Toffoli) while minimizing leakage.
