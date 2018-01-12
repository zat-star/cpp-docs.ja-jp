---
title: "コンパイラの警告 (レベル 3) C4101 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4101
dev_langs: C++
helpviewer_keywords: C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 162ad70f6d87ba6de51f677d95f1af7c1b6d8054
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4101"></a>コンパイラの警告 (レベル 3) C4101
'identifier': 参照されていないローカル変数  
  
 ローカル変数は使用されません。 この警告は、明らかな場合に発生します。  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 ただし、この警告がまた発生を呼び出すときに、**静的**メンバー関数は、クラスのインスタンスを経由します。  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 コンパイラはこのような状況で、に関する情報を使用して`si`にアクセスする、**静的**関数がクラスのインスタンスを呼び出すには必要ありません、**静的**関数です。 そのため、警告します。 この警告を解決するのには、次のことができます。  
  
-   インスタンス、コンパイラが使用して、コンス トラクターを追加`si`への呼び出しで`func`です。  
  
-   削除、**静的**キーワードの定義から`func`です。  
  
-   呼び出す、**静的**明示的に関数:`int y = S::func();`です。