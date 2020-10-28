---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: Tipo definito dall'utente RequiresCapability
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725137"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="165fe-102">Tipo definito dall'utente RequiresCapability</span><span class="sxs-lookup"><span data-stu-id="165fe-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="165fe-103">Spazio dei nomi: [Microsoft. Quantum. targeting](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="165fe-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="165fe-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="165fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="165fe-105">Attributo riconosciuto dal compilatore utilizzato per contrassegnare un oggetto chiamabile con le funzionalità di runtime richieste.</span><span class="sxs-lookup"><span data-stu-id="165fe-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="165fe-106">Elementi denominati</span><span class="sxs-lookup"><span data-stu-id="165fe-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="165fe-107">Livello: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="165fe-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="165fe-108">Nome del livello di funzionalità di runtime richiesto dall'oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="165fe-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="165fe-109">Motivo: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="165fe-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="165fe-110">Descrizione del motivo per cui l'oggetto chiamabile richiede questa funzionalità di Runtime.</span><span class="sxs-lookup"><span data-stu-id="165fe-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="165fe-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="165fe-111">Remarks</span></span>

<span data-ttu-id="165fe-112">Questo attributo viene aggiunto automaticamente a Callable dal compilatore, a meno che non esista già un'istanza di questo attributo nell'oggetto chiamabile.</span><span class="sxs-lookup"><span data-stu-id="165fe-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="165fe-113">Non deve essere usato tranne nei rari casi in cui il compilatore non deduce correttamente la funzionalità richiesta.</span><span class="sxs-lookup"><span data-stu-id="165fe-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="165fe-114">Di seguito è riportato l'elenco dei nomi dei livelli di funzionalità, in ordine di aumento delle funzionalità o delle restrizioni di riduzione:</span><span class="sxs-lookup"><span data-stu-id="165fe-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="165fe-115">Impossibile confrontare i risultati della misurazione per verificarne l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="165fe-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="165fe-116">I risultati della misurazione possono essere confrontati per verificarne l'uguaglianza solo nelle espressioni condizionali if-Statement nelle operazioni.</span><span class="sxs-lookup"><span data-stu-id="165fe-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="165fe-117">Il blocco di un'istruzione If che dipende da un risultato non può contenere istruzioni set per variabili modificabili dichiarate all'esterno del blocco o istruzioni return.</span><span class="sxs-lookup"><span data-stu-id="165fe-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="165fe-118">Nessuna restrizione di Runtime.</span><span class="sxs-lookup"><span data-stu-id="165fe-118">No runtime restrictions.</span></span> <span data-ttu-id="165fe-119">Qualsiasi programma Q # può essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="165fe-119">Any Q# program can be executed.</span></span>