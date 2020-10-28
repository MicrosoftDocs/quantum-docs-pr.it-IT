---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operazione per la determinazione della somma
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719502"
---
# <a name="sum-operation"></a>Operazione per la determinazione della somma

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Implementa un controllo Sum reversibile. Dato un bit di trasporto codificato in qubit `carryIn` e due bit summand codificati in `summand1` e `summand2` , calcola l'XOR bit per bit di `carryIn` `summand1` e `summand2` nel qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="carryin--qubit"></a>carryin: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Eseguire il qubit.


### <a name="summand1--qubit"></a>sommando1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo summand qubit.


### <a name="summand2--qubit"></a>sommando2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Il secondo summand qubit, viene sostituito con il bit più basso della somma di `summand1` e `summand2` .



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

A differenza dell' `Carry` operazione, questo non calcola il bit di trascinamento.