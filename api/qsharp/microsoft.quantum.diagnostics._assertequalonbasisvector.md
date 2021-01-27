---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: operazione _assertEqualOnBasisVector
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853591"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="568ef-102">operazione _assertEqualOnBasisVector</span><span class="sxs-lookup"><span data-stu-id="568ef-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="568ef-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="568ef-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="568ef-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="568ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="568ef-105">Controlla se il risultato dell'applicazione di due operazioni `givenU` e `expectedU` a uno stato di base è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="568ef-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="568ef-106">Lo stato di base è descritto dal `basis` parametro.</span><span class="sxs-lookup"><span data-stu-id="568ef-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="568ef-107"><xref:microsoft.quantum.extensions.fliptobasis>Per ulteriori informazioni su questa descrizione, vedere la funzione.</span><span class="sxs-lookup"><span data-stu-id="568ef-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="568ef-108">Input</span><span class="sxs-lookup"><span data-stu-id="568ef-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="568ef-109">base: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="568ef-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="568ef-110">Stato di base specificato da un ID di stato di base a qubit singolo (0 <= ID <= 3) per ogni $n $ qubits.</span><span class="sxs-lookup"><span data-stu-id="568ef-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="568ef-111">dato: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="568ef-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="568ef-112">Operazione su $n $ qubits da controllare.</span><span class="sxs-lookup"><span data-stu-id="568ef-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="568ef-113">previsto: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ</span><span class="sxs-lookup"><span data-stu-id="568ef-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="568ef-114">Operazione di riferimento su $n $ qubits in base a cui deve essere confrontato.</span><span class="sxs-lookup"><span data-stu-id="568ef-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="568ef-115">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="568ef-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

