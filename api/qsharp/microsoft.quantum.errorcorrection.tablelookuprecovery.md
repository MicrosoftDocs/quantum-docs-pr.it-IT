---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824406"
---
# <a name="tablelookuprecovery-function"></a>TableLookupRecovery (funzione)

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Per una tabella specificata di operazioni di Pauli in un determinato registro di qubits, questa funzione restituisce un oggetto di tipo `RecoveryFn` che contiene tutte le informazioni necessarie per eseguire una decodifica della ricerca di tabella rispetto alla matrice di operazioni di Pauli specificata.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Input

### <a name="table--pauli"></a>tabella: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Tabella delle operazioni di Pauli che operano su un determinato registro qubit



## <a name="output--recoveryfn"></a>Output: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Oggetto di tipo `RecoveryFn` , ad esempio una mappa `Syndrome -> Pauli[]` che associa a una matrice di sindromi specificata un'operazione di correzione di Pauli corrispondente.