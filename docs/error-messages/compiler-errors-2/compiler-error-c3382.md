---
title: "コンパイラ エラー C3382 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3382
dev_langs: C++
helpviewer_keywords: C3382
ms.assetid: a7603abd-ac4e-4ae6-a02b-3bdc6d1908a6
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c58047e409c60fd2b6cb65418131f6aadb1430a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3382"></a>コンパイラ エラー C3382
'sizeof' は /clr:safe でサポートされていません  
  
 **/clr:safe** コンパイルの出力ファイルは検証可能なタイプ セーフのファイルです。sizeof 演算子の戻り値は size_t であり、そのサイズはオペレーティング システムによって異なるため、sizeof はサポートされていません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [sizeof 演算子](../../cpp/sizeof-operator.md)  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Visual C++ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>例  
 次の例では C3382 が生成されます。  
  
```  
// C3382.cpp  
// compile with: /clr:safe  
int main() {  
   sizeof( char );   // C3382  
}  
```