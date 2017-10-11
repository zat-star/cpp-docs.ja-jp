---
title: "コンパイラ エラー C3389 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 561359afcd9cf694369bd1addb4f641a33a3f989
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3389"></a>コンパイラ エラー C3389
/clr で __declspec(keyword) は使用できません:/clr:pure または/clr:safe  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 A [_ _declspec](../../cpp/declspec.md)修飾子の使用を意味するプロセスの状態ごとです。  [/clr: 純粋な](../../build/reference/clr-common-language-runtime-compilation.md)意味、あたり[appdomain](../../cpp/appdomain.md)状態です。  そのために変数を宣言する、 `keyword` **_ _declspec**修飾子と指定してコンパイル**/clr: 純粋な**は許可されていません。  
  
 次の例では、C3389 が生成されます。  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```
