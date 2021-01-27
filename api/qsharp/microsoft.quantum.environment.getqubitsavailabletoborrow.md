---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operazione GetQubitsAvailableToBorrow
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853238"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="b39ed-102">Operazione GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="b39ed-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="b39ed-103">Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="b39ed-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="b39ed-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b39ed-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b39ed-105">Restituisce il numero di qubits attualmente disponibili per il prestito.</span><span class="sxs-lookup"><span data-stu-id="b39ed-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="b39ed-106">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b39ed-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b39ed-107">Numero di qubits che possono essere presi in prestito e che non verranno allocati come parte di un' `borrowing` istruzione.</span><span class="sxs-lookup"><span data-stu-id="b39ed-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="b39ed-108">Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="b39ed-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="b39ed-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b39ed-109">See Also</span></span>

- [<span data-ttu-id="b39ed-110">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="b39ed-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)