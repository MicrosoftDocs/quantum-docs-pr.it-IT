---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Operazione Carry
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843347"
---
# <a name="carry-operation"></a>Operazione Carry

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementa un controllo di porta reversibile. Dato un bit di trasporto codificato in qubit `carryIn` e due bit summand codificati in `summand1` e `summand2` , calcola l'operatore XOR bit per bit di e `carryIn` `summand1` `summand2` in qubit `summand2` e il riporto è XORed a qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Input

### <a name="carryin--qubit"></a>carryin: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Eseguire il qubit.


### <a name="summand1--qubit"></a>sommando1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo summand qubit.


### <a name="summand2--qubit"></a>sommando2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Il secondo summand qubit, viene sostituito con il bit più basso della somma di `summand1` e `summand2` .


### <a name="carryout--qubit"></a>esecuzione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Il qubit di esecuzione, sarà XORed con il bit più alto della somma.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

