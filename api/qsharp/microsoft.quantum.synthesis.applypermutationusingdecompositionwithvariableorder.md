---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: Operazione ApplyPermutationUsingDecompositionWithVariableOrder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725294"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a>Operazione ApplyPermutationUsingDecompositionWithVariableOrder

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


Permuta le ampiezze in uno stato quantum data una permutazione usando la sintesi basata sulla scomposizione.

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

Questa operazione è una versione più generale di @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in cui è possibile specificare l'ordine delle variabili. Un ordine variabile diverso modifica la sequenza di scomposizione e le tabelle di verità usate per le attività di controllo @"microsoft.quantum.intrinsic.x" .  Pertanto, la modifica dell'ordine delle variabili cambia il numero di controlli generali utilizzati per realizzare la permutazione.

## <a name="input"></a>Input

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutazione di $2 ^ n $ elementi a partire da 0.


### <a name="variableorder--int"></a>variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutazione di $n $ Elements a partire da 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Elenco di $n $ qubits a cui viene applicata la permutazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)