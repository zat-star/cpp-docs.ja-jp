---
title: "コンパイラ エラー C3387 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3387
dev_langs: C++
helpviewer_keywords: C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f61d65b62c32623b69cf7b4f533382e706d9f0b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3387"></a>コンパイラ エラー C3387
'member': 関数/\__declspec(dllimport) は WinRT 型またはマネージのメンバーに適用できません  
  
 `dllimport`と[dllexport](../../cpp/dllexport-dllimport.md) `__declspec`修飾子は、管理対象のメンバーまたは Windows ランタイム型では有効でありません。  
  
 次の例では C3387 を生成し、その修正方法を示しています。  
  
```  
// C3387a.cpp  
// compile with: /clr /c  
ref class X2 {  
   void __declspec(dllexport) mf() {   // C3387  
   // try the following line instead  
   // void mf() {  
   }  
};  
```