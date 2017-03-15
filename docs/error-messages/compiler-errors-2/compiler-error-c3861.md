---
title: "コンパイラ エラー C3861 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 177890dcd3ff2abf07f5d9e282efd4a9fd7121a7
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3861"></a>コンパイラ エラー C3861
'identifier': 識別子が見つかりませんでした  
  
コンパイラでは、引数依存の検索を使用しても、識別子への参照を解決できませんでした。  
  
このエラーを修正するには、識別子の宣言で大文字小文字とスペルを確認します。 いることを確認[スコープ解決演算子](../../cpp/scope-resolution-operator.md)と名前空間[ディレクティブを使用して](../../cpp/namespaces-cpp.md#using_directives)が正しく使用します。 識別子がヘッダー ファイルで宣言されている場合は、識別子の参照前にこのヘッダー ファイルがインクルードされていることを確認します。 識別子は除外されていないことを確認しても[条件付きコンパイル ディレクティブ](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)します。  
  
## <a name="example"></a>例  
次の例では C3861 が生成されます。  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>例  
現在、C++ 標準ライブラリの例外クラスは `std` 名前空間にあります。  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```
