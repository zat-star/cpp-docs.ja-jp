---
title: "アドレスの格納 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- storage [C++], addresses
- addresses [C++], storage of
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 78ed46fc8412f351d46d3a2b4c37348382d7aaa5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="storage-of-addresses"></a>アドレスの格納
アドレスに必要なストレージの量およびアドレスの意味は、コンパイラの実装によって異なります。 異なる型へのポインターが同じ長さを持つという保証はありません。 したがって、**sizeof(char \*)** は **sizeof(int \*)** と必ずしも同じではありません。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft C コンパイラでは、**sizeof(char \*)** は **sizeof(int \*)** と同じです。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [ポインター宣言](../c-language/pointer-declarations.md)
