---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722956"
---
# <a name="quantumrom-function"></a>QuantumROM (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata.

Dato un elenco di $N $ coefficienti $ \ alpha_j $, restituisce un Unity $U $ che usa la tecnica Quantum-ROM per preparare un'approssimazione $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ della purificazione della matrice di densità $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $. In questa approssimazione, l'errore $ \epsilon $ è tale che $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ e $ \| \tilde\rho-\rho \| \Le \epsilon $. In altre parole, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ KET {0} ^ {m} = \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\Text{Garbage} _J}.
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Input

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Errore di destinazione $ \epsilon $.


### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di $N $ coefficienti che specificano la probabilità di Stati di base.
I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a>Output:[((int, int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)),[Double](xref:microsoft.quantum.lang-ref.double)[, (](xref:microsoft.quantum.lang-ref.int)[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL)

## <a name="first-parameter"></a>Primo parametro

Tupla `(x,(y,z))` `x = y + z` in cui è il numero totale di qubits allocato, `y` è il numero di qubits per il `LittleEndian` registro e `z` è il numero di Garbage qubits.

## <a name="second-parameter"></a>Secondo parametro

Una regola $ \ sum_j | \ alpha_j | $ della matrice coefficiente.

## <a name="third-parameter"></a>Terzo parametro

Unitario $U $.

## <a name="references"></a>Riferimenti

- Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662