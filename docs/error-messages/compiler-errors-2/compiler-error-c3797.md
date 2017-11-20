---
title: "コンパイラ エラー C3797 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3797
dev_langs: C++
helpviewer_keywords: C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f03b677eac09b7935778590be605897e5eca1524
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3797"></a>コンパイラ エラー C3797
'override': イベントの宣言は、配置しなければなりませんイベントを追加/削除/raise の各メソッドの代わりに) オーバーライド指定子を持つことはできません  
  
 別の単純なイベントでは、単純なイベント (明示的に定義されたアクセサー メソッドせずイベント) をオーバーライドすることはできません。 オーバーライドするイベントは、アクセサー関数の動作を定義する必要があります。  
  
 詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3797 を生成します。  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```