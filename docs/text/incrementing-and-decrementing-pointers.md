---
title: "ポインターのインクリメントとデクリメント | Microsoft Docs"
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
  - "デクリメント (ポインターを)"
  - "インクリメント (ポインターを)"
  - "MBCS [C++], ポインター"
  - "ポインター [C++], マルチバイト文字"
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# ポインターのインクリメントとデクリメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のヒントを参考にしてください。  
  
-   後続バイトではなく、常に先行バイトを指すようにします。  後続バイトへのポインターを持つことは危険です。  通常は、逆方向からではなく、順方向に文字列スキャンを行うようにします。  
  
-   文字単位でポインター値を増減できる、インクリメント\/デクリメント関数とマクロが用意されています。  
  
    ```  
    sz1++;  
    ```  
  
     上のコードは、次のようになります。  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc` 関数と `_mbsdec` 関数は、文字のバイト サイズとは無関係に、あくまで "`character` 単位" で正しくポインターを増減させます。  
  
-   次に示すように、デクリメントには文字列の先頭へのポインターが必要になります。  
  
    ```  
    sz2--;  
    ```  
  
     上のコードは、次のようになります。  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     または、次のように文字列の中の有効文字を先頭ポインターとすることができます。  
  
    ```  
    sz2Head < sz2  
    ```  
  
     先行バイトへの有効なポインターが必要です。  
  
-   前の文字へのポインターを保持しておいた方が `_mbsdec` への呼び出しが速くなる場合があります。  
  
## 参照  
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)   
 [バイト インデックス](../text/byte-indices.md)