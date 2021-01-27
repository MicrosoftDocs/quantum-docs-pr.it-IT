---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operazione InjectPi4YRotation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 249c347c9e9729e719eda69e4e9a21847d9a46eb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98825952"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="131de-102">Operazione InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="131de-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="131de-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="131de-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="131de-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="131de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="131de-105">Ruota un singolo qubit per π/4 sull'asse Y.</span><span class="sxs-lookup"><span data-stu-id="131de-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="131de-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="131de-106">Description</span></span>

<span data-ttu-id="131de-107">Esegue una rotazione di π/4 su `Y` .</span><span class="sxs-lookup"><span data-stu-id="131de-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="131de-108">La rotazione viene eseguita utilizzando uno stato magico; ovvero una copia dello stato $ $ \begin{align} \cos\frac{\Pi} {8} \ket {0} + \sin \frac{\Pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="131de-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="131de-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="131de-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="131de-110">Input</span><span class="sxs-lookup"><span data-stu-id="131de-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="131de-111">dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="131de-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="131de-112">Qubit da ruotare circa $Y $ by $ \Pi/$4.</span><span class="sxs-lookup"><span data-stu-id="131de-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="131de-113">magia: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="131de-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="131de-114">Un qubit inizialmente nello stato Magic.</span><span class="sxs-lookup"><span data-stu-id="131de-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="131de-115">L'applicazione seguente di questa operazione `magic` viene restituita allo stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="131de-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="131de-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="131de-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="131de-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="131de-117">Remarks</span></span>

<span data-ttu-id="131de-118">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="131de-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="131de-119">e</span><span class="sxs-lookup"><span data-stu-id="131de-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="131de-120">Questa operazione supporta il `Adjoint` functor, nel qual caso viene utilizzato lo stesso stato magico, ma l'effetto sui dati qubit è una rotazione $-\ PI/4 $ $Y $-Rotation.</span><span class="sxs-lookup"><span data-stu-id="131de-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>