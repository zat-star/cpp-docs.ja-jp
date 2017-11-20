---
title: "コンパイラ エラー C2492 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2492
dev_langs: C++
helpviewer_keywords: C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 68268be94897e3c648e95185877dec9e276355c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2492"></a>コンパイラ エラー C2492
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