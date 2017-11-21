---
title: "コンパイラ エラー C3530 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3530
dev_langs: C++
helpviewer_keywords: C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d66e76fc3e44a037f52aa6e217fae848f1338d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3530"></a>コンパイラ エラー C3530
'auto' は、その他の型指定子と組み合わせることはできません。  
  
 型指定子を使用、`auto`キーワード。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  使用する変数宣言で型指定子を使用しない、`auto`キーワード。  
  
## <a name="example"></a>例  
 次の例では C3530 のため変数`x`が両方で宣言されて、`auto`キーワードと型`int`、例をコンパイルしたため、 **/Zc:auto**です。  
  
```  
// C3530.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto int x;   // C3530  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)