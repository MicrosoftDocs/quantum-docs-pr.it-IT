---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definito dall'utente UnivariateOptimizationResult
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194033"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Tipo definito dall'utente UnivariateOptimizationResult

Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta il risultato dell'ottimizzazione di una funzione univariata.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Elementi denominati

### <a name="coordinate--double"></a>Coordinata: [Double](xref:microsoft.quantum.lang-ref.double)

Input in corrispondenza del quale è stato trovato un risultato ottimale.
### <a name="value--double"></a>Valore: [Double](xref:microsoft.quantum.lang-ref.double)

Valore restituito dalla funzione al suo Optimum.