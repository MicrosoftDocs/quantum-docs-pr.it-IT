---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Operazione ReflectAboutInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: 4d451c4e8e002f86c892b394f58ea2d7e9dd6a48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842984"
---
# <a name="reflectaboutinteger-operation"></a>Operazione ReflectAboutInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Riflette un registro Quantum su un valore integer classico specificato.

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
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