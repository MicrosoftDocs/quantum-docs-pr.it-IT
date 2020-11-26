---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200476"
---
# <a name="steanecode-function"></a><span data-ttu-id="dbe8e-102">SteaneCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="dbe8e-102">SteaneCode function</span></span>

<span data-ttu-id="dbe8e-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="dbe8e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="dbe8e-104">Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbe8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbe8e-105">Restituisce un valore CSS che rappresenta il codificatore di codice Steane ⟦ 7, 1, 3 ⟧ e il decodificatore con misurazione della sindrome sul posto.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="dbe8e-106">Output: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="dbe8e-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="dbe8e-107">Oggetto di tipo CSS che raccoglie tutti i dati rilevanti per eseguire la codifica e la correzione degli errori per il codice Steane ⟧ ⟦ 7, 1, 3.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbe8e-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="dbe8e-108">Remarks</span></span>

<span data-ttu-id="dbe8e-109">Questo codice è stato trovato nel documento seguente:</span><span class="sxs-lookup"><span data-stu-id="dbe8e-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="dbe8e-110">R.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-110">A.</span></span> <span data-ttu-id="dbe8e-111">Steane, "interferenza di più particelle e correzione degli errori quantistici", proc.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="dbe8e-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-112">Roy.</span></span> <span data-ttu-id="dbe8e-113">Soc. Lond.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-113">Soc. Lond.</span></span> <span data-ttu-id="dbe8e-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="dbe8e-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>