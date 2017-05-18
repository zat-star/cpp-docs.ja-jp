---
title: "コンパイラ エラー C2032 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f1079979099dbf3b12e81a9b736faa40e8e4d8d8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2032"></a>コンパイラ エラー C2032
'identifier': 関数は 'structorunion' の構造体/共用体のメンバーであることはできません  
  
 構造体または共用体が C. ではなく C++ では許可されているメンバー関数エラーを解決するには、C + + プログラムとしてコンパイルするか、メンバー関数を削除します。  
  
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
