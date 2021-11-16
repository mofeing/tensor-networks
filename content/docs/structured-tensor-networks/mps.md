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

The **Density Matrix Renormalization Group** algorithm...

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

#### Step 2:

#### Step 3: Reduced density matrix

{{<katex display>}}
\rho_{i j;i^\prime j^\prime} = \sum_{k,w} \psi_{i,j,k,w} \psi^*_{i^\prime,j^\prime,k,w}
{{</katex>}}

### Finite DMRG