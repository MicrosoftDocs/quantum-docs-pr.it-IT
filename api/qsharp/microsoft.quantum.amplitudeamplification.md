---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Spazio dei nomi Microsoft. Quantum. AmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: 09c29bd9d0648bb8652051ad97ceca6ef6557df3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721847"
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