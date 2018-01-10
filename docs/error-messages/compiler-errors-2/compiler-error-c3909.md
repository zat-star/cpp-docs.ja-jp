---
title: "コンパイラ エラー C3909 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3909
dev_langs: C++
helpviewer_keywords: C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d22341deb7ef6acd8a93ea234be7231a2c59b96e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3909"></a>コンパイラ エラー C3909
aWinRT またはマネージ イベント宣言は WinRT またはマネージ型で行う必要があります。  
  
 Windows ランタイム イベントまたはマネージ イベントがネイティブ型内で宣言されました。 このエラーを修正するには、Windows ランタイム型またはマネージ型内でイベントを宣言します。  
  
 詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
 次の例では、C3909 を生成し、その修正方法を示しています。  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```