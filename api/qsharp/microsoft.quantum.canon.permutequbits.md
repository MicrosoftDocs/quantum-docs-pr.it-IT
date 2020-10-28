---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operazione PermuteQubits
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715658"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="42bb7-102">Operazione PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="42bb7-102">PermuteQubits operation</span></span>

<span data-ttu-id="42bb7-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="42bb7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="42bb7-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42bb7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42bb7-105">Permuta qubits tramite l'operazione SWAP.</span><span class="sxs-lookup"><span data-stu-id="42bb7-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="42bb7-106">Input</span><span class="sxs-lookup"><span data-stu-id="42bb7-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="42bb7-107">ordinamento: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="42bb7-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="42bb7-108">Viene descritto il nuovo ordinamento di qubits, in cui il qubit in corrispondenza dell'indice i verrà ora ordinato [i].</span><span class="sxs-lookup"><span data-stu-id="42bb7-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="42bb7-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="42bb7-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="42bb7-110">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="42bb7-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42bb7-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42bb7-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

