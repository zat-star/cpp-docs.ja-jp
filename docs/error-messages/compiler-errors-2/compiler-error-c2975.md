---
title: "コンパイラ エラー C2975 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 07b2b96cd79364215c9a859a9fd0282768ff45e4
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2975"></a>コンパイラ エラー C2975
'arg': 無効なテンプレート引数を 'type'、予期されるコンパイル時の定数式  
  
 テンプレート引数が、テンプレート宣言と一致しません山かっこ内の定数式が表示されます。 変数は、テンプレートの実引数としては許可されません。 テンプレートの定義を調べて正しい型が指定されていることをご確認ください。  
  
 次の例では、C2975 が生成されます。  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 __LINE を使用する場合にも C2975 が発生\_\_コンパイル時定数として[/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)です。 1 つのソリューションは、使用してコンパイルすること[/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)の代わりに**/ZI**です。  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```
