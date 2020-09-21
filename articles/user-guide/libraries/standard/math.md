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
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833607"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i Q# tipi di dati incorporati `Int` , `Double` e `Range` .

L' <xref:microsoft.quantum.intrinsic.random> operazione è firmata `(Double[] => Int)` .
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.
