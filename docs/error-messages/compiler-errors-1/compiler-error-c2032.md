---
title: "コンパイラ エラー C2032 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2032
dev_langs: C++
helpviewer_keywords: C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 81bbe4c9e5242f68a5e0e304858c13c9274c1743
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2032"></a>コンパイラ エラー C2032
'identifier': 関数 'structorunion' の構造体/共用体のメンバーであることはできません  
  
 構造体または共用体が C ではありませんが、C++ では許可されているメンバー関数エラーを解決するには、C++ プログラムとしてコンパイルするか、メンバー関数を削除します。  
  
 次の例では、C2032 が生成されます。  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 考えられる解決策:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```