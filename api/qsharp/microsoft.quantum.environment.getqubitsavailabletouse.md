---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operazione GetQubitsAvailableToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827791"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="7811c-102">Operazione GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="7811c-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="7811c-103">Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="7811c-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="7811c-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7811c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7811c-105">Restituisce il numero di qubits attualmente disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="7811c-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="7811c-106">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7811c-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7811c-107">Numero di qubits che possono essere allocati in un' `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7811c-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="7811c-108">Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="7811c-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="7811c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7811c-109">See Also</span></span>

- [<span data-ttu-id="7811c-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="7811c-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)