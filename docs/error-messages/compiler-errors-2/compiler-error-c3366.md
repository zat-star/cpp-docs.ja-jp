---
title: "コンパイラ エラー C3366 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3366"
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable': マネージ型または WinRT 型の静的データ メンバーは、クラス定義内で定義される必要があります  
  
 WinRT または .NET のクラスまたはインターフェイスの静的メンバーをそのクラスまたはインターフェイスの定義外で参照しようとしました。  
  
 コンパイラは、\(1 回のパスの後に、メタデータを出力するために\) クラスの完全定義を認識する必要があり、静的データ メンバーをクラス内で初期化する必要があります。  
  
 たとえば、次の例では、C3366 を生成し、その修正方法を示しています。  
  
```  
// C3366.cpp  
// compile with: /clr /c  
ref class X {  
   public:  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```  
  
 次の例では、C3366 を生成し、その修正方法を示しています。  
  
```  
// C3366_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc struct X {  
   static int i;   // initialize i here to avoid C3366  
};  
  
int X::i = 5;      // C3366  
```