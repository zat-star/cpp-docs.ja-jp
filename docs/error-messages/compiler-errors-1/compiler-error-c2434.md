---
title: "コンパイラ エラー C2434 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 65aac590a3282f2fd71c460d14927f5695fcdc5a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2434"></a>コンパイラ エラー C2434
'symbol': __declspec(process) で宣言されたシンボルは/clr で動的に初期化できません: 純粋なモード  
  
 **/Clr: 純粋な**と**/clr:safe**コンパイラ オプションは、Visual Studio 2015 で廃止されました。  
  
 Process ごとの変数を動的に初期化することはできません**/clr: 純粋な**です。 詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[プロセス](../../cpp/process.md)します。  
  
## <a name="example"></a>例  
 次の例では、c2434 エラーを生成します。  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```
