---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: BoolArrayAsResultArray (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: b30da07272ee1a6c19ae13afa618ba5deb7aaa2d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834198"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="75a5b-102">BoolArrayAsResultArray (funzione)</span><span class="sxs-lookup"><span data-stu-id="75a5b-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="75a5b-103">Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="75a5b-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="75a5b-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75a5b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75a5b-105">Converte un `Bool[]` tipo in un `Result[]` tipo, dove `true` viene mappato a `One` e `false` viene mappato a `Zero` .</span><span class="sxs-lookup"><span data-stu-id="75a5b-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="75a5b-106">Input</span><span class="sxs-lookup"><span data-stu-id="75a5b-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="75a5b-107">input: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="75a5b-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="75a5b-108">`Bool[]` da convertire.</span><span class="sxs-lookup"><span data-stu-id="75a5b-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="75a5b-109">Output: __non <Result> valido__[]</span><span class="sxs-lookup"><span data-stu-id="75a5b-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="75a5b-110">Oggetto `Result[]` che rappresenta l'istanza di `input`.</span><span class="sxs-lookup"><span data-stu-id="75a5b-110">A `Result[]` representing the `input`.</span></span>