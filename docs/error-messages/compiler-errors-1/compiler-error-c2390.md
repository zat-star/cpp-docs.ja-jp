---
title: "コンパイラ エラー C2390 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: 9
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8334477aef71e8f698bb70a48218c4b4b6c5ce0b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2390"></a>コンパイラ エラー C2390
'identifier': ストレージ クラス '指定子'  
  
 グローバル スコープ識別子のストレージ クラスが正しくありません。 既定のストレージ クラスは、無効なクラスの代わりに使用されます。  
  
 考えられる解決方法:  
  
-   識別子が関数の場合は、宣言で`extern`ストレージです。  
  
-   識別子は、仮パラメーターまたはローカル変数には、自動ストレージで宣言します。  
  
-   識別子が、グローバル変数の場合は、ストレージ クラスが存在しません (自動ストレージ) を宣言します。  
  
## <a name="example"></a>例  
  
-   次の例では、c2390 エラーが生成されます。  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```
