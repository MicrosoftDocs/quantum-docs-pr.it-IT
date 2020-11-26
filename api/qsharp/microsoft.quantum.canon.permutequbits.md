---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: Operazione PermuteQubits
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: deb5fa5b0bc0509c957e01bf22e491ad3e2214f3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205605"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="c00f4-102">Operazione PermuteQubits</span><span class="sxs-lookup"><span data-stu-id="c00f4-102">PermuteQubits operation</span></span>

<span data-ttu-id="c00f4-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c00f4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c00f4-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c00f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c00f4-105">Permuta qubits tramite l'operazione SWAP.</span><span class="sxs-lookup"><span data-stu-id="c00f4-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c00f4-106">Input</span><span class="sxs-lookup"><span data-stu-id="c00f4-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="c00f4-107">ordinamento: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c00f4-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c00f4-108">Viene descritto il nuovo ordinamento di qubits, in cui il qubit in corrispondenza dell'indice i verrà ora ordinato [i].</span><span class="sxs-lookup"><span data-stu-id="c00f4-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="c00f4-109">Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c00f4-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c00f4-110">Registro qubit su cui agire.</span><span class="sxs-lookup"><span data-stu-id="c00f4-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c00f4-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c00f4-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

