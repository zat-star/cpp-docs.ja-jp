---
title: "コンパイラ エラー C3900 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3900"
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'メンバー': 現在のスコープには使用できません  
  
 プロパティ ブロックには、関数宣言およびインライン関数定義だけを含めることができます。  関数以外のメンバーをプロパティ ブロックに含めることはできません。  typedef、演算子、フレンド関数は許可されません。  詳細については、「[プロパティ](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
 イベント定義には、アクセス メソッドおよび関数だけを含めることができます。  
  
 次の例では警告 C3900 が生成されます。  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 次の例では警告 C3900 が生成されます。  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```