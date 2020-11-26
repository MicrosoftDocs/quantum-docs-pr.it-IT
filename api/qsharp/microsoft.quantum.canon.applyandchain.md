---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Operazione ApplyAndChain
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219363"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="04100-102">Operazione ApplyAndChain</span><span class="sxs-lookup"><span data-stu-id="04100-102">ApplyAndChain operation</span></span>

<span data-ttu-id="04100-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="04100-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="04100-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04100-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04100-105">Calcola una catena di porte e</span><span class="sxs-lookup"><span data-stu-id="04100-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="04100-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04100-106">Description</span></span>

<span data-ttu-id="04100-107">Il qubits ausiliario per calcolare i risultati temporanei deve essere specificato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="04100-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="04100-108">La lunghezza di tale registro è `Length(ctrlRegister) - 2` , se sono presenti almeno due controlli; in caso contrario, la lunghezza è 0.</span><span class="sxs-lookup"><span data-stu-id="04100-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="04100-109">Input</span><span class="sxs-lookup"><span data-stu-id="04100-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="04100-110">auxRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="04100-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="04100-111">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="04100-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="04100-112">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="04100-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="04100-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04100-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

