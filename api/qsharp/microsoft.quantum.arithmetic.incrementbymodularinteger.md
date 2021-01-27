---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: Operazione IncrementByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846593"
---
# <a name="incrementbymodularinteger-operation"></a>Operazione IncrementByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue un incremento modulare di un registro qubit da una costante Integer.

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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