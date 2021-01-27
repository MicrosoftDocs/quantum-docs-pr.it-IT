---
uid: Microsoft.Quantum.Canon.WeightOnePaulis
title: WeightOnePaulis (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: WeightOnePaulis
qsharp.summary: Returns an array of all weight-1 Pauli operators on a given number of qubits.
ms.openlocfilehash: 8aeea795ef5409339e8a1b39c3ffcfaf29d675b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851979"
---
# <a name="weightonepaulis-function"></a><span data-ttu-id="dd589-102">WeightOnePaulis (funzione)</span><span class="sxs-lookup"><span data-stu-id="dd589-102">WeightOnePaulis function</span></span>

<span data-ttu-id="dd589-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dd589-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dd589-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dd589-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dd589-105">Restituisce una matrice di tutti gli operatori Weight-1 di Pauli su un determinato numero di qubits.</span><span class="sxs-lookup"><span data-stu-id="dd589-105">Returns an array of all weight-1 Pauli operators on a given number of qubits.</span></span>

```qsharp
function WeightOnePaulis (nQubits : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="dd589-106">Input</span><span class="sxs-lookup"><span data-stu-id="dd589-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="dd589-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd589-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd589-108">Numero di qubits in cui sono definiti gli operatori Pauli restituiti.</span><span class="sxs-lookup"><span data-stu-id="dd589-108">The number of qubits on which the returned Pauli operators are defined.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="dd589-109">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="dd589-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="dd589-110">Matrice di operatori Pauli qubit, ognuno dei quali è rappresentato come matrice con lunghezza `nQubits` .</span><span class="sxs-lookup"><span data-stu-id="dd589-110">An array of multi-qubit Pauli operators, each of which is represented as an array with length `nQubits`.</span></span>