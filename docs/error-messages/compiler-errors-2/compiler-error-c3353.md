---
title: "コンパイラ エラー C3353 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 051300b1c670381c0450b373058644fc5a84e7d4
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3353"></a>コンパイラ エラー C3353
'delegate': デリゲートはマネージ型または WinRT 型のグローバル関数またはメンバー関数からのみ作成できます  
  
 デリゲートの宣言、[委任](../../windows/delegate-cpp-component-extensions.md)キーワードは、グローバル スコープでのみ宣言できます。  
  
 次の例では C3353 が生成されます。  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```
