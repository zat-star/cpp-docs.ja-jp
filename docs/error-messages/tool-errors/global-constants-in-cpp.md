---
title: "C++ のグローバル定数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 766e1a6f48ecf3f64110e64d916c50d92c89345d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="global-constants-in-c"></a>C++ のグローバル定数
C++ のグローバル定数は、静的リンケージを持ちます。 これは、C とは異なりますグローバルを使用しようとする場合は、複数のファイルで C++ の定数エラーが発生した未解決外部です。 コンパイラは、変数の予約された領域がなくなる、グローバル定数を最適化します。  
  
 このエラーを解決するのには 1 つの方法は、const の初期化をヘッダー ファイルに含めるし、必要に応じて、関数のプロトタイプする場合と同様に、CPP ファイルでそのヘッダーをインクルードします。 別の方法としては、非定数、変数を作成し、それを評価するときに、定数の参照を使用してです。  
  
 次の例では、C2019 が生成されます。  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 この場合、次のようになります。  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>参照  
 [リンカー ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)