---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operazione GreaterThan
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721134"
---
# <a name="greaterthan-operation"></a>Operazione GreaterThan

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Applica un confronto maggiore di tra due numeri interi codificati in registri qubit, capovolgendo un qubit di destinazione in base al risultato del confronto.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Esegue un confronto rigoroso tra due numeri interi $x $ e $y $, codificati in qubit registra XS e YS. Se $x > y $, il risultato qubit verrà capovolto, in caso contrario il risultato qubit manterrà il proprio stato.

## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codifica del primo Integer $x $.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit-registrazione che codifica il secondo Integer $y $.


### <a name="result--qubit"></a>risultato: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Singolo qubit che verrà capovolto se $x > y $.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Usa il trucco che $x-y = (x ' + y)' $, dove ' denota il complemento a uno.

## <a name="references"></a>Riferimenti

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas haener, Martin Roetteler, Krysta M. Svore: "factoring using 2n + 2 qubits with Toffoli Modular based Moltiplication", 2016 https://arxiv.org/abs/1611.07995