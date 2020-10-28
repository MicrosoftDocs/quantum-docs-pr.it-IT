---
uid: Microsoft.Quantum.Convert.BoolAsResult
title: BoolAsResult (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolAsResult
qsharp.summary: Converts a `Bool` type to a `Result` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: eea6c062afdbb3172e63261e52a82e2576c14011
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713586"
---
# <a name="boolasresult-function"></a>BoolAsResult (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Converte un `Bool` tipo in un `Result` tipo, dove `true` viene mappato a `One` e `false` viene mappato a `Zero` .

```qsharp
function BoolAsResult (input : Bool) : Result
```


## <a name="input"></a>Input

### <a name="input--bool"></a>input: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool` da convertire.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Oggetto `Result` che rappresenta l'istanza di `input`.