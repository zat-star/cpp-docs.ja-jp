---
title: "コンパイラの警告 (レベル 1) C4917 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4917
dev_langs: C++
helpviewer_keywords: C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37849850c89f8c02726b730fbdbabed66bd849b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4917"></a>コンパイラの警告 (レベル 1) C4917
'declarator': GUID はクラス、インターフェイスまたは名前空間に関連付けできます。  
  
以外のユーザー定義の構造[クラス](../../cpp/class-cpp.md)、[インターフェイス](../../cpp/interface.md)、または[名前空間](../../cpp/namespaces-cpp.md)GUID を持つことはできません。  
  
既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
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