---
title: "コンパイラの警告 C4957 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4957
dev_langs:
- C++
helpviewer_keywords:
- C4957
ms.assetid: a18c52d4-23e2-44f1-b4b5-f7fa5a7f3987
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8eb7283942a8a89fc3322983c41c68082b6c5cee
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4957"></a>コンパイラの警告 C4957
'cast': 'cast_from' から 'cast_to' への明示的なキャストは検証できません  
  
 キャストにより、検証不可能なイメージが生成されます。  
  
 安全なキャストもあります (ユーザー定義の変換をトリガーする `static_cast` 、 `const_cast`など)。 A [safe_cast](../../windows/safe-cast-cpp-component-extensions.md)検証可能なコードを生成することが保証されます。  
  
 詳細については、次を参照してください。[純粋なコードと検証可能なコード (C + + CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)です。  
  
 この警告がエラーとして発行され、無効にする、[警告](../../preprocessor/warning.md)プラグマ、または[/wd](../../build/reference/compiler-option-warning-level.md)コンパイラ オプション。  
  
 次の例では C4957 が生成されます。  
  
```  
// C4957.cpp  
// compile with: /clr:safe  
// #pragma warning( disable : 4957 )  
using namespace System;  
int main() {  
   Object ^ o = "Hello, World!";  
   String ^ s = static_cast<String^>(o);   // C4957  
   String ^ s2 = safe_cast<String^>(o);   // OK  
}  
```
