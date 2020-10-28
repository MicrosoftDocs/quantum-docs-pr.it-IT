---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 0356fe9c98306ee3e1857f4af311aef9b3789a7d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713359"
---
# <a name="resultarrayasboolarray-function"></a>ResultArrayAsBoolArray (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Converte un `Result[]` tipo in un `Bool[]` tipo, dove `One` viene mappato a `true` e `Zero` viene mappato a `false` .

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a>Input

### <a name="input--__invalidresult__"></a>input: __non <Result> valido__ []

`Result[]` da convertire.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Oggetto `Bool[]` che rappresenta l'istanza di `input`.