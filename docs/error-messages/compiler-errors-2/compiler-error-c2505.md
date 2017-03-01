---
title: "コンパイラ エラー C2505 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2505
dev_langs:
- C++
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: cd11a76d1cbfd6f082c4926816a99c29733994c3
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2505"></a>コンパイラ エラー C2505
'symbol': '__declspec(modifer)' は、関数宣言またはグローバル オブジェクトまたは静的データ メンバーの定義にのみ適用できます  
  
 A`__declspec`グローバル スコープでのみ使用するようにデザインされた関数で使用します。  
  
 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[プロセス](../../cpp/process.md)します。  
  
 次の例では、c2505 エラーが生成されます。  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```
