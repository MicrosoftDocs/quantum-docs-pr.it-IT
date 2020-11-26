---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0190529dd804922a69499fbf1c2c4c916c4b720a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214246"
---
# <a name="boolasresult-function"></a>BoolAsResult (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte un `Bool` tipo in un `Result` tipo, dove `true` viene mappato a `One` e `false` viene mappato a `Zero` .

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>Input

### <a name="input--bool"></a>input: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` da convertire.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Oggetto `Result` che rappresenta l'istanza di `input`.