---
title: "最後の文字列の文字 |Microsoft ドキュメント"
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
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7b766bec977f35f9f346723cbaf3f62e48c8c878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="last-character-in-a-string"></a>文字列の最後の文字
次のヒントを使用します。  
  
-   後続バイトの範囲では、ASCII 文字セットで多くの場合と重複します。 すべての制御文字 (32 未満) のバイト単位のスキャンを安全に使用できます。  
  
-   文字列の最後の文字は、円記号かどうかをチェックしたり、コードの次の行を考慮してください。  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     `strlen`は MBCS を認識しないマルチバイト文字列で、文字の数ではなくバイト単位の数を返します。 また、なおいくつかのコード ページ (932 など)、'\\' (0x5c) が有効な末尾バイト (`sz` C 文字列です)。  
  
     1 つの考えられる解決方法は、この方法でコードを書き換えるには。  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     このコードは、MBCS の関数を使用して`_mbsrchr`と`_mbsinc`です。 これらの関数が MBCS に対応するため、それらを区別できる、'\\'文字と末尾バイト'\\' です。 コードは、文字列の最後の文字が null ('\0') の場合に、何らかのアクションを実行します。  
  
## <a name="see-also"></a>参照  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [文字の代入](../text/character-assignment.md)