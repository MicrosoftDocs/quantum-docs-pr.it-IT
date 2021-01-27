---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Tipo definito dall'utente RequiresCapability
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855142"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="e162d-102">Tipo definito dall'utente RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="e162d-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="e162d-103">Spazio dei nomi: [Microsoft. Quantum. targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="e162d-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="e162d-104">Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e162d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e162d-105">Attributo riconosciuto dal compilatore utilizzato per contrassegnare un oggetto chiamabile con le funzionalità di runtime richieste.</span><span class="sxs-lookup"><span data-stu-id="e162d-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="e162d-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="e162d-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="e162d-107">Livello: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e162d-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e162d-108">Nome del livello di funzionalità di runtime richiesto dall'oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="e162d-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="e162d-109">Motivo: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e162d-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e162d-110">Descrizione del motivo per cui l'oggetto chiamabile richiede questa funzionalità di Runtime.</span><span class="sxs-lookup"><span data-stu-id="e162d-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="e162d-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="e162d-111">Remarks</span></span>

<span data-ttu-id="e162d-112">Questo attributo viene aggiunto automaticamente a Callable dal compilatore, a meno che non esista già un'istanza di questo attributo nell'oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="e162d-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="e162d-113">Non deve essere usato tranne nei rari casi in cui il compilatore non deduce correttamente la funzionalità richiesta.</span><span class="sxs-lookup"><span data-stu-id="e162d-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="e162d-114">Di seguito è riportato l'elenco dei nomi dei livelli di funzionalità, in ordine di aumento delle funzionalità o delle restrizioni di riduzione:</span><span class="sxs-lookup"><span data-stu-id="e162d-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="e162d-115">Impossibile confrontare i risultati della misurazione per verificarne l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="e162d-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="e162d-116">I risultati della misurazione possono essere confrontati per verificarne l'uguaglianza solo nelle espressioni condizionali if-Statement nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="e162d-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="e162d-117">Il blocco di un'istruzione If che dipende da un risultato non può contenere istruzioni set per variabili modificabili dichiarate all'esterno del blocco o istruzioni return.</span><span class="sxs-lookup"><span data-stu-id="e162d-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="e162d-118">Nessuna restrizione di Runtime.</span><span class="sxs-lookup"><span data-stu-id="e162d-118">No runtime restrictions.</span></span> <span data-ttu-id="e162d-119">Qualsiasi programma Q # può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="e162d-119">Any Q# program can be executed.</span></span>