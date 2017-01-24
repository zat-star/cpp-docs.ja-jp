---
title: "文字の代入 | Microsoft Docs"
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
  - "文字 [C++], 代入"
  - "MBCS [C++], 文字の代入"
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# 文字の代入
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次に、`while` ループで文字列をスキャンし、"X" 以外の文字をすべて別の文字列へコピーする場合を考えてみます。  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 このコードでは、`sz2` で示されるバイトを `sz1` が指す場所へコピーし、次のバイトに進めるために `sz1` をインクリメントしています。  ただし、`sz2` の次の文字が 2 バイト文字である場合は、`sz1` への代入では最初のバイトしかコピーされません。  次のコードでは、移植性のある関数を使って文字を安全にコピーし、`sz1` と `sz2` を適切にインクリメントしています。  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## 参照  
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)   
 [文字の比較](../text/character-comparison.md)