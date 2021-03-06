---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Operazione ApplyPermutationUsingDecomposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857402"
---
# <a name="applypermutationusingdecomposition-operation"></a>Operazione ApplyPermutationUsingDecomposition

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permuta le ampiezze in uno stato quantum data una permutazione usando la sintesi basata sulla scomposizione.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Questa procedura implementa l'approccio di sintesi basato sulla scomposizione.  L'input è una permutazione $ \Pi $ oltre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, che rappresenta una $N funzione booleana reversibile $-variable.
L'algoritmo esegue in modo iterativo i passaggi seguenti per ogni indice di variabile $i $:

1. Compute $ ((\ pi_l, \ pi_r), \Pi ') $ in modo che le immagini di $ \ pi_l $ e $ \ pi_r $ non modifichino i bit nei rispettivi elementi con indici diversi da $i $ e immagini di $ \Pi ' $ non cambiano bit $i $ nei relativi elementi.
2. Impostare $ \Pi \leftarrow \Pi ' $ e derivare le tabelle di verità da $ \ pi_l $ e $ \ pi_r $ in base a elementi che non sono punti fissi.

Dopo aver applicato questi passaggi per tutti gli indici delle variabili, la permutazione rimanente $ \Pi $ sarà l'identità e, in base agli indici e alle tabelle di verità raccolte, è possibile applicare le operazioni controllate dalla tabella di verità @"microsoft.quantum.intrinsic.x" usando l' @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operazione.

L'ordine della variabile è $0, \dots, n-$1.  Nell'operazione è possibile specificare un ordine di variabili personalizzato @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Input

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]

Permutazione di $2 ^ n $ elementi a partire da 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Elenco di $n $ qubits a cui viene applicata la permutazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Esempio

Per sintetizzare un' `SWAP` operazione:

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Riferimenti

- [*Alexis de vos*, *Yvan van Rentergem*, ADV. in Math. of comm. 2 (2), 2008, pp. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of simbologie computing 73 (2016), pp. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)