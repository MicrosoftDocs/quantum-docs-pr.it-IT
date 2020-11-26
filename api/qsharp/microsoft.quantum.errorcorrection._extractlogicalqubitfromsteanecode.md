---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: Operazione _ExtractLogicalQubitFromSteaneCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201343"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>Operazione _ExtractLogicalQubitFromSteaneCode

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Misurazione della sindrome e inverso dell'incorporamento.

$X $-e $Z $-stabilizzatori non vengono considerati equamente, a causa della scelta particolare del circuito di codifica.
Questa asimmetria conduce a una routine di estrazione della sindrome diversa.
Uno può misurare la sindrome misurando l'operatore Pauli multiqubit direttamente sullo stato del codice, ma per lo scopo della distillazione il qubit logico viene restituito in un singolo qubit, in cui le misurazioni di sindrome possono essere eseguite senza ulteriori ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Input

### <a name="code--logicalregister"></a>Codice: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Il qubit logico e una coppia di numeri interi per $X $-Syndrome e $Z $-Syndrome.
Rappresentano l'indice del qubit del codice in cui un singolo $X $-o $Z $-Error avrebbe causato la sindrome misurata.

## <a name="remarks"></a>Commenti

Si noti che questa operazione non è contrassegnata come `internal` , perché gli unit test dipendono direttamente da questa operazione. Come miglioramento futuro, è necessario effettuare il refactoring degli unit test in modo che dipendano direttamente dai chiamanti pubblici.

> [!WARNING]
> Questa routine è adattata a un particolare circuito di codifica per il codice qubit 7 di Steane; Se il circuito di codifica viene modificato, il risultato della sindrome potrebbe essere interpretato in modo diverso.