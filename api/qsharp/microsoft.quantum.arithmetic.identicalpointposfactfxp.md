---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721119"
---
# <a name="identicalpointposfactfxp-function"></a>IdenticalPointPosFactFxP (funzione)

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Dichiarare che tutti i numeri a virgola fissa nella matrice fornita hanno posizioni di punti identiche quando si esegue il conteggio dal bit meno significativo. Ovvero, il numero di bit meno punti deve essere costante per tutti i numeri a virgola fissa nella matrice.

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>Input

### <a name="fixedpoints--fixedpoint"></a>fixedPoints: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

Matrice di numeri a virgola fissa di Quantum di cui verrà verificata la compatibilità (usando le asserzioni).



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

