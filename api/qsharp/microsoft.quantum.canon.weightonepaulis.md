---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 89802c1bc6f3da8edef27b698eb61098e47dfc85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715196"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="27841-102">WeightOnePaulis (funzione)</span><span class="sxs-lookup"><span data-stu-id="27841-102">WeightOnePaulis function</span></span>

<span data-ttu-id="27841-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27841-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27841-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27841-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27841-105">Restituisce una matrice di tutti gli operatori Weight-1 di Pauli su un determinato numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="27841-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="27841-106">Input</span><span class="sxs-lookup"><span data-stu-id="27841-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="27841-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27841-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27841-108">Numero di qubits in cui sono definiti gli operatori Pauli restituiti.</span><span class="sxs-lookup"><span data-stu-id="27841-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="27841-109">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="27841-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="27841-110">Matrice di operatori Pauli qubit, ognuno dei quali è rappresentato come matrice con lunghezza `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="27841-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>