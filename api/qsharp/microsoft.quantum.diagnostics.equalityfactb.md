---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829212"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="63302-102">EqualityFactB (funzione)</span><span class="sxs-lookup"><span data-stu-id="63302-102">EqualityFactB function</span></span>

<span data-ttu-id="63302-103">Spazio dei nomi: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="63302-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="63302-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63302-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63302-105">Dichiara che una variabile bool classica presenta il valore previsto.</span><span class="sxs-lookup"><span data-stu-id="63302-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="63302-106">Input</span><span class="sxs-lookup"><span data-stu-id="63302-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="63302-107">effettivo: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63302-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63302-108">Variabile da verificare.</span><span class="sxs-lookup"><span data-stu-id="63302-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="63302-109">previsto: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63302-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63302-110">Valore previsto.</span><span class="sxs-lookup"><span data-stu-id="63302-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="63302-111">messaggio: [stringa](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="63302-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="63302-112">Stringa del messaggio di errore da utilizzare quando viene attivata l'asserzione.</span><span class="sxs-lookup"><span data-stu-id="63302-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63302-113">Output: [unità](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63302-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

