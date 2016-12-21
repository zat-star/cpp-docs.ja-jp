---
title: "バイト インデックス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "バイト インデックス [C++]"
  - "MBCS [C++], バイト インデックス"
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# バイト インデックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のヒントを参考にしてください。  
  
-   文字列をバイト単位でインデックスすると、ポインター操作時と同じような問題が生じます。  文字列の中の円記号を探すスキャン例を考えてみます。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     これは、先頭バイトではなく後続バイトのインデックスを作成する場合があります。そのため、`character` を指さない可能性があります。  
  
-   [\_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) 関数を使って上の問題を解決します。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     これは、先行バイトを正しくインデックスするので、実際の文字を正しくインデックスしています。  `_mbclen` 関数は、文字のサイズ \(1 バイトまたは 2 バイト\) を決定します。  
  
## 参照  
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)   
 [文字列の最後の文字](../text/last-character-in-a-string.md)