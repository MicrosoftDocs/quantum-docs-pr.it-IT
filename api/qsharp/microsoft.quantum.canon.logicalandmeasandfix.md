---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operazione LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715924"
---
# <a name="logicalandmeasandfix-operation"></a>Operazione LogicalANDMeasAndFix

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Calcola l'operatore AND logico di più qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Input di qubits per l'input multiplo e il controllo.


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit in cui viene scritto l'output di e. Si presuppone che si avvii sempre nello stato $ \ket {0} $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Quando `ctrlRegister` ha esattamente $2 $ qubits, equivale all' `CCNOT` operazione ma alla fase con una fase $e ^ {i \ PI/2} $ su $ \ket {001} $ e $-e ^ {i \ PI/2} $ su $ \ket {101} $ e $ \ket {011} $.
Il contiguo è anche l'approccio di misura e correzione che è l'inverso dell'operazione originale solo in casi speciali (vedere i riferimenti), ma usa un numero inferiore di T-Gates.

## <a name="references"></a>Riferimenti

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)