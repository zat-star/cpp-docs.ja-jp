---
title: "コンパイラ エラー C2390 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 37803b8eb5034fb3281dcea385b4a0fca462aaf0
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2390"></a>コンパイラ エラー C2390
'identifier': 'specifier' のストレージ クラス  
  
 グローバル スコープ識別子のストレージ クラスが正しくありません。 既定のストレージ クラスは、無効なクラスの代わりに使用されます。  
  
 考えられる解決策:  
  
-   識別子が関数の場合は、宣言で`extern`記憶域。  
  
-   識別子は、仮パラメーターまたはローカル変数には、自動ストレージで宣言します。  
  
-   識別子がグローバル変数の場合は、ストレージ クラスが存在しません (自動ストレージ) を宣言します。  
  
## <a name="example"></a>例  
  
-   次の例では、C2390 が生成されます。  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```
