---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Operazione _ExtractLogicalQubitFromSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853204"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="ea281-102">Operazione _ExtractLogicalQubitFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="ea281-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="ea281-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ea281-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ea281-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ea281-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ea281-105">Misurazione della sindrome e inverso dell'incorporamento.</span><span class="sxs-lookup"><span data-stu-id="ea281-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="ea281-106">$X $-e $Z $-stabilizzatori non vengono considerati equamente, a causa della scelta particolare del circuito di codifica.</span><span class="sxs-lookup"><span data-stu-id="ea281-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="ea281-107">Questa asimmetria conduce a una routine di estrazione della sindrome diversa.</span><span class="sxs-lookup"><span data-stu-id="ea281-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="ea281-108">Uno può misurare la sindrome misurando l'operatore Pauli multiqubit direttamente sullo stato del codice, ma per lo scopo della distillazione il qubit logico viene restituito in un singolo qubit, in cui le misurazioni di sindrome possono essere eseguite senza ulteriori ancillas.</span><span class="sxs-lookup"><span data-stu-id="ea281-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="ea281-109">Input</span><span class="sxs-lookup"><span data-stu-id="ea281-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="ea281-110">Codice: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="ea281-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="ea281-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="ea281-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="ea281-112">Il qubit logico e una coppia di numeri interi per $X $-Syndrome e $Z $-Syndrome.</span><span class="sxs-lookup"><span data-stu-id="ea281-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="ea281-113">Rappresentano l'indice del qubit del codice in cui un singolo $X $-o $Z $-Error avrebbe causato la sindrome misurata.</span><span class="sxs-lookup"><span data-stu-id="ea281-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea281-114">Commenti</span><span class="sxs-lookup"><span data-stu-id="ea281-114">Remarks</span></span>

<span data-ttu-id="ea281-115">Si noti che questa operazione non è contrassegnata come `internal` , perché gli unit test dipendono direttamente da questa operazione.</span><span class="sxs-lookup"><span data-stu-id="ea281-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="ea281-116">Come miglioramento futuro, è necessario effettuare il refactoring degli unit test in modo che dipendano direttamente dai chiamanti pubblici.</span><span class="sxs-lookup"><span data-stu-id="ea281-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="ea281-117">Questa routine è adattata a un particolare circuito di codifica per il codice qubit 7 di Steane; Se il circuito di codifica viene modificato, il risultato della sindrome potrebbe essere interpretato in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="ea281-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>