---
title: Matematica nelle Q# librerie standard
description: Informazioni sulle funzioni matematiche classiche nelle Q# librerie standard usate con i tipi di dati incorporati.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853987"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i Q# tipi di dati incorporati `Int` , `Double` e `Range` .

L' <xref:Microsoft.Quantum.Intrinsic.Random> operazione è firmata `(Double[] => Int)` .
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.
