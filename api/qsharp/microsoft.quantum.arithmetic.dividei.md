---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: Operazione divide
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721218"
---
# <a name="dividei-operation"></a>Operazione divide

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Divide due interi quantici.

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

`xs` manterrà il resto `xs - floor(xs/ys) * ys` e conterrà `result` `floor(xs/ys)` .

## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n dividendi $ bit, verrà sostituito dal resto.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

divisore $n $ bit


### <a name="result--littleendian"></a>risultato: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n risultato $-bit, deve trovarsi nello stato $ \ket {0} $ inizialmente e verrà sostituito dal risultato della divisione di interi.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Usa un approccio standard di spostamento e sottrazione per implementare la divisione.
La versione controllata è specializzata, di conseguenza la sottrazione non richiede controlli aggiuntivi.