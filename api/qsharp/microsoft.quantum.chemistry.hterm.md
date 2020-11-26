---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Tipo definito dall'utente HTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204131"
---
# <a name="hterm-user-defined-type"></a>Tipo definito dall'utente HTerm

Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Formato dei dati passati da C# a Q # per rappresentare un termine dell'hamiltoniana.
Il significato dei dati rappresentati è determinato dall'algoritmo che lo riceve.

```qsharp

newtype HTerm = (Int[], Double[]);
```

