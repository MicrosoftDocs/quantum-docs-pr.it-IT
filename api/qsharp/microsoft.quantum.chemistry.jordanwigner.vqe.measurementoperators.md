---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 204ae621b77559a894f0bce14e494824d58e4ad6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835404"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="6a05d-102">MeasurementOperators (funzione)</span><span class="sxs-lookup"><span data-stu-id="6a05d-102">MeasurementOperators function</span></span>

<span data-ttu-id="6a05d-103">Spazio dei nomi: [Microsoft. Quantum. Chemistry. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="6a05d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="6a05d-104">Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6a05d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6a05d-105">Calcola tutti gli operatori di misurazione necessari per calcolare l'aspettativa di un termine di Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="6a05d-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="6a05d-106">Input</span><span class="sxs-lookup"><span data-stu-id="6a05d-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6a05d-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a05d-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a05d-108">Numero di qubits necessari per simulare il sistema molecolare.</span><span class="sxs-lookup"><span data-stu-id="6a05d-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="6a05d-109">indici: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6a05d-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6a05d-110">Matrice contenente gli indici di qubit a cui viene applicato ogni operatore Pauli.</span><span class="sxs-lookup"><span data-stu-id="6a05d-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="6a05d-111">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6a05d-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6a05d-112">Tipo del termine del Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="6a05d-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="6a05d-113">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="6a05d-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="6a05d-114">Matrice di operatori di misurazione (ognuno dei quali è una matrice di Pauli).</span><span class="sxs-lookup"><span data-stu-id="6a05d-114">An array of measurement operators (each being an array of Pauli).</span></span>