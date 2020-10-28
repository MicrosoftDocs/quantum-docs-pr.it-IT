---
uid: Microsoft.Quantum.Canon.RAll1
title: Operazione RAll1
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715627"
---
# <a name="rall1-operation"></a><span data-ttu-id="5cd83-102">Operazione RAll1</span><span class="sxs-lookup"><span data-stu-id="5cd83-102">RAll1 operation</span></span>

<span data-ttu-id="5cd83-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5cd83-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5cd83-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5cd83-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5cd83-105">Esegue un'operazione di spostamento della fase.</span><span class="sxs-lookup"><span data-stu-id="5cd83-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="5cd83-106">$R = \boldone-(1-e ^ {i \Phi}) \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="5cd83-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="5cd83-107">Input</span><span class="sxs-lookup"><span data-stu-id="5cd83-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="5cd83-108">fase: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5cd83-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5cd83-109">La fase $ \Phi $ è stata applicata allo stato $ \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="5cd83-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5cd83-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5cd83-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5cd83-111">Registro il cui stato deve essere ruotato di $R $.</span><span class="sxs-lookup"><span data-stu-id="5cd83-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5cd83-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cd83-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

