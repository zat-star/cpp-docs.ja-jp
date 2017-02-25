---
title: "バッファー オーバーフロー | Microsoft Docs"
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
  - "バッファー オーバーフロー [C++]"
  - "バッファー [C++], 文字サイズ"
  - "MBCS [C++], バッファー オーバーフロー"
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# バッファー オーバーフロー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字のサイズが異なると、文字をバッファーへ入れるときに問題となります。  文字列 `sz` から文字をバッファー `rgch` へコピーする次のコードを考えてみます。  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 問題は、最後にコピーされたバイトが先行バイトかどうかということです。  次のコードはバッファーをオーバーフローする可能性があるため、この問題は解決されません。  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy` 呼び出しは、1 バイトか 2 バイトかに関係なく、文字全体をコピーするため、正しく動作するように見えます。  しかし、コピーされる最後の文字が 2 バイトの場合に最後の文字がバッファーに入らなくなる可能性については考慮されていません。  その点を解決するには次のようにします。  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 このコードは、`_mbclen` を使って `sz` が指す現在の文字のサイズを調べることにより、ループ テストでバッファーのオーバーフローをテストしています。  `_mbsnbcpy` 関数を呼び出すことにより、`while` ループのコードを 1 行のコードで置き換えることができます。  たとえば、次のようになります。  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## 参照  
 [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)