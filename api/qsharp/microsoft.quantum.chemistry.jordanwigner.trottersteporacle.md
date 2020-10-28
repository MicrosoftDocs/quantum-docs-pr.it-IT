---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: TrotterStepOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f7659616ea39d781137c26965cbf2005c5e634b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713768"
---
# <a name="trottersteporacle-function"></a><span data-ttu-id="602fd-102">TrotterStepOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="602fd-102">TrotterStepOracle function</span></span>

<span data-ttu-id="602fd-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="602fd-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="602fd-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="602fd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="602fd-105">Restituisce l'operazione del passaggio Trotter e i parametri necessari per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="602fd-105">Returns Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="602fd-106">Input</span><span class="sxs-lookup"><span data-stu-id="602fd-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="602fd-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="602fd-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="602fd-108">Hamiltoniana descritta dal `JordanWignerEncodingData` formato.</span><span class="sxs-lookup"><span data-stu-id="602fd-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="602fd-109">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="602fd-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="602fd-110">Dimensioni del passaggio di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="602fd-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="602fd-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="602fd-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="602fd-112">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="602fd-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="602fd-113">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL))</span><span class="sxs-lookup"><span data-stu-id="602fd-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="602fd-114">Tupla in cui: `Int` è il numero di qubits allocato, `Double` è `1.0/trotterStepSize` e l'operazione è il passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="602fd-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>