---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Operazione per la determinazione della somma
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: e659c77a876e10df75f28ca1798fb0335e1bfb22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847761"
---
# <a name="sum-operation"></a>Operazione per la determinazione della somma

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa un controllo Sum reversibile. Dato un bit di trasporto codificato in qubit `carryIn` e due bit summand codificati in `summand1` e `summand2` , calcola l'XOR bit per bit di `carryIn` `summand1` e `summand2` nel qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit is Adj + Ctl
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