---
title: "コンパイラの警告 (レベル 4) C4565 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 70b0311ff02fc9c5fb2b06005a639d0a3dca21e4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4565"></a>コンパイラの警告 (レベル 4) C4565
'function': 再定義します。シンボルが以前に宣言された __declspec(modifier) と  
  
 2 番目の定義または宣言の最初の定義または宣言とは異なり、ありませんでしたシンボルが再定義または再宣言され、`__declspec`修飾子 (***修飾子***)。 これは、情報提供の警告です。 この警告を解決するには、いずれかの定義を削除します。  
  
 次の例では、C4565 が生成されます。  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```
