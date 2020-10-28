---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Operazione selezionerò
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718458"
---
# <a name="applyand-operation"></a>Operazione selezionerò

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Inverte un qubit di destinazione specificato se e solo se entrambi i qubits di controllo si trovano nello stato 1, usando la misurazione per eseguire l'operazione contigua.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Inverte `target` se e solo se entrambi i controlli sono pari a 1, ma presuppone che `target` si trovi nello stato 0.  L'operazione ha T-Count 4, T-Depth 2 e non richiede qubit helper e può pertanto essere preferibile a un'operazione CCNOT, se `target` è noto come 0.  Il contiguo di questa operazione è basato sulla misurazione e non richiede alcun controllo T.

Per l'applicazione controllata di questa operazione non è richiesto alcun supporto qubit, `2^c` `Rz` Gates e non è ottimizzato per la profondità, dove `c` è il numero di qubits del controllo complessivo, inclusi i due controlli dell' `ApplyAnd` operazione.  L'applicazione controllata contigua richiede i controlli `2^c - 1` `Rz` (con un angolo doppio della dimensione dell'operazione non contigua), nessun helper qubit e non è ottimizzato per la profondità.

## <a name="input"></a>Input

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Primo controllo qubit


### <a name="control2--qubit"></a>controllo2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Secondo qubit di controllo


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ausiliari di destinazione; deve essere nello stato 0



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- Cody Jones: "costruzioni innovative per il controllo Toffoli A tolleranza di errore", fisico. Rev. A 87, 022328, 2013 [arXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328
- Craig Gidney: "dimezzando il costo di aggiunta Quantum", Quantum 2, pagina 74, 2018 [arXiv: 1709.06648](https://arxiv.org/abs/1709.06648) DOI: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "Quantum Oracle Circuits and the Christmas Tree pattern", [articolo del Blog del 19 dicembre 2019](https://msoeken.github.io/blog_qac.html) (Nota: spiega la costruzione a più controlli)