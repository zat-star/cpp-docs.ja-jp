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
ms.openlocfilehash: 5cb5929fe1619ce75a7bde15ac08955247f1af7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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