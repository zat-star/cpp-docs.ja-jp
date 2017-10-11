---
title: "コンパイラ エラー C3353 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 47a0231a161a2502c26786fceeb1b3634b236eaf
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3353"></a>コンパイラ エラー C3353
'delegate': デリゲートはマネージ型または WinRT 型のグローバル関数またはメンバー関数からのみ作成できます  
  
 宣言されたデリゲートを[委任](../../windows/delegate-cpp-component-extensions.md)キーワードでは、グローバル スコープでのみ宣言できます。  
  
 次の例では C3353 が生成されます。  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```
