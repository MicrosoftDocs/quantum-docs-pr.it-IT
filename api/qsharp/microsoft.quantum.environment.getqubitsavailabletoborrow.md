---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Operazione GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712589"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="1000f-102">Operazione GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="1000f-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="1000f-103">Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="1000f-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="1000f-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1000f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1000f-105">Restituisce il numero di qubits attualmente disponibili per il prestito.</span><span class="sxs-lookup"><span data-stu-id="1000f-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="1000f-106">Sono inclusi i qubits inutilizzati; Ciò è incluso il qubits restituito da `GetQubitsAvailableToUse` .</span><span class="sxs-lookup"><span data-stu-id="1000f-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="1000f-107">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1000f-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1000f-108">Numero di qubits che possono essere allocati in un' `borrowing` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1000f-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="1000f-109">Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="1000f-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="1000f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1000f-110">See Also</span></span>

- [<span data-ttu-id="1000f-111">Microsoft. Quantum. Environment. GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="1000f-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)