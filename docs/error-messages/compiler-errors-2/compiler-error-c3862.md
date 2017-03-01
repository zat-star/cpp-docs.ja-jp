---
title: "コンパイラ エラー C3862 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 6
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 48dbae62c367616a437db0607d84fa89e8006021
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3862"></a>コンパイラ エラー C3862
'function':/clr を指定したアンマネージ関数をコンパイルすることはできません: 純粋なまたは/clr:safe  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 使用してコンパイル**/clr: 純粋な**または**/clr:safe**は MSIL だけイメージ、ネイティブ (アンマネージ) コードなしでイメージを生成します。  したがって、使用することはできません、`unmanaged`プラグマ、 **/clr: 純粋な**または**/clr:safe**コンパイルします。  
  
 詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)します。  
  
## <a name="example"></a>例  
 次の例では、c3862 エラーが生成されます。  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```
