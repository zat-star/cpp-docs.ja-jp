---
title: "文字の代入 |Microsoft ドキュメント"
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
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 266d3284716647fa073f76ef6ef871a3abd179bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="character-assignment"></a>文字の代入
これで、次の例を検討してください、`while`ループが別の文字列に 'X' 以外のすべての文字のコピー、文字列をスキャンします。  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 コードでは、位置のバイトをコピーする`sz2`によって示される場所に`sz1`、インクリメントし、`sz1`を次のバイトを受信します。 場合の次の文字`sz2`2 バイト文字への割り当ては、`sz1`最初のバイトのみをコピーします。 次のコードを使用してポータブル関数の文字を安全にコピーするもう 1 つをインクリメントする`sz1`と`sz2`正しく。  
  
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
  
## <a name="see-also"></a>参照  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [文字の比較](../text/character-comparison.md)