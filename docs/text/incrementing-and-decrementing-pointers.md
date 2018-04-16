---
title: "インクリメントとデクリメント ポインター |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9eccf65f091c8c5c273f6a65cb7e81b0d386afa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="incrementing-and-decrementing-pointers"></a>ポインターのインクリメントとデクリメント
次のヒントを使用します。  
  
-   先行バイト、いない後続バイトをポイントします。 末尾バイトにポインターを持つ通常安全ではありません。 逆の順序ではなく、順方向に文字列をスキャンすることが通常できます。  
  
-   ポインターのインクリメントまたはデクリメント関数や文字単位を移動するマクロをもあります。  
  
    ```  
    sz1++;  
    ```  
  
     ようになります。  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc`と`_mbsdec`関数正しくインクリメントし、後置デクリメントの`character`文字のサイズに関係なく、単位です。  
  
-   デクリメント、次のように、文字列の先頭へのポインターが必要です。  
  
    ```  
    sz2--;  
    ```  
  
     ようになります。  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     または、ヘッド ポインターが、文字列で、有効な文字になります。 ようにします。  
  
    ```  
    sz2Head < sz2  
    ```  
  
     既知の有効な先行バイトを指すポインターが必要です。  
  
-   高速の呼び出しの前の文字へのポインターを維持することができます`_mbsdec`です。  
  
## <a name="see-also"></a>参照  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [バイト インデックス](../text/byte-indices.md)