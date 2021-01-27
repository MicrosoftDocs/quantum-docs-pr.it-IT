---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854288"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData (funzione)

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un'operazione che prepara una purificazione di uno stato misto specificato, correlata a un registro che rappresenta una raccolta di dati specificata.
Uno "stato misto purificato con dati" si riferisce allo stato del formato σi √ pi | i ⟩ | XI ⟩ | garbagei ⟩, in cui ogni XI è un Bitstring di codifica dei dati aggiuntivi associati al registro | i ⟩.

https://arxiv.org/pdf/1805.03662.pdf?page=15Per ulteriori informazioni, vedere.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Descrizione

Usa la tecnica Quantum ROM per rappresentare una matrice di densità specificata, restituendo tale rappresentazione come operazione di preparazione dello stato.

In particolare, in base a un elenco di $N $ coefficienti $ \ alpha_j $ e a un Bitstring $ \vec{x}_j $ associato a ogni coefficiente, questa funzione restituisce un'operazione che usa la tecnica Quantum ROM per preparare un'approssimazione $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {n-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ dello stato misto $ $ \begin{align} \rho = \sum_{j = 0} ^ {n-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $ dove ogni $p _j $ è un'approssimazione al coefficiente specificato $ \ alpha_j $ in modo tale che $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ per ogni $j $.

Quando viene passato un registro di indice e un registro di Garbage qubits, inizialmente nello stato $ \ket {0} \ket{00\cdots 0}, l'operazione restituita prepara entrambi i registri per la purificazione di $ \tilde \rho $, $ $ \begin{align} \ Sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $, in modo che la reimpostazione e la deallocazione del registro di Garbage Collection comportino la preparazione desiderata nell'errore di destinazione $ \epsilon $.

## <a name="input"></a>Input

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Errore di destinazione $ \epsilon $.


### <a name="coefficients--doublebool"></a>coefficienti: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Matrice di $N $ coefficienti che specificano la probabilità degli Stati di base, insieme al Bitstring $ \vec{x} _j $ associato a ogni coefficiente.
I numeri negativi $-\ alpha_j $ verranno considerati positivi $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Output: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operazione che prepara $ \tilde \rho $ come purificazione su un indice misto e un registro di Garbage Collection.

## <a name="remarks"></a>Commenti

I coefficienti forniti a questa operazione vengono normalizzati secondo la norma 1, in modo che i coefficienti vengano sempre considerati per descrivere una distribuzione di probabilità categorica valida.

## <a name="references"></a>Riferimenti

- Codifica di spettri elettronici nei circuiti Quantum con complessità T lineare Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pallido, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)