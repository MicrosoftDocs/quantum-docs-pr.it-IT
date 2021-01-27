---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 0ed5c81cb80458e2f56ba2fcaac03eb92a534bea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834179"
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