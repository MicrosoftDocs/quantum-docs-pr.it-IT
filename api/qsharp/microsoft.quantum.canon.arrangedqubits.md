---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 7f3bc4dff73d5ad6393294fc3770b8d36e6094fb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217068"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="7598d-102">ArrangedQubits (funzione)</span><span class="sxs-lookup"><span data-stu-id="7598d-102">ArrangedQubits function</span></span>

<span data-ttu-id="7598d-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7598d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7598d-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7598d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7598d-105">Disporre qubits di controllo, di destinazione e di supporto in base a un indice</span><span class="sxs-lookup"><span data-stu-id="7598d-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="7598d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7598d-106">Description</span></span>

<span data-ttu-id="7598d-107">Restituisce una matrice qubit con la destinazione in corrispondenza dell'indice 0 e il controllo i in corrispondenza dell'indice 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="7598d-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="7598d-108">Il qubits Helper viene inserito in tutte le altre posizioni nella matrice.</span><span class="sxs-lookup"><span data-stu-id="7598d-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="7598d-109">Input</span><span class="sxs-lookup"><span data-stu-id="7598d-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="7598d-110">Controlli: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7598d-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="7598d-111">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7598d-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="7598d-112">Helper: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7598d-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="7598d-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7598d-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

