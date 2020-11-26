---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201513"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dichiara che un valore a virgola mobile classico ha il valore previsto fino a una piccola tolleranza di 1E-10.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Input

### <a name="actual--double"></a>effettivo: [Double](xref:microsoft.quantum.lang-ref.double)

Numero da verificare.


### <a name="expected--double"></a>previsto: [Double](xref:microsoft.quantum.lang-ref.double)

Valore previsto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Equivale a con la <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> tolleranza hardcoded di $10 ^ {-10} $.