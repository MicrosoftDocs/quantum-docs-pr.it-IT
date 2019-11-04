---
title: 'Librerie standard Q #-Math | Microsoft Docs'
description: 'Librerie standard Q #-Math'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184458"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i tipi di dati predefiniti Q # `Int`, `Double`e `Range`.

L'operazione <xref:microsoft.quantum.intrinsic.random> ha `(Double[] => Int)`di firma.
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int`.
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.