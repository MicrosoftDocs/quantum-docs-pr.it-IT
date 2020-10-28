---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712183"
---
# <a name="steanecode-function"></a><span data-ttu-id="60c80-102">SteaneCode (funzione)</span><span class="sxs-lookup"><span data-stu-id="60c80-102">SteaneCode function</span></span>

<span data-ttu-id="60c80-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="60c80-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="60c80-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60c80-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60c80-105">Restituisce un valore CSS che rappresenta il codificatore di codice Steane ⟦ 7, 1, 3 ⟧ e il decodificatore con misurazione della sindrome sul posto.</span><span class="sxs-lookup"><span data-stu-id="60c80-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="60c80-106">Output: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="60c80-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="60c80-107">Oggetto di tipo CSS che raccoglie tutti i dati rilevanti per eseguire la codifica e la correzione degli errori per il codice Steane ⟧ ⟦ 7, 1, 3.</span><span class="sxs-lookup"><span data-stu-id="60c80-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="60c80-108">Commenti</span><span class="sxs-lookup"><span data-stu-id="60c80-108">Remarks</span></span>

<span data-ttu-id="60c80-109">Questo codice è stato trovato nel documento seguente:</span><span class="sxs-lookup"><span data-stu-id="60c80-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="60c80-110">A.</span><span class="sxs-lookup"><span data-stu-id="60c80-110">A.</span></span> <span data-ttu-id="60c80-111">Steane, "interferenza di più particelle e correzione degli errori quantistici", proc.</span><span class="sxs-lookup"><span data-stu-id="60c80-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="60c80-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="60c80-112">Roy.</span></span> <span data-ttu-id="60c80-113">Soc. Lond.</span><span class="sxs-lookup"><span data-stu-id="60c80-113">Soc. Lond.</span></span> <span data-ttu-id="60c80-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="60c80-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>