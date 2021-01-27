---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: Tipo definito dall'utente ReflectionPhases
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: fc3642b76c6e01f0709e78ea42c9ea7237389afa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847175"
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

## <a name="remarks"></a>Commenti

Entrambe le matrici devono essere di uguale lunghezza. Si noti che in molti casi, la prima fase sullo stato di avvio e l'ultima fase sullo stato di destinazione introduce un cambio di fase globale e può essere impostato su $0 $.