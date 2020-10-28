---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712676"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="0af5d-102">FormattedFailure (funzione)</span><span class="sxs-lookup"><span data-stu-id="0af5d-102">FormattedFailure function</span></span>

<span data-ttu-id="0af5d-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0af5d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0af5d-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0af5d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0af5d-105">Funzione interna utilizzata per generare un errore con messaggi di errore significativi.</span><span class="sxs-lookup"><span data-stu-id="0af5d-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="0af5d-106">Input</span><span class="sxs-lookup"><span data-stu-id="0af5d-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="0af5d-107">valore effettivo:' t</span><span class="sxs-lookup"><span data-stu-id="0af5d-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="0af5d-108">previsto:' t</span><span class="sxs-lookup"><span data-stu-id="0af5d-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="0af5d-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0af5d-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="0af5d-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0af5d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0af5d-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="0af5d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0af5d-112">T</span><span class="sxs-lookup"><span data-stu-id="0af5d-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="0af5d-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="0af5d-113">Remarks</span></span>

<span data-ttu-id="0af5d-114">Questa funzione è progettata per essere emulata dai runtime di simulazione, in modo da consentire l'invio di contraddizioni formattate.</span><span class="sxs-lookup"><span data-stu-id="0af5d-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>