---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: Operazione RippleCarryAdderNoCarryTTK
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 59451b4f5c992f900a27139332059af7427b9b93
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719583"
---
# <a name="ripplecarryaddernocarryttk-operation"></a>Operazione RippleCarryAdderNoCarryTTK

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Ripple sul posto reversibile: porta l'aggiunta di due numeri interi senza eseguire l'esecuzione.

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

Dato che due interi $n $ bit codificati nei registri LittleEndian `xs` e `ys` , l'operazione calcola la somma dei due valori interi modulo $2 ^ n $, dove $n $ è la dimensione in bit degli input `xs` e `ys` . Non calcola il bit di esecuzione.

## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit registra la codifica del primo Integer summand.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Il registro LittleEndian qubit che codifica il secondo valore integer summand, viene modificato in modo da mantenere i bit $n $ meno significativi della somma.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione ha la stessa funzionalità di RippleCarryAdderTTK, ma non restituisce il bit di riporto.

## <a name="references"></a>Riferimenti

- Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum addition Circuits and unbounded fan-out", Quantum Information and Computing, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530