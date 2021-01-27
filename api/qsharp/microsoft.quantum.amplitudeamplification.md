---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Spazio dei nomi Microsoft. Quantum. AmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: managed-reference
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: a014f923de62c5e660c1c0fc839fbe60e80f8ba9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845838"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Spazio dei nomi Microsoft. Quantum. AmplitudeAmplification

Questo spazio dei nomi contiene funzioni e operazioni per eseguire l'amplificazione dell'ampiezza.



## <a name="description"></a>Descrizione

L'amplificazione dell'ampiezza ignara con riflessioni parziali è la forma più generale di amplificazione dell'ampiezza implementata

Questo metodo viene chiamato tramite l'operazione AmpAmpObliviousByReflectionPhases.

Sono presenti due registri: `ancillaRegister` e `systemRegister` .

Accetta due Oracle per questi riflessi di tipo `ReflectionOracle` che agiscono solo nel `ancillaRegister` registro.

Questo accetta un Oracle speciale per l'amplificazione dell'ampiezza ignara del tipo `ObliviousOracle` che agisce congiuntamente su entrambi i registri.

Si presuppone che lo stato di input a sia `ancillaRegister` il autostato univoco $-$1 del primo operatore di reflection $I-2 \ KET {s} \ Bra {s} $.

Le riflessioni su uno stato quantum di destinazione vengono spesso implementate supponendo l'accesso a un Oracle che prepara tale stato dalla base computazionale $ \ket{0\cdots 0} $.

La convenzione per questi Oracle richiede due registri: un registro con un solo qubit `flagQubit` e un registro per tutti gli altri elementi nel registro ancillaRegister.

Oracle di tipo `StateOracle` agisce congiuntamente su entrambi i registri per creare lo stato di destinazione contrassegnato da $ \ket {1} $ nel `flagQubit` registro con un'ampiezza reale.

La reflection `ReflectionOracle` relativa a questo stato del flag viene generata dall'operazione `TargetStateReflectionOracle` .

La reflection `ReflectionOracle` sullo stato di input di `ancillaRegister` viene generata dal StateOracle invertente e quindi riflette circa $ \ket{0\cdots 0} $ con ReflectionStart ().

Oracle di tipo `DeterministicStateOracle` agisce sui `qubitState` registri per creare esattamente lo stato di destinazione senza flag.

`AmpAmpObliviousByOraclePhases` è una versione di amplificazione dell'ampiezza ignara che accetta Oracle `StateOracle` e `ObliviousOracle` invece di riflessi.

Si noti che l'amplificazione dell'ampiezza è un caso speciale di amplificazione dell'ampiezza ignara `ObliviousOracle` , dove è l'operatore di identità e non esistono qubits di sistema, ad esempio `systemRegister` è vuoto.

Questo metodo viene chiamato tramite l'operazione `AmpAmByReflectionPhases` e `AmpAmpByOraclePhases` .

Le fasi per le riflessioni parziali nel caso standard di ricerca Grover sono fornite dalla funzione AmpAmpPhasesStandard.

Ad esempio, sono presenti le dipendenze seguenti: AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.