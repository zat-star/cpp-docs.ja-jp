---
title: "コンパイラの警告 (レベル 3) C4390 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: dd04b9faa2ed1376b821dedb6270950e1b035df5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4390"></a>コンパイラの警告 (レベル 3) C4390
';' : 制御が空の文が見つかりました。意図した記述でしょうか?  
  
 指示が含まれていない制御ステートメントの後にセミコロンが見つかりました。  
  
 使用する必要があります C4390 マクロが原因で発生した場合、[警告](../../preprocessor/warning.md)プラグマ マクロを含むモジュールで C4390 を無効にします。  
  
 次の例では、C4390 が生成されます。  
  
```  
// C4390.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
   if (i);   // C4390  
      i++;  
}  
```
