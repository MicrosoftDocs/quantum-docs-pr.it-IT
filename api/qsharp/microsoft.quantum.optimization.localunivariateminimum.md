---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854601"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum (funzione)

Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce il valore minimo locale per una funzione univariata su un intervallo delimitato, usando una ricerca con intervallo dorato.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Input

### <a name="fn--double---double"></a>FN: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)

Funzione univariata da ridurre a icona.


### <a name="bounds--doubledouble"></a>limiti: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

Intervallo nel quale deve essere trovato il valore minimo locale.


### <a name="tolerance--double"></a>tolleranza: [Double](xref:microsoft.quantum.lang-ref.double)

Accuratezza nell'input della funzione da tollerare.
La ricerca di Optima locale continuerà fino a quando l'intervallo non sarà più piccolo in larghezza rispetto a questa tolleranza.



## <a name="output--univariateoptimizationresult"></a>Output: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Optima locale della funzione specificata, che si trova all'interno dei limiti specificati.