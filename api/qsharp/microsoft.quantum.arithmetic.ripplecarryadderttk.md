---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Operazione RippleCarryAdderTTK
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719562"
---
# <a name="ripplecarryadderttk-operation"></a>Operazione RippleCarryAdderTTK

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Ripple sul posto reversibile: porta l'aggiunta di due numeri interi.
Dati due $n interi a $ bit codificati nei registri LittleEndian `xs` e e `ys` un qubit Carry, l'operazione calcola la somma dei due numeri interi in cui i $n bit meno significativi del risultato sono contenuti in `ys` e il bit di esecuzione è XORed a qubit `carry` .

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codifica del primo Integer summand.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Il registro LittleEndian qubit che codifica il secondo valore integer summand, viene modificato in modo da mantenere i bit $n $ meno significativi della somma.


### <a name="carry--qubit"></a>porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Carry qubit, is XORed con il bit più significativo della somma.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione ha la stessa funzionalità di RippleCarryAdderD e RippleCarryAdderCDKM, ma non usa alcun ancilla qubits.

## <a name="references"></a>Riferimenti

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530