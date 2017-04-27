---
title: "コンパイラ エラー C2492 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2492
dev_langs:
- C++
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
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
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 54a650e967acb2ee0b6864780823111b4db9414c
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2492"></a>{1&gt;コンパイラ エラー C2492&lt;1}
'*変数*': スレッド ストレージ存続期間を使用してデータには、dll インターフェイスはありません。    
  
 変数が宣言された、[スレッド](../../cpp/thread.md)属性し、DLL とインターフェイスします。 アドレス、`thread`変数が不明、実行時までため、DLL のインポートまたはエクスポートにリンクすることはできません。  
  
 次の例では、C2492 が生成されます。  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```
