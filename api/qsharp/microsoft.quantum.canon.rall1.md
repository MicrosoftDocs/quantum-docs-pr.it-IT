---
uid: Microsoft.Quantum.Canon.RAll1
title: Operazione RAll1
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 36e460f93b4349bc2e3da9bfb22cb0aa82ef1795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205534"
---
# <a name="rall1-operation"></a><span data-ttu-id="fcfa0-102">Operazione RAll1</span><span class="sxs-lookup"><span data-stu-id="fcfa0-102">RAll1 operation</span></span>

<span data-ttu-id="fcfa0-103">Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fcfa0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fcfa0-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcfa0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcfa0-105">Esegue un'operazione di spostamento della fase.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="fcfa0-106">$R = \boldone-(1-e ^ {i \Phi}) \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fcfa0-107">Input</span><span class="sxs-lookup"><span data-stu-id="fcfa0-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="fcfa0-108">fase: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fcfa0-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fcfa0-109">La fase $ \Phi $ è stata applicata allo stato $ \ket{1\cdots 1} \bra{1\cdots 1} $.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="fcfa0-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="fcfa0-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="fcfa0-111">Registro il cui stato deve essere ruotato di $R $.</span><span class="sxs-lookup"><span data-stu-id="fcfa0-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fcfa0-112">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fcfa0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

