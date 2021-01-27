---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: Tipo definito dall'utente UnivariateOptimizationResult
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854577"
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