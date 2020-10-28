---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: de15a32d5b38c5ab8c681d2c052669a48cf676cc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712746"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact (funzione)

Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacchetto [](https://nuget.org/packages/)


Rappresenta l'attestazione che un valore a virgola mobile classico ha il valore previsto fino a una tolleranza assoluta specificata.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Input

### <a name="actual--double"></a>effettivo: [Double](xref:microsoft.quantum.lang-ref.double)

Numero da verificare.


### <a name="expected--double"></a>previsto: [Double](xref:microsoft.quantum.lang-ref.double)

Valore previsto.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Tolleranza assoluta sulla differenza tra il valore effettivo e quello previsto.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

