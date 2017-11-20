---
title: "バイト インデックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: ec28ce5e577fe4d1e766934095d22a7e64a6a3da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="byte-indices"></a>バイト インデックス
次のヒントを使用します。  
  
-   バイト単位でインデックスの操作を文字列には、ポインター操作と同様の問題を表示します。 この例では、円記号の文字列をスキャンを考慮してください。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     末尾バイト、先行バイトではありません、このインデックスを可能性があり、したがって可能性がありますいないを指している、`character`です。  
  
-   使用して、 [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)上記の問題を解決する関数。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     これは、正しくため先行バイトにインデックスを作成する、`character`です。 `_mbclen`関数 (1 つまたは 2 バイト) 文字のサイズが決まります。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [文字列の最後の文字](../text/last-character-in-a-string.md)