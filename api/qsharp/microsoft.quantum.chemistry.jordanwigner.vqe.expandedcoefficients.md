---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835612"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="4a0da-102">ExpandedCoefficients (funzione)</span><span class="sxs-lookup"><span data-stu-id="4a0da-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="4a0da-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="4a0da-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="4a0da-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4a0da-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4a0da-105">Espande la rappresentazione compatta dei coefficienti di Jordan-Wigner per ottenere un mapping uno-a-uno tra questi e i termini di Pauli.</span><span class="sxs-lookup"><span data-stu-id="4a0da-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="4a0da-106">Input</span><span class="sxs-lookup"><span data-stu-id="4a0da-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="4a0da-107">Coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4a0da-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4a0da-108">Matrice di coefficienti, come letto dalla struttura di dati Jordan-Wigner hamiltoniana.</span><span class="sxs-lookup"><span data-stu-id="4a0da-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="4a0da-109">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4a0da-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4a0da-110">Tipo del termine del Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="4a0da-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="4a0da-111">Output: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4a0da-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4a0da-112">Matrici di coefficienti espanse, una per ogni termine di Pauli.</span><span class="sxs-lookup"><span data-stu-id="4a0da-112">Expanded arrays of coefficients, one per Pauli term.</span></span>