---
title: "コンパイラ エラー C3290 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3290
dev_langs: C++
helpviewer_keywords: C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28f350f8cf522032fbdaad22098508ec8545ee01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3290"></a>コンパイラ エラー C3290
'type': trivial プロパティに参照型を含めることはできません。  
  
 プロパティが正しく宣言されませんでした。 trivial プロパティを宣言すると、コンパイラは、プロパティが更新する変数を作成します。クラスに追跡参照変数を指定することはできません。  
  
 参照してください[プロパティ](../../windows/property-cpp-component-extensions.md)と[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C3290 が生成されます。  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```