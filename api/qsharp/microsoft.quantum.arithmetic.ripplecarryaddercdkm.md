---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: Operazione RippleCarryAdderCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: 6dcb5193c5d1d059682a79e63e6562aabff7539d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719610"
---
# <a name="ripplecarryaddercdkm-operation"></a>Operazione RippleCarryAdderCDKM

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Ripple sul posto reversibile: porta l'aggiunta di due numeri interi.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Dati due $n interi a $ bit codificati nei registri LittleEndian `xs` e e `ys` un qubit Carry, l'operazione calcola la somma dei due numeri interi in cui i $n bit meno significativi del risultato sono contenuti in `ys` e il bit di esecuzione è XORed a qubit `carry` .

## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codifica del primo Integer summand.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registro codifica il secondo Integer summand, viene modificato in modo da mantenere i bit meno significativi della somma.


### <a name="carry--qubit"></a>porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Carry qubit, is XORed con il bit più significativo della somma.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione ha la stessa funzionalità di RippleCarryAdderD, ma usa solo un qubit ausiliario invece di $n $.

## <a name="references"></a>Riferimenti

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1