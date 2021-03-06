---
title: "コンパイラ エラー C3533 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7bcd9c710ac5cdd50b966a72291918459d984be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3533"></a>コンパイラ エラー C3533
'type': パラメーターは 'auto' を含む型を持つことはできません  
  
 メソッドまたはテンプレート パラメーターを宣言することはできません、`auto`キーワード場合、既定[/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションが有効にします。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  削除、`auto`パラメーターの宣言からキーワード。  
  
## <a name="example"></a>例  
 関数パラメーターを宣言しているために、次の例で C3535、`auto`キーワードとそれをコンパイルした**/Zc:auto**です。  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>例  
 テンプレート パラメーターを宣言しているために、次の例で C3535、`auto`キーワードとそれをコンパイルした**/Zc:auto**です。  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>参照  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)