---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230022"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un'operazione che prepara una purificazione di uno stato misto specificato.
Uno "stato misto purificato" si riferisce agli Stati del formato | ψ ⟩ = σi √ pi | i ⟩ | garbagei ⟩ specificato da un vettore di coefficienti {pi}. Gli Stati di questo modulo possono essere ridotti a stati misti ρ ≔ pi | i ⟩ ⟨ | eseguendo la traccia sul Registro di Garbage Collection, ovvero uno stato misto diagonale nella base computazionale.

https://arxiv.org/pdf/1805.03662.pdf?page=15Per ulteriori informazioni, vedere.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Descrizione

Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata, restituendo tale rappresentazione come operazione di preparazione dello stato.

In particolare, dato un elenco di $N $ coefficienti $ \ alpha_j $, questa funzione restituisce un'operazione che usa la tecnica Quantum ROM per preparare un'approssimazione $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ dello stato misto $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ dove ogni $p _j $ è un'approssimazione al coefficiente specificato $ \ alpha_j $ tale che $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ per ogni $j $.

Quando viene passato un registro di indice e un registro di Garbage qubits, inizialmente nello stato $ \ket {0} \ket{00\cdots 0}, l'operazione restituita prepara entrambi i registri per la purificazione di $ \tilde \rho $, $ $ \begin{align} \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, in modo che la reimpostazione e la deallocazione del registro di Garbage Collection interagisce con la preparazione desiderata nell'errore $ \epsilon

## <a name="input"></a>Input

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Errore di destinazione $ \epsilon $.


### <a name="coefficients--double"></a>coefficienti: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di $N $ coefficienti che specificano la probabilità di Stati di base.
I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Output: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operazione che prepara $ \tilde \rho $ come purificazione su un indice misto e un registro di Garbage Collection.

## <a name="remarks"></a>Commenti

I coefficienti forniti a questa operazione vengono normalizzati secondo la norma 1, in modo che i coefficienti vengano sempre considerati per descrivere una distribuzione di probabilità categorica valida.

## <a name="references"></a>Riferimenti

- Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)