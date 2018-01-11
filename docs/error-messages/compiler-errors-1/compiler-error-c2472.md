---
title: "コンパイラ エラー C2472 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2472
dev_langs: C++
helpviewer_keywords: C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5267f20aaed4ebf1c320d3d960684376e29814ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2472"></a>コンパイラ エラー C2472
'function' を 'message' マネージ コードで生成できません。混合イメージを生成するには、/clr と共にコンパイルしてください  
  
 このエラーは、純粋な共通言語ランタイム (CLR) の環境内で、マネージ コードでサポートされていない型を使用すると発生します。 エラーを解決するには、 **/clr** を使用してコンパイルします。  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
## <a name="example"></a>例  
 次の例では警告 C2472 が生成されます。  
  
```  
// C2472.cpp  
// compile with: /clr:pure  
// C2472 expected  
  
#include <cstdlib>  
  
int main()  
{  
   int * __ptr32 p32;  
   int * __ptr64 p64;  
  
   p32 = (int * __ptr32)malloc(4);  
   p64 = p32;  
}  
```  
  
## <a name="see-also"></a>参照  
 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)