---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definito dall'utente ReflectionPhases
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191347"
---
# <a name="reflectionphases-user-defined-type"></a>Tipo definito dall'utente ReflectionPhases

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fasi per una sequenza di riflessioni parziali nell'amplificazione dell'ampiezza.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Elementi denominati

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di fasi per la reflection sullo stato di avvio.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di fasi per la reflection sullo stato di destinazione.

## <a name="remarks"></a>Osservazioni

Entrambe le matrici devono essere di uguale lunghezza. Si noti che in molti casi, la prima fase sullo stato di avvio e l'ultima fase sullo stato di destinazione introduce un cambio di fase globale e può essere impostato su $0 $.