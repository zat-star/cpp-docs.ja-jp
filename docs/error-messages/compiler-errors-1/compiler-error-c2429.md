---
title: "コンパイラ エラー C2429 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
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
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 7d2c27ccdba28720596984c46c9d24f9d29c7b15
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2429"></a>コンパイラ エラー C2429
'*言語機能*'コンパイラ フラグが必要です'*コンパイラ オプション*'  
  
言語機能には、サポートについては、特定のコンパイラ オプションが必要です。  
  
エラー C2429: 言語機能 '入れ子になった名前空間の定義' には、コンパイラ フラグが必要です。 '/std:c では最新 ' を定義しようとする場合に生成される、*複合名前空間*、を 1 つ以上のスコープにネストされた名前空間名、Visual Studio 2015 の Update 3 以降を含む名前空間。 C++&17; する前に、定義は C++ では許可されませんが名前空間を合成します。 コンパイラは、複合名前空間の定義をサポートしているときに、 [/std:c では最新](../../build/reference/std-specify-language-standard-version.md)コンパイラ オプションを指定します。  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
