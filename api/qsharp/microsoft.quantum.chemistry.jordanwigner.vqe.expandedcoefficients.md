---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713712"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="22efa-102">ExpandedCoefficients (funzione)</span><span class="sxs-lookup"><span data-stu-id="22efa-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="22efa-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="22efa-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="22efa-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22efa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22efa-105">Espande la rappresentazione compatta dei coefficienti di Jordan-Wigner per ottenere un mapping uno-a-uno tra questi e i termini di Pauli.</span><span class="sxs-lookup"><span data-stu-id="22efa-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="22efa-106">Input</span><span class="sxs-lookup"><span data-stu-id="22efa-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="22efa-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="22efa-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="22efa-108">Matrice di coefficienti, come letto dalla struttura di dati Jordan-Wigner hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="22efa-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="22efa-109">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22efa-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22efa-110">Tipo del termine del Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="22efa-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="22efa-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="22efa-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="22efa-112">Matrici di coefficienti espanse, una per ogni termine di Pauli.</span><span class="sxs-lookup"><span data-stu-id="22efa-112">Expanded arrays of coefficients, one per Pauli term.</span></span>