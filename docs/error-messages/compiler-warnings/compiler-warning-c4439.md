---
title: "コンパイラの警告 C4439 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4439
dev_langs:
- C++
helpviewer_keywords:
- C4439
ms.assetid: 9449958f-f407-4824-829b-9e092f2af97d
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b827d0d2feac4cafe4a90d58003a348ece36bd2d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4439"></a>コンパイラの警告 C4439
'function': 署名のマネージ型と関数定義は、_ _clrcall 呼び出し規約を含んでいなければなりません  
  
 コンパイラは、呼び出し規約を暗黙的に交換してください。 [_ _clrcall](../../cpp/clrcall.md)します。 この警告を解決するには、削除、`__cdecl`または`__stdcall`呼び出し規約です。  
  
 C4439 はエラーとして常に発行されます。 この警告をオフにすることができます、`#pragma warning`または**/wd**; を参照してください[警告](../../preprocessor/warning.md)または[/w、/W0、/W1、/W2、/W3、/W4、/w1、/w2、/w3、/w4、/Wall、/wd、/お/wo、/Wv/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)の詳細。  
  
## <a name="example"></a>例  
 次の例では、C4439 を生成します。  
  
```  
// C4439.cpp  
// compile with: /clr  
void __stdcall f( System::String^ arg ) {}   // C4439  
void __clrcall f2( System::String^ arg ) {}   // OK  
void f3( System::String^ arg ) {}   // OK  
```
