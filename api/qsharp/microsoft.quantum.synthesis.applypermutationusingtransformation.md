---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: Operazione ApplyPermutationUsingTransformation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858988"
---
# <a name="applypermutationusingtransformation-operation"></a>Operazione ApplyPermutationUsingTransformation

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permuta le ampiezze in uno stato quantum data una permutazione utilizzando la sintesi basata sulla trasformazione.

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

Questa procedura implementa l'approccio di sintesi basata sulla trasformazione unidirezionale.  L'input è una permutazione $ \Pi $ oltre $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, che rappresenta una $N funzione booleana reversibile $-variable.
L'algoritmo esegue in modo iterativo i passaggi seguenti:

1. Trova il più piccolo $x $ in modo che $x \ne \Pi (x) = y $.
2. Trovare le operazioni Toffoli a più controlli, che sono state applicate agli output make $ \Pi (x) = x $ e non cambiano $ \Pi (x ') $ per tutti $x ' < x $

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
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a>Riferimenti

- [*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, pp. 318-323, 2003](https://doi.org/10.1145/775832.775915)
- [*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, pp. 307-321, 2016](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Synthesis. ApplyPermutationUsingDecomposition](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)