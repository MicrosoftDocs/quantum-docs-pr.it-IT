---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828272"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="a7d46-102">FormattedFailure (funzione)</span><span class="sxs-lookup"><span data-stu-id="a7d46-102">FormattedFailure function</span></span>

<span data-ttu-id="a7d46-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a7d46-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a7d46-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7d46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7d46-105">Funzione interna utilizzata per generare un errore con messaggi di errore significativi.</span><span class="sxs-lookup"><span data-stu-id="a7d46-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a7d46-106">Input</span><span class="sxs-lookup"><span data-stu-id="a7d46-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="a7d46-107">valore effettivo:' t</span><span class="sxs-lookup"><span data-stu-id="a7d46-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="a7d46-108">previsto:' t</span><span class="sxs-lookup"><span data-stu-id="a7d46-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="a7d46-109">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a7d46-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="a7d46-110">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a7d46-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a7d46-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="a7d46-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7d46-112">T</span><span class="sxs-lookup"><span data-stu-id="a7d46-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="a7d46-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="a7d46-113">Remarks</span></span>

<span data-ttu-id="a7d46-114">Questa funzione è progettata per essere emulata dai runtime di simulazione, in modo da consentire l'invio di contraddizioni formattate.</span><span class="sxs-lookup"><span data-stu-id="a7d46-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>