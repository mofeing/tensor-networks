---
title: "Origins: DMRG"
description: ""
keywords:
weight: 1
katex: true
---

# Origins: DMRG

The **Density Matrix Renormalization Group** algorithm is a numerical method introduced in _"Density-matrix algorithms for quantum renormalization groups"_ by Stephen White.

## Infinite DMRG


{{<figure src="spin-chain.svg" class="center">}}

### Step 1: Superblock Hamiltonian

{{<katex display>}}
H = - J \sum_{j=1}^N \sigma_j \sigma_{j+1} - h \sum_{j=1}^N \sigma_j
{{</katex>}}

{{<figure src="dmrg-sites.svg" class="center">}}

{{<figure src="dmrg-sites+superblock.svg" class="center">}}

### Step 2: Select target state

{{<katex display>}}
H_{BB} = Q \Lambda Q^\dagger
{{</katex>}}

Usually, the desired state is the _ground state_ which corresponds to eigenstate with the lowest eigenvalue.
{{<katex display>}}
\Psi = Q(\min \lambda)
{{</katex>}}

{{<katex display>}}
H_{BB} | \Psi \rangle = \lambda_0 |\Psi\rangle \quad \lambda_0 = \min(\lambda)
{{</katex>}}

We could update {{<katex>}}H_B{{</katex>}} to be the outer product of the

{{<katex display>}}
\tilde\Psi_{ij} = \sum_\alpha \Psi_{ij\alpha\alpha}
{{</katex>}}

{{<katex display>}}
[H_B]_{ij;i^\prime j^\prime} = | \tilde\Psi_{ij} \rangle \langle \tilde\Psi_{i^\prime j^\prime} |
{{</katex>}}

### Step 3: Low-rank representation of the reduced density matrix
Instead, the DMRG uses the reduced density matrix to find a better representation of {{<katex>}}H_B{{</katex>}}. The reduced density matrix is a much more appropiate tool to deal with the representation of subsystems and mixed quantum states.

{{<katex display>}}
\rho_{i j;i^\prime j^\prime} = \sum_{k,w} |\Psi_{i,j,k,w}\rangle \langle \Psi_{i^\prime,j^\prime,k,w} |
{{</katex>}}

We want to find the minimal ensemble of states that better approximates the reduced density matrix {{<katex>}}\rho{{</katex>}}.

{{<katex display>}}
\rho = U \Lambda U^\dagger
{{</katex>}}

<!-- As the density matrix is always positive-definite, all its eigenvalues are positive and -->
Let {{<katex>}}\lambda_1, \dots, \lambda_m{{</katex>}} be the {{<katex>}}m{{</katex>}} highest eigenvalues of {{<katex>}}\rho{{</katex>}}, then the new {{<katex>}}H_B{{</katex>}} is the matrix formed by the associated eigenvectors.

{{<katex display>}}
O = U_{ij;\alpha} \qquad 1 \leq \alpha \leq m
{{</katex>}}

{{<katex display>}}
\rho \approx O \tilde\Lambda O^\dagger
{{</katex>}}

{{<katex display>}}
H_B = O H_B^\prime O^\dagger
{{</katex>}}


## Finite DMRG

### Step 1:

### Step 2:

{{<figure src="dmrg-finite-sites.svg" class="center">}}
