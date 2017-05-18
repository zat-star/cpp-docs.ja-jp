---
title: "コンパイラの警告 (レベル 1) C4917 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
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
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: 43dce460fb336b09ce39d3e4c0e52b43a175ea36
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4917"></a>コンパイラの警告 (レベル 1) C4917
'declarator': GUID だけに関連付けることにより、クラス、インターフェイス、または名前空間  
  
ユーザー定義構造体以外の[クラス](../../cpp/class-cpp.md)、[インターフェイス](../../cpp/interface.md)、または[名前空間](../../cpp/namespaces-cpp.md)GUID を持つことはできません。  
  
既定では、この警告はオフに設定されています。 参照してください[コンパイラの警告ことは既定で無効](../../preprocessor/compiler-warnings-that-are-off-by-default.md)の詳細。  
  
## <a name="example"></a>例  
次のコード サンプルには、C4917 が生成されます。  
  
```cpp  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```
