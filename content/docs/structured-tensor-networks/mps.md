---
title: "Matrix Product States (MPS)"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
katex: true
---

# Matrix Product States

## Origins: DMRG

The **Density Matrix Renormalization Group** algorithm is a numerical method developed by Stephen White

### Infinite DMRG

{{<center>}}
{{<figure src="/tensor-networks/docs/structured-tensor-networks/spin-chain.svg">}}
{{</center>}}

#### Step 1: Superblock Hamiltonian

{{<katex display>}}
H = - J \sum_{j=1}^N \sigma_j \sigma_{j+1} - h \sum_{j=1}^N \sigma_j
{{</katex>}}

{{<center>}}
{{<figure src="/tensor-networks/docs/structured-tensor-networks/dmrg-sites.svg">}}
{{</center>}}

{{<center>}}
{{<figure src="/tensor-networks/docs/structured-tensor-networks/dmrg-sites+superblock.svg" style="text-align: center">}}
{{</center>}}

#### Step 2: Select target state

{{<katex display>}}
H_{BB} = Q \Lambda Q^\dagger
{{</katex>}}

Usually, the desired state is the _ground state_ which corresponds to eigenstate with the lowest eigenvalue.
{{<katex display>}}
\Psi = Q(\min \lambda)
{{</katex>}}

#### Step 3: Reduced density matrix

{{<katex display>}}
\rho_{i j;i^\prime j^\prime} = \sum_{k,w} \Psi_{i,j,k,w} \Psi^*_{i^\prime,j^\prime,k,w}
{{</katex>}}

{{<katex display>}}
\tilde\Psi_{ij}= \text{Tr}_{k,w}[\Psi_{ijkw}] % \to \rho = | \tilde\Psi \rangle \langle \tilde\Psi |
{{</katex>}}

{{<katex display>}}
\rho_{i j;i^\prime j^\prime} = \sum_{k,w} (\text{Tr}_{ij}[\Psi_{ijkw}])^2 |\tilde\Psi_{ij} \rangle \langle \tilde\Psi_{ij} |
{{</katex>}}

#### Step 4: Low-rank representation of the reduced density matrix

{{<katex display>}}
\rho = U \Lambda U^\dagger
{{</katex>}}

{{<katex display>}}
\Lambda_{ij} = \lambda_i \delta_{ij}
{{</katex>}}


{{<katex display>}}
\Lambda_{ij} = \begin{cases}
\lambda_i &\text{if } i = j \\
0 &\text{otherwise}
\end{cases}
{{</katex>}}

{{<katex display>}}
\tilde\Lambda_{ij} = \begin{cases}
\lambda_i &\text{if } i = j \land i \leq m \\
0 &\text{otherwise}
\end{cases}
{{</katex>}}

{{<katex display>}}
H_B = \tilde{U}_{ij} = U_{ij}
{{</katex>}}

### Finite DMRG