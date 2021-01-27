---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853369"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="9ca78-102">EqualityFactC (funzione)</span><span class="sxs-lookup"><span data-stu-id="9ca78-102">EqualityFactC function</span></span>

<span data-ttu-id="9ca78-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9ca78-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9ca78-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9ca78-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9ca78-105">Dichiara che un numero complesso presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="9ca78-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9ca78-106">Input</span><span class="sxs-lookup"><span data-stu-id="9ca78-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="9ca78-107">effettivo: [complesso](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="9ca78-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="9ca78-108">Valore da verificare.</span><span class="sxs-lookup"><span data-stu-id="9ca78-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="9ca78-109">previsto: [complesso](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="9ca78-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="9ca78-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="9ca78-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="9ca78-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9ca78-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9ca78-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="9ca78-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ca78-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ca78-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

