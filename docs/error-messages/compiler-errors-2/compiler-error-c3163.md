---
title: "コンパイラ エラー C3163 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 95fb254036d2883b6efe6b81bda54864d533c2a8
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3163"></a>コンパイラ エラー C3163
'construct': 属性を前の宣言と整合性がありません  
  
 定義に適用される属性は、宣言に適用される属性と競合します。  
  
 C3163 を解決するのには 1 つの方法は、事前宣言の属性を取り除くことです。 事前宣言の属性が定義の属性よりも小さくする以上で、多くてもそれらにします。  
  
 C3163 エラーの考えられる原因には、Microsoft ソース コード注釈言語 (SAL) が含まれます。 使用してプロジェクトをコンパイルするまで、SAL マクロは展開されません、 **/analyze**フラグ。 /Analyze せず、クリーンにコンパイルされるプログラムをスロー C3163 で再コンパイルを試行した場合、/analyze オプション。 SAL の詳細については、次を参照してください。 [SAL 注釈](../../c-runtime-library/sal-annotations.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3163 が生成されます。  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## <a name="see-also"></a>関連項目  
 [SAL 注釈](../../c-runtime-library/sal-annotations.md)
