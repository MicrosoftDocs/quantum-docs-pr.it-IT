---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operazione IncrementByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 271033b32b0de6cf600dca82126dab19c2bb4f5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721098"
---
# <a name="incrementbymodularinteger-operation"></a>Operazione IncrementByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Esegue un incremento modulare di un registro qubit da una costante Integer.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

È ora indicata `increment` da $a $, `modulus` da $N $ e Integer codificati in `target` da $y $.
L'operazione esegue quindi la trasformazione seguente: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} integer sono codificati in formato little-endian.

## <a name="input"></a>Input

### <a name="increment--int"></a>incremento: [int](xref:microsoft.quantum.lang-ref.int)

Incremento Integer $a $ da aggiungere a $y $.


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Integer $N $ che mods $y + a $.


### <a name="target--littleendian"></a>destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Integer $y $ nel `LittleEndian` formato `increment` a cui $a $ viene aggiunto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Presuppone che il valore iniziale di target sia minore di $N $ e che l'incremento $a $ sia minore di $N $.
Si noti che <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implementa la stessa operazione in `PhaseLittleEndian` base a.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. IncrementPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)