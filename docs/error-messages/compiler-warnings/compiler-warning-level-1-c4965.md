---
title: "コンパイラの警告 (レベル 1) C4965 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4965
dev_langs:
- C++
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: 14
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
ms.openlocfilehash: 53ed24bf928a971d1a315af73fa01b786da8958e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4965"></a>コンパイラの警告 (レベル 1) C4965
整数 0 の暗黙的なボックスです。nullptr または明示的なキャストを使用してください  
  
 Visual C では、値型の暗黙のボックス化を備えています。 C++ マネージ拡張を使用すると、今すぐ null 割り当てを発生させた命令をボックス化された int に代入になります  
  
 詳細については、次を参照してください。[ボックス化](../../windows/boxing-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では、c4965 エラーを生成します。  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```
