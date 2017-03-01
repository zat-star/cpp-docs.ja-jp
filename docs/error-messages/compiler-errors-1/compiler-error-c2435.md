---
title: "コンパイラ エラー C2435 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
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
ms.openlocfilehash: dbc2045eae70cacd42e13ddb7cc8ecb3d60b8596
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2435"></a>コンパイラ エラー C2435
'var': 動的な初期化、管理対象の CRT が必要ですが、/clr:safe とコンパイルできません。  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 アプリケーション ドメインにグローバル変数の初期化でコンパイルされた CRT を必要と`/clr:pure`、検証可能なイメージを生成しません。  
  
 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[プロセス](../../cpp/process.md)します。  
  
## <a name="example"></a>例  
 次の例では、c2435 エラーが生成されます。  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
