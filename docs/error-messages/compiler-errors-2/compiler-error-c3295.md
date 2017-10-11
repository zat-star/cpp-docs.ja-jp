---
title: "コンパイラ エラー C3295 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3295
dev_langs:
- C++
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b72e4839341006d2058c21a1523b0d7567f51696
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3295"></a>コンパイラ エラー C3295
'#pragma pragma' は、グローバルまたは名前空間スコープでのみ使用できます  
  
 一部のプラグマは関数内では使用できません。  参照してください[プラグマ ディレクティブと _ _pragma キーワード](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C3295 が生成されます。  
  
```  
// C3295.cpp  
int main() {  
   #pragma managed   // C3295  
}  
```
