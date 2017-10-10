---
title: "コンパイラ エラー C2506 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2506
dev_langs:
- C++
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 200155978fe12a142519dd79e50cb409e9ea1e54
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2506"></a>コンパイラ エラー C2506
'member': '__declspec(modifier)' はこのシンボルに適用することはできません  
  
 マネージ クラスの静的メンバーの場合は、プロセスごとまたは appdomain ごとを宣言できません。  
  
 詳細については、「 [appdomain](../../cpp/appdomain.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C2506 を生成します。  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```
