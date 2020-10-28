---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712130"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="c9bdb-102">SteaneCodeRecoveryX (funzione)</span><span class="sxs-lookup"><span data-stu-id="c9bdb-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="c9bdb-103">Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c9bdb-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c9bdb-104">Pacchetto [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9bdb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9bdb-105">Decodificatore per la parte X del gruppo stabilizzatore del codice Quantum Steane 7, 1, 3 ⟧ di ⟦.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="c9bdb-106">Input</span><span class="sxs-lookup"><span data-stu-id="c9bdb-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="c9bdb-107">Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="c9bdb-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="c9bdb-108">Matrice di sindromi ottenuta dalla misurazione della parte X dello stabilizzatore.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="c9bdb-109">Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="c9bdb-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="c9bdb-110">Matrice di operazioni di Pauli che, quando applicato al sistema quantistico codificato, corregge l'errore corrispondente a `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="c9bdb-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9bdb-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="c9bdb-111">Remarks</span></span>

<span data-ttu-id="c9bdb-112">Il decodificatore scelto usa la proprietà del codice CSS del codice Steane ⟧ ⟦ 7, 1, 3, ovvero corregge gli errori X e Z separatamente.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="c9bdb-113">Una proprietà del codice è che la posizione della X, rispettivamente, della correzione Z da applicare è la codifica a 3 bit della sindrome X, rispettivamente, Z quando viene considerato un numero intero.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="c9bdb-114">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c9bdb-114">References</span></span>

- <span data-ttu-id="c9bdb-115">D.</span><span class="sxs-lookup"><span data-stu-id="c9bdb-115">D.</span></span> <span data-ttu-id="c9bdb-116">Gottesman, "codici stabilizzatori e correzione errori Quantum", Ph.D. tesi, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="c9bdb-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="c9bdb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9bdb-117">See Also</span></span>

- [<span data-ttu-id="c9bdb-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="c9bdb-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="c9bdb-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="c9bdb-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)