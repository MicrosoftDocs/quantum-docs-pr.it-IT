---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Operazione GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201411"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="1e254-102">Operazione GetQubitsAvailableToUse</span><span class="sxs-lookup"><span data-stu-id="1e254-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="1e254-103">Spazio dei nomi: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="1e254-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="1e254-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1e254-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1e254-105">Restituisce il numero di qubits attualmente disponibili per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="1e254-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="1e254-106">Output: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1e254-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1e254-107">Numero di qubits che possono essere allocati in un' `using` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1e254-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="1e254-108">Se il computer di destinazione utilizzato non fornisce queste informazioni, `-1` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="1e254-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e254-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e254-109">See Also</span></span>

- [<span data-ttu-id="1e254-110">Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow</span><span class="sxs-lookup"><span data-stu-id="1e254-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)