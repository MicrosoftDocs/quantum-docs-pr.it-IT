---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201700"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="bfdbc-102">FormattedFailure (funzione)</span><span class="sxs-lookup"><span data-stu-id="bfdbc-102">FormattedFailure function</span></span>

<span data-ttu-id="bfdbc-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bfdbc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bfdbc-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bfdbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bfdbc-105">Funzione interna utilizzata per generare un errore con messaggi di errore significativi.</span><span class="sxs-lookup"><span data-stu-id="bfdbc-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bfdbc-106">Input</span><span class="sxs-lookup"><span data-stu-id="bfdbc-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="bfdbc-107">valore effettivo:' t</span><span class="sxs-lookup"><span data-stu-id="bfdbc-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="bfdbc-108">previsto:' t</span><span class="sxs-lookup"><span data-stu-id="bfdbc-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="bfdbc-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bfdbc-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="bfdbc-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfdbc-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bfdbc-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="bfdbc-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bfdbc-112">T</span><span class="sxs-lookup"><span data-stu-id="bfdbc-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="bfdbc-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="bfdbc-113">Remarks</span></span>

<span data-ttu-id="bfdbc-114">Questa funzione è progettata per essere emulata dai runtime di simulazione, in modo da consentire l'invio di contraddizioni formattate.</span><span class="sxs-lookup"><span data-stu-id="bfdbc-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>