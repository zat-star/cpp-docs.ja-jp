---
title: "コンパイラの警告 (レベル 4) c4634 警告 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4634
dev_langs:
- C++
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4f2812675fd47c72bc0825f9afb870af2451731d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4634"></a>コンパイラの警告 (レベル 4) C4634
XML ドキュメント コメント: 適用できません: 理由  
  
 XML ドキュメントのタグは、すべての C++ コンストラクトに適用できません。  たとえば、名前空間またはテンプレートにドキュメント コメントを追加できません。  
  
 詳細については、「 [XML Documentation](../../ide/xml-documentation-visual-cpp.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C4634 警告が生成されます。  
  
```  
// C4634.cpp  
// compile with: /W4 /doc /c  
/// This is a namespace.   // C4634  
namespace hello {  
   class MyClass  {};  
};  
```  
  
## <a name="example"></a>例  
 次の例では C4634 警告が生成されます。  
  
```  
// C4634_b.cpp  
// compile with: /W4 /doc /c  
/// This is a template.   // C4634  
template <class T>  
class MyClass  {};  
```