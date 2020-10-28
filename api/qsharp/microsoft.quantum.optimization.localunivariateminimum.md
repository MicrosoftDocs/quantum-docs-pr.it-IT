---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711021"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum (funzione)

Spazio dei nomi: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Pacchetto [](https://nuget.org/packages/)


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