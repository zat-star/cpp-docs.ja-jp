---
title: "文字の比較 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28c2cd3a2e868a595d73d06b5cae8e71ec8cc313
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="character-comparison"></a>文字の比較
次のヒントを使用します。  
  
-   ASCII 文字で既知の先行バイトを比較することは正しく動作します。  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   2 つの不明な文字を比較するには、Mbstring.h で定義されているマクロのいずれかを使用する必要があります。  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     これにより、2 バイト文字の両方のバイトが等しいかどうか比較されます。  
  
## <a name="see-also"></a>参照  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [バッファー オーバーフロー](../text/buffer-overflow.md)