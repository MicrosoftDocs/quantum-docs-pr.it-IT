---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712757"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="bc19d-102">EqualityFactL (funzione)</span><span class="sxs-lookup"><span data-stu-id="bc19d-102">EqualityFactL function</span></span>

<span data-ttu-id="bc19d-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bc19d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bc19d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc19d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc19d-105">Dichiara che una variabile BigInt classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="bc19d-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bc19d-106">Input</span><span class="sxs-lookup"><span data-stu-id="bc19d-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="bc19d-107">effettivo: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bc19d-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bc19d-108">Numero da verificare.</span><span class="sxs-lookup"><span data-stu-id="bc19d-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="bc19d-109">previsto: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bc19d-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bc19d-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="bc19d-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="bc19d-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bc19d-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bc19d-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="bc19d-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc19d-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc19d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
