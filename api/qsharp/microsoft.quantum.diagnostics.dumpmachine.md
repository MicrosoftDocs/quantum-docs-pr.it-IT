---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712872"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="c4367-102">DumpMachine (funzione)</span><span class="sxs-lookup"><span data-stu-id="c4367-102">DumpMachine function</span></span>

<span data-ttu-id="c4367-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c4367-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c4367-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4367-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4367-105">Scarica lo stato del computer di destinazione corrente.</span><span class="sxs-lookup"><span data-stu-id="c4367-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="c4367-106">Input</span><span class="sxs-lookup"><span data-stu-id="c4367-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="c4367-107">Località:' t</span><span class="sxs-lookup"><span data-stu-id="c4367-107">location : 'T</span></span>

<span data-ttu-id="c4367-108">Fornisce informazioni sulla posizione in cui generare il dump del computer.</span><span class="sxs-lookup"><span data-stu-id="c4367-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4367-109">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4367-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="c4367-110">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="c4367-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4367-111">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="c4367-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c4367-112">T</span><span class="sxs-lookup"><span data-stu-id="c4367-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c4367-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="c4367-113">Remarks</span></span>

<span data-ttu-id="c4367-114">Questo metodo consente di eseguire il dump delle informazioni sullo stato corrente del computer di destinazione in un file o in un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="c4367-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="c4367-115">Le informazioni effettive generate e la semantica di `location` sono specifiche per ogni computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c4367-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="c4367-116">Tuttavia, se si specifica una tupla vuota come posizione ( `()` ) o semplicemente si omette il parametro, in `location` genere significa generare l'output nella console.</span><span class="sxs-lookup"><span data-stu-id="c4367-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="c4367-117">Per il simulatore di stato completo locale distribuito come parte del quantum Development Kit, questo metodo prevede una stringa con il percorso di un file in cui verrà scritta la funzione Wave come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta le ampiezze della probabilità di misurazione dello stato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c4367-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>