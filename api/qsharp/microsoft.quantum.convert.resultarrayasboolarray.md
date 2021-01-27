---
uid: Microsoft.Quantum.Convert.ResultArrayAsBoolArray
title: ResultArrayAsBoolArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: ResultArrayAsBoolArray
qsharp.summary: Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.
ms.openlocfilehash: 384531137474562ebc8cc24dcd1ac976dc91ad9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832601"
---
# <a name="resultarrayasboolarray-function"></a><span data-ttu-id="d6e29-102">ResultArrayAsBoolArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="d6e29-102">ResultArrayAsBoolArray function</span></span>

<span data-ttu-id="d6e29-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d6e29-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d6e29-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6e29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6e29-105">Converte un `Result[]` tipo in un `Bool[]` tipo, dove `One` viene mappato a `true` e `Zero` viene mappato a `false` .</span><span class="sxs-lookup"><span data-stu-id="d6e29-105">Converts a `Result[]` type to a `Bool[]` type, where `One` is mapped to `true` and `Zero` is mapped to `false`.</span></span>

```qsharp
function ResultArrayAsBoolArray (input : Result[]) : Bool[]
```


## <a name="input"></a><span data-ttu-id="d6e29-106">Input</span><span class="sxs-lookup"><span data-stu-id="d6e29-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="d6e29-107">input: __non <Result> valido__[]</span><span class="sxs-lookup"><span data-stu-id="d6e29-107">input : __invalid<Result>__[]</span></span>

<span data-ttu-id="d6e29-108">`Result[]` da convertire.</span><span class="sxs-lookup"><span data-stu-id="d6e29-108">`Result[]` to be converted.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d6e29-109">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d6e29-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="d6e29-110">Oggetto `Bool[]` che rappresenta l'istanza di `input`.</span><span class="sxs-lookup"><span data-stu-id="d6e29-110">A `Bool[]` representing the `input`.</span></span>