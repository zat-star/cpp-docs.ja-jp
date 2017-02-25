---
title: "コンパイラ エラー C2535 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2535"
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C2535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : メンバー関数は、既に定義または宣言されています。  
  
 このエラーは、オーバーロードされた関数の定義または宣言で、同じ仮パラメーター リストを繰り返し使用した場合に発生します。  
  
 Dispose 関数が原因で C2535 が生成された場合、詳細については「[デストラクターとファイナライザー](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)」を参照してください。  
  
 ATL プロジェクトをコンパイルする場合は、サポート技術情報の「PRB: C2535 Error When Compiling ATL Project with Visual C\+\+ 6.0 \(Q241852\)」を参照してください。  
  
 次の例では警告 C2535 が生成されます。  
  
```  
// C2535.cpp  
// compile with: /c  
class C {  
public:  
   void func();   // forward declaration  
   void func() {}   // C2535  
};  
```