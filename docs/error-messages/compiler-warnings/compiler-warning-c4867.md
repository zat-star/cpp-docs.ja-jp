---
title: "コンパイラの警告 C4867 | Microsoft Docs"
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
  - "C4867"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4867"
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4867
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数': 関数呼び出しには引数リストがありません。メンバーへのポインターを作成するために 'call' を使用してください  
  
 メンバー関数へのポインターが正しく初期化されていません。  
  
 この警告は、ポインターからメンバーへの準拠が強化された Visual C\+\+ 2005 で行ったコンパイラ準拠作業の結果として生成されることがあります。Visual C\+\+ 2005 より前にコンパイルされたコードでは C4867 が生成されるようになりました。  
  
 この警告は、常にエラーとして表示されます。  この警告を無効にするには、[warning](../../preprocessor/warning.md) プラグマを使用します。  C4867 および MFC\/ATL の詳細については、「[\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md)」を参照してください。  
  
## 使用例  
 次の例では C4867 エラーが生成されます。  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```