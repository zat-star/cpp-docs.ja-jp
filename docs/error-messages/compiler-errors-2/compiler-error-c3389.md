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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 6cfe5a03ecbb370eaf290f94ee5e26a5d185a1ae
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3389"></a>コンパイラ エラー C3389
/clr で __declspec(keyword) は使用できません: 純粋なまたは/clr:safe  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 A [_ _declspec](../../cpp/declspec.md)修飾子の使用を意味するプロセスの状態ごとです。  [/clr: 純粋な](../../build/reference/clr-common-language-runtime-compilation.md)意味、あたり[appdomain](../../cpp/appdomain.md)状態です。  そのために変数を宣言する、 `keyword` **_ _declspec**修飾子と指定してコンパイル**/clr: 純粋な**は許可されていません。  
  
 次の例では、c3389 エラーが生成されます。  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```
