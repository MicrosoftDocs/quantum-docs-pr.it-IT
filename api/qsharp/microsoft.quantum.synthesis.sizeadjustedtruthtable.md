---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: c53ac3f2c46bca955847fc7b380337e3910390ac
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202924"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Regola la tabella di verità da una matrice di valori booleani in base al numero di variabili

Viene restituita una nuova matrice di lunghezza `2^numVars` , che può richiedere l'estensione delle `table` dimensioni con le `false` voci o il troncamento degli `2^numVars` elementi.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Input

### <a name="table--bool"></a>tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabella di verità come matrice di valori di verità


### <a name="numvars--int"></a>numVars: [int](xref:microsoft.quantum.lang-ref.int)

Numero di variabili



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Ridimensionamento della tabella di verità