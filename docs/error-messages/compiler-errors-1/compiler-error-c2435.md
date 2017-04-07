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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 53a3144fe8e87f36a1a5149d292130a9913b646a
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-error-c2435"></a>コンパイラ エラー C2435
'var': 動的な初期化、マネージ CRT が必要ですが、/clr:safe と共にコンパイルできません  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 アプリケーションごとのドメインのグローバル変数の初期化でコンパイルされた CRT が必要です。 `/clr:pure`、検証可能なイメージが生成されません。  
  
 詳細については、次を参照してください。 [appdomain](../../cpp/appdomain.md)と[プロセス](../../cpp/process.md)です。  
  
## <a name="example"></a>例  
 次の例では、C2435 が生成されます。  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
