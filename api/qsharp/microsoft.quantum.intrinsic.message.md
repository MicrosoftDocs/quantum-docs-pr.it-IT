---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849367"
---
# <a name="message-function"></a><span data-ttu-id="2d45c-102">Message (funzione)</span><span class="sxs-lookup"><span data-stu-id="2d45c-102">Message function</span></span>

<span data-ttu-id="2d45c-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2d45c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2d45c-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="2d45c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2d45c-105">Registra un messaggio.</span><span class="sxs-lookup"><span data-stu-id="2d45c-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2d45c-106">Input</span><span class="sxs-lookup"><span data-stu-id="2d45c-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="2d45c-107">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2d45c-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2d45c-108">Messaggio da segnalare.</span><span class="sxs-lookup"><span data-stu-id="2d45c-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2d45c-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2d45c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2d45c-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="2d45c-110">Remarks</span></span>

<span data-ttu-id="2d45c-111">Il comportamento specifico di questa funzione è dipendente dal simulatore, ma nella maggior parte dei casi il messaggio specificato verrà scritto nella console.</span><span class="sxs-lookup"><span data-stu-id="2d45c-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>