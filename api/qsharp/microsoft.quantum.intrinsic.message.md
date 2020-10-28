---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711427"
---
# <a name="message-function"></a><span data-ttu-id="3373a-102">Message (funzione)</span><span class="sxs-lookup"><span data-stu-id="3373a-102">Message function</span></span>

<span data-ttu-id="3373a-103">Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3373a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3373a-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3373a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3373a-105">Registra un messaggio.</span><span class="sxs-lookup"><span data-stu-id="3373a-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3373a-106">Input</span><span class="sxs-lookup"><span data-stu-id="3373a-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="3373a-107">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3373a-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3373a-108">Messaggio da segnalare.</span><span class="sxs-lookup"><span data-stu-id="3373a-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3373a-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3373a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3373a-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="3373a-110">Remarks</span></span>

<span data-ttu-id="3373a-111">Il comportamento specifico di questa funzione è dipendente dal simulatore, ma nella maggior parte dei casi il messaggio specificato verrà scritto nella console.</span><span class="sxs-lookup"><span data-stu-id="3373a-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>