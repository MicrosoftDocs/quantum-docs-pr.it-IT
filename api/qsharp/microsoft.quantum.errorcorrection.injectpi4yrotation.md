---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operazione InjectPi4YRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712323"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="b49e3-102">Operazione InjectPi4YRotation</span><span class="sxs-lookup"><span data-stu-id="b49e3-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="b49e3-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b49e3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b49e3-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b49e3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b49e3-105">Ruota un singolo qubit per π/4 sull'asse Y.</span><span class="sxs-lookup"><span data-stu-id="b49e3-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b49e3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b49e3-106">Description</span></span>

<span data-ttu-id="b49e3-107">Esegue una rotazione di π/4 su `Y` .</span><span class="sxs-lookup"><span data-stu-id="b49e3-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="b49e3-108">La rotazione viene eseguita utilizzando uno stato magico; ovvero una copia dello stato $ $ \begin{align} \cos\frac{\Pi} {8} \ket {0} + \sin \frac{\Pi} {8} \ket {1} .</span><span class="sxs-lookup"><span data-stu-id="b49e3-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="b49e3-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="b49e3-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="b49e3-110">Input</span><span class="sxs-lookup"><span data-stu-id="b49e3-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="b49e3-111">dati: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b49e3-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b49e3-112">Qubit da ruotare circa $Y $ by $ \Pi/$4.</span><span class="sxs-lookup"><span data-stu-id="b49e3-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="b49e3-113">magia: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b49e3-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b49e3-114">Un qubit inizialmente nello stato Magic.</span><span class="sxs-lookup"><span data-stu-id="b49e3-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="b49e3-115">L'applicazione seguente di questa operazione `magic` viene restituita allo stato $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b49e3-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b49e3-116">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b49e3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b49e3-117">Commenti</span><span class="sxs-lookup"><span data-stu-id="b49e3-117">Remarks</span></span>

<span data-ttu-id="b49e3-118">Gli elementi seguenti sono equivalenti:</span><span class="sxs-lookup"><span data-stu-id="b49e3-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="b49e3-119">e</span><span class="sxs-lookup"><span data-stu-id="b49e3-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="b49e3-120">Questa operazione supporta il `Adjoint` functor, nel qual caso viene utilizzato lo stesso stato magico, ma l'effetto sui dati qubit è una rotazione $-\ PI/4 $ $Y $-Rotation.</span><span class="sxs-lookup"><span data-stu-id="b49e3-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>