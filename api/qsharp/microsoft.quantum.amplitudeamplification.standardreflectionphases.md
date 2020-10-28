---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721735"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases (funzione)

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto [](https://nuget.org/packages/)


Calcola le fasi di Reflection parziali per l'amplificazione dell'ampiezza standard.

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>Input

### <a name="niterations--int"></a>nIterations: [int](xref:microsoft.quantum.lang-ref.int)

Numero di iterazioni di amplificazione dell'ampiezza per generare fasi di Reflection parziali per.



## <a name="output--reflectionphases"></a>Output: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Operazione che implementa le fasi specificate come riflessioni parziali

## <a name="remarks"></a>Commenti

Tutte le fasi sono $ \Pi $, ad eccezione della prima Reflection sullo stato di avvio e dell'ultima Reflection sullo stato di destinazione, ovvero $0 $.