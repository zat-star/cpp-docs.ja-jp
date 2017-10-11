---
title: "コンパイラ エラー C2480 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 06f6c536d5756a19e28df7060373512e3e883a41
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2480"></a>コンパイラ エラー C2480
'identifier': 'thread' は静的なデータ項目の有効なのみ  
  
 使用することはできません、`thread`属性と自動変数、非静的データ メンバー、関数パラメーター、または関数宣言または定義します。  
  
 使用して、`thread`属性をグローバル変数、静的データ メンバー、およびローカルの静的変数のみです。  
  
 次の例では、C2480 が生成されます。  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```
