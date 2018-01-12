---
title: "コンパイラ エラー C2390 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2390
dev_langs: C++
helpviewer_keywords: C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93d4cbd9de274d53fdc0369c2b85dbf2e97af48f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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