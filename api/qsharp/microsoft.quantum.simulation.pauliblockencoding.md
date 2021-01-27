---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848012"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crea un Unity di codifica a blocchi per un'Hamiltoniana.

Hamiltoniana $H = \ sum_ {j} \ alpha_j P_j $ è descritto da una somma dei termini di Pauli $P _j $, ognuno con un coefficiente reale $ \ alpha_j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Input

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Oggetto `GeneratorSystem` che descrive $H $ come somma dei termini di Pauli



## <a name="output--doubleblockencodingreflection"></a>Output: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Primo parametro

La regola uno dei coefficienti $ \Alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Secondo parametro

`BlockEncodingReflection`Unitario $U $ dell'hamiltoniana $H $. Poiché questo unitario soddisfa $U ^ 2 = I $, è anche una reflection.

## <a name="remarks"></a>Commenti

Questa operazione viene ottenuta preparando e disinstallando lo stato $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ e costruendo un Unity controllato da moltiplicato <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> e <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .