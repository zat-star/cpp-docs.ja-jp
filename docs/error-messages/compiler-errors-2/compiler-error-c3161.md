---
title: "コンパイラ エラー C3161 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4be981b2af166d85a3a83209a901f3e3e51b6246
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3161"></a>コンパイラ エラー C3161
'interface': クラスを入れ子構造体、共用体、またはインターフェイスのインターフェイスは無効です。クラス、構造体または共用体でインターフェイスを入れ子は無効です。  
  
 [_ _Interface](../../cpp/interface.md)グローバル スコープまたは名前空間内でのみ使用できます。 クラス、構造体、または共用体は、インターフェイスに表示できません。  
  
## <a name="example"></a>例  
 次の例では、C3161 を生成します。  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```
