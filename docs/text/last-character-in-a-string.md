---
title: "文字列の最後の文字 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "最後の文字 (文字列の)"
  - "MBCS [C++], 最後の文字 (文字列の)"
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# 文字列の最後の文字
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のヒントを参考にしてください。  
  
-   後続バイトの範囲は、多くの場合、ASCII 文字セットとオーバーラップしています。  ただし、制御文字 \(32 未満\) は、問題なくバイトごとにスキャンできます。  
  
-   文字列の最後の文字が円記号文字かどうかを調べる次のコード行について考えてみます。  
  
    ```  
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?  
        // . . .  
    ```  
  
     `strlen` は MBCS を認識しないため、マルチバイト文字列では、文字数ではなくバイト数が返されます。  またコード ページ \(932 など\) では、"\\" \(0x5c\) が有効な後続バイトになることもあります \(`sz` は C 文字列\)。  
  
     対策の 1 つとしては、コードを次のように記述し直します。  
  
    ```  
    char *pLast;  
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz  
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )  
        // . . .  
    ```  
  
     このコードでは、MBCS 関数の `_mbsrchr` と `_mbsinc` を使っています。  これらの関数は、MBCS を認識できるので、"\\" 文字と後続バイトの "\\" とを区別します。  文字列の最後の文字が null \("\\0"\) の場合でも、コードはなんらかの動作をします。  
  
## 参照  
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)   
 [文字の代入](../text/character-assignment.md)