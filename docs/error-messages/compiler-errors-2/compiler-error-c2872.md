---
title: "コンパイラ エラー C2872 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
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
ms.openlocfilehash: d53dbd9429ba3c1a525b85a3ef9f2e70152ddfa2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2872"></a>コンパイラ エラー C2872
'symbol': あいまいなシンボル  
  
コンパイラを参照する記号を判断できません。  
  
C2872 エラーは、ヘッダー ファイルが含まれている場合に発生することが、[ディレクティブを使用して](../../cpp/namespaces-cpp.md#using_directives)、後続のヘッダー ファイルが含まれており、またで指定された名前空間内にある型が含まれていると、`using`ディレクティブです。 指定する`using`とヘッダー ファイルが指定されているすべての後のみディレクティブ`#include`します。  
  
 C2872 エラーの詳細については、サポート技術情報の記事を参照してください。 [PRB: コンパイラ エラー時に使用する #import Visual c .NET で XML を](http://support.microsoft.com/kb/316317)と["エラー C2872: 'プラットフォーム': あいまいなシンボル"Visual Studio 2013 で Windows::Foundation::Metadata 名前空間を使用すると、エラー メッセージ](https://support.microsoft.com/kb/2890859)します。  
  
## <a name="example"></a>例  
 次の例では、c2872 エラーが生成されます。  
  
```cpp  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```
