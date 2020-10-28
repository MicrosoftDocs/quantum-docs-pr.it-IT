---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Operazione MeasurePaulis
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720342"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="046c9-102">Operazione MeasurePaulis</span><span class="sxs-lookup"><span data-stu-id="046c9-102">MeasurePaulis operation</span></span>

<span data-ttu-id="046c9-103">Spazio dei nomi: [Microsoft. Quantum. Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="046c9-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="046c9-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="046c9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="046c9-105">Data una matrice di operatori qubit di Pauli, misura ognuno usando un gadget di misurazione specificato, quindi restituisce la matrice di risultati.</span><span class="sxs-lookup"><span data-stu-id="046c9-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="046c9-106">Input</span><span class="sxs-lookup"><span data-stu-id="046c9-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="046c9-107">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="046c9-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="046c9-108">Matrice di operatori Pauli multiqubit da misurare.</span><span class="sxs-lookup"><span data-stu-id="046c9-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="046c9-109">destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="046c9-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="046c9-110">Eseguire la registrazione per misurare gli operatori specificati.</span><span class="sxs-lookup"><span data-stu-id="046c9-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="046c9-111">Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __non <Result> valido__</span><span class="sxs-lookup"><span data-stu-id="046c9-111">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="046c9-112">Operazione che esegue la misurazione di un operatore multiqubit specificato.</span><span class="sxs-lookup"><span data-stu-id="046c9-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="046c9-113">Output: __non <Result> valido__ []</span><span class="sxs-lookup"><span data-stu-id="046c9-113">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="046c9-114">Matrice di risultati ottenuti dalla misurazione di ogni elemento di `paulis` su `target` .</span><span class="sxs-lookup"><span data-stu-id="046c9-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>