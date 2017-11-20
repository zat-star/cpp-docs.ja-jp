---
title: "アドレスの格納 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3d0e996ac191ba3091925a85937e7636a2425215
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="storage-of-addresses"></a>アドレスの格納
アドレスに必要なストレージの量およびアドレスの意味は、コンパイラの実装によって異なります。 異なる型へのポインターが同じ長さを持つという保証はありません。 したがって、**sizeof(char \*)** は **sizeof(int \*)** と必ずしも同じではありません。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft C コンパイラでは、**sizeof(char \*)** は **sizeof(int \*)** と同じです。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [ポインター宣言](../c-language/pointer-declarations.md)