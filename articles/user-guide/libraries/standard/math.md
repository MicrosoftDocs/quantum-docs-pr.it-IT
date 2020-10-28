---
title: Matematica nelle Q# librerie standard
description: Informazioni sulle funzioni matematiche classiche nelle Q# librerie standard usate con i tipi di dati incorporati.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692062"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i Q# tipi di dati incorporati `Int` , `Double` e `Range` .

L' <xref:Microsoft.Quantum.Intrinsic.Random> operazione è firmata `(Double[] => Int)` .
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.
