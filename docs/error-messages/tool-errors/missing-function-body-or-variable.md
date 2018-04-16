---
title: "関数本体または変数がありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 356d0f0a71feccee953a0b1bd7dc54bc64a0e233
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="missing-function-body-or-variable"></a>関数本体または変数の未定義
だけ関数のプロトタイプでは、コンパイラがエラーを発生させず続行できますが、関数のコードまたは予約された変数の領域がないために、リンカーが、アドレスへの呼び出しを解決することはできません。 リンカーが解決する必要がある関数への呼び出しを作成するまで、このエラーを表示はされません。  
  
## <a name="example"></a>例  
 Main 関数呼び出しは、プロトタイプにより、関数の存在を考えるため lnk2019 エラーが発生します。  リンカーは、しないことを検出します。  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>例  
 C++ では、クラス定義に、クラスであり、プロトタイプだけでなく、特定の機能の実装を含めることを確認します。 ヘッダー ファイルの外部でクラスを定義する場合は必ず関数の前にクラス名を含める (`Classname::memberfunction`)。  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>参照  
 [リンカー ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)