---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 9623d6d881f1f0ec048c3a951fe259bdfac84766
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202023"
---
# <a name="dumpregister-function"></a><span data-ttu-id="f8389-102">DumpRegister (funzione)</span><span class="sxs-lookup"><span data-stu-id="f8389-102">DumpRegister function</span></span>

<span data-ttu-id="f8389-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f8389-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f8389-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f8389-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f8389-105">Scarica lo stato del computer di destinazione corrente associato al qubits specificato.</span><span class="sxs-lookup"><span data-stu-id="f8389-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="f8389-106">Input</span><span class="sxs-lookup"><span data-stu-id="f8389-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="f8389-107">Località:' t</span><span class="sxs-lookup"><span data-stu-id="f8389-107">location : 'T</span></span>

<span data-ttu-id="f8389-108">Fornisce informazioni sulla posizione in cui generare il dump dello stato.</span><span class="sxs-lookup"><span data-stu-id="f8389-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="f8389-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f8389-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f8389-110">Elenco di qubits da segnalare.</span><span class="sxs-lookup"><span data-stu-id="f8389-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8389-111">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8389-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="f8389-112">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="f8389-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f8389-113">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f8389-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8389-114">T</span><span class="sxs-lookup"><span data-stu-id="f8389-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f8389-115">Commenti</span><span class="sxs-lookup"><span data-stu-id="f8389-115">Remarks</span></span>

<span data-ttu-id="f8389-116">Questo metodo consente di eseguire il dump delle informazioni associate allo stato del qubits specificato in un file o in un altro percorso.</span><span class="sxs-lookup"><span data-stu-id="f8389-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="f8389-117">Le informazioni effettive generate e la semantica di `location` sono specifiche per ogni computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f8389-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="f8389-118">Tuttavia, se si specifica una tupla vuota come posizione ( `()` ), in genere viene generato l'output nella console.</span><span class="sxs-lookup"><span data-stu-id="f8389-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="f8389-119">Per il simulatore di stato completo locale distribuito come parte del quantum Development Kit, questo metodo prevede una stringa con il percorso di un file in cui scriverà lo stato del qubits specificato (ovvero la funzione Wave del sottosistema corrispondente) come matrice unidimensionale di numeri complessi, in cui ogni elemento rappresenta le ampiezze della probabilità di misurazione dello stato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f8389-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="f8389-120">Se i qubits specificati sono associati ad altri qubit e il relativo stato non può essere separato, viene semplicemente segnalato che i qubits sono aggrovigliati.</span><span class="sxs-lookup"><span data-stu-id="f8389-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>