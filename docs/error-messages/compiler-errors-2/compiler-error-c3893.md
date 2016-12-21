---
title: "コンパイラ エラー C3893 | Microsoft Docs"
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
  - "C3893"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3893"
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3893
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : データ メンバーの左辺値は、クラス 'type\_name' のインスタンス コンストラクターでのみ使用することができます  
  
 静的な [initonly](../../dotnet/initonly-cpp-cli.md) データ メンバーは、静的コンストラクターで取得されたそれぞれのアドレスだけを保持できます。  
  
 インスタンス \(非静的\) initonly データ メンバーは、インスタンス \(非静的\) コンストラクターで取得されたそれぞれのアドレスだけを保持できます。  
  
 次の例では警告 C3893 が生成されます。  
  
```  
// C3893.cpp  
// compile with: /clr  
ref struct Y1 {  
   Y1() : data_var(0) {  
      int% i = data_var;   // OK  
   }  
   initonly int data_var;  
};  
  
int main(){  
   Y1^ y= gcnew Y1;  
   int% i = y->data_var;   // C3893  
}  
```