---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definito dall'utente ReflectionPhases
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: e0c7db6cd1aad636a34684958be117de1b9888f8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721819"
---
# <a name="reflectionphases-user-defined-type"></a>Tipo definito dall'utente ReflectionPhases

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto [](https://nuget.org/packages/)


Fasi per una sequenza di riflessioni parziali nell'amplificazione dell'ampiezza.

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a>Elementi denominati

### <a name="aboutstart--double"></a>AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di fasi per la reflection sullo stato di avvio.
### <a name="abouttarget--double"></a>AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di fasi per la reflection sullo stato di destinazione.

## <a name="remarks"></a>Commenti

Entrambe le matrici devono essere di uguale lunghezza. Si noti che in molti casi, la prima fase sullo stato di avvio e l'ultima fase sullo stato di destinazione introduce un cambio di fase globale e può essere impostato su $0 $.