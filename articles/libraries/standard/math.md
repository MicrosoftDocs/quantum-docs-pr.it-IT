---
title: 'Math nelle librerie standard Q #'
description: 'Informazioni sulle funzioni matematiche classiche nelle librerie standard Q # usate con i tipi di dati incorporati.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906152"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i tipi di dati predefiniti Q # `Int`, `Double`e `Range`.

L'operazione <xref:microsoft.quantum.intrinsic.random> ha `(Double[] => Int)`di firma.
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int`.
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.
