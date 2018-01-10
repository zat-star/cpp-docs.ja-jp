---
title: "コンパイラ エラー C3383 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3383
dev_langs: C++
helpviewer_keywords: C3383
ms.assetid: ceb7f725-f417-4dc3-8496-0f413bb76687
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4edf434b9bd1d7a1e8c6609541bd29fab3c0e66d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3383"></a>コンパイラ エラー C3383
'operator new' は /clr:safe でサポートされていません  
  
 **/clr:safe** コンパイルの出力ファイルが検証可能なタイプ セーフのファイルであり、ポインターがサポートされていません。  
  
 詳細については、次のトピックを参照してください。  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Visual C++ の 64 ビットへの移行に関する一般的な問題](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>例  
 次の例では C3383 が生成されます。  
  
```  
// C3383.cpp  
// compile with: /clr:safe  
int main() {  
   char* pCharArray = new char[256];  // C3383  
}  
```