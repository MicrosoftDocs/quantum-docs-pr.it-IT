---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definito dall'utente UnivariateOptimizationResult
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724325"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>Tipo definito dall'utente UnivariateOptimizationResult

Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Pacchetto [](https://nuget.org/packages/)


Rappresenta il risultato dell'ottimizzazione di una funzione univariata.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Elementi denominati

### <a name="coordinate--double"></a>Coordinata: [Double](xref:microsoft.quantum.lang-ref.double)

Input in corrispondenza del quale è stato trovato un risultato ottimale.
### <a name="value--double"></a>Valore: [Double](xref:microsoft.quantum.lang-ref.double)

Valore restituito dalla funzione al suo Optimum.