---
title: "コンパイラ エラー C2443 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2443
dev_langs:
- C++
helpviewer_keywords:
- C2443
ms.assetid: 315330d5-24bc-4193-a531-0642095be58f
caps.latest.revision: 8
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
ms.openlocfilehash: 5ded9feffed54fc9efa4909a0bf4ef1bdf630a7b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2443"></a>コンパイラ エラー C2443
この命令には同じサイズのオペランドが必要です。  
  
 命令では、オペランドは同じサイズである必要があります。  
  
 次の例では、c2443 エラーが生成されます。  
  
```  
// C2443.cpp  
// processor: x86  
short var;  
int main() {  
   __asm xchg ax,bl   // C2443  
   __asm mov al,red   // C2443  
   __asm mov al,BYTE PTR var   // OK  
}  
```
