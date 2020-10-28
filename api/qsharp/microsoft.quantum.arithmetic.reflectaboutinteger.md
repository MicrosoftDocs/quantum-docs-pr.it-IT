---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operazione ReflectAboutInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719715"
---
# <a name="reflectaboutinteger-operation"></a>Operazione ReflectAboutInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Riflette un registro Quantum su un valore integer classico specificato.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

Dato un registro Quantum inizialmente nello stato $ \ sum_i \ alpha_i \ket{i} $, dove ogni $ \ket{i} $ è uno stato di base che rappresenta un numero intero $i $, riflette lo stato del registro sullo stato di base per un dato Integer $ \ket{j} $, $ $ \ sum_i (-1) ^ {\ delta_ {IJ}} \ alpha_i \ket{i} $ $

## <a name="input"></a>Input

### <a name="index--int"></a>Indice: [int](xref:microsoft.quantum.lang-ref.int)

Integer classico che indicizza lo stato di base su cui riflettere.


### <a name="reg--littleendian"></a>reg: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)





## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Questa operazione viene implementata sul posto, senza allocazione esplicita di altri qubits ausiliari.