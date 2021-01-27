---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: TrotterStepOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: a3164da1ce9ae1f72ec2fb1fa151159768cd5a4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835809"
---
# <a name="trottersteporacle-function"></a><span data-ttu-id="1452b-102">TrotterStepOracle (funzione)</span><span class="sxs-lookup"><span data-stu-id="1452b-102">TrotterStepOracle function</span></span>

<span data-ttu-id="1452b-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1452b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1452b-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1452b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1452b-105">Restituisce l'operazione del passaggio Trotter e i parametri necessari per eseguirlo.</span><span class="sxs-lookup"><span data-stu-id="1452b-105">Returns Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="1452b-106">Input</span><span class="sxs-lookup"><span data-stu-id="1452b-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="1452b-107">qSharpData: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="1452b-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="1452b-108">Hamiltoniana descritta dal `JordanWignerEncodingData` formato.</span><span class="sxs-lookup"><span data-stu-id="1452b-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="1452b-109">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1452b-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1452b-110">Dimensioni del passaggio di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="1452b-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="1452b-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1452b-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1452b-112">Ordine di Trotter Integrator.</span><span class="sxs-lookup"><span data-stu-id="1452b-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit--is-adj--ctl"></a><span data-ttu-id="1452b-113">Output: ([int](xref:microsoft.quantum.lang-ref.int), ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unit](xref:microsoft.quantum.lang-ref.unit)  is ADJ + CTL))</span><span class="sxs-lookup"><span data-stu-id="1452b-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl))</span></span>

<span data-ttu-id="1452b-114">Tupla in cui: `Int` è il numero di qubits allocato, `Double` è `1.0/trotterStepSize` e l'operazione è il passaggio Trotter.</span><span class="sxs-lookup"><span data-stu-id="1452b-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>