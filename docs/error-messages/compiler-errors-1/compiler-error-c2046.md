---
title: "コンパイラ エラー C2046 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2046
dev_langs: C++
helpviewer_keywords: C2046
ms.assetid: f0c8f9dd-dbd7-4c4a-8838-fde54208ec71
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 39f85239298b554e62fd525c8020f65c0e94a831
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2046"></a>コンパイラ エラー C2046
'case' が正しくありません。  
  
 キーワード `case` は `switch` ステートメントでのみ使用できます。  
  
 次の例では C2046 エラーが生成されます。  
  
```  
// C2046.cpp  
int main() {  
   case 0:   // C2046  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2046b.cpp  
int main() {  
   int i = 0;  
  
   switch(i) {  
      case 0:  
      break;  
  
      default:  
      break;  
   }  
}  
```