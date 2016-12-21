---
title: "コンパイラ エラー C2144 | Microsoft Docs"
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
  - "C2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2144"
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

構文エラー : 'type' は 'token' によって先行されなければなりません。  
  
 `token` を置く必要がある場所で `type` を検出しました。  
  
 このエラーは、右中かっこ \(}\)、右かっこ、またはセミコロンが欠落していることが原因で発生する場合があります。  
  
 C2144 は、空白文字を含む CLR キーワードからマクロを作成しようとした場合にも発生します。  
  
 型の転送を行おうとして C2144 が発生することもあります。  詳細については、「[Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)」を参照してください。  
  
## 使用例  
 次の例では C2144 エラーが生成されます。  
  
```  
// C2144.cpp  
// compile with: /clr /c  
#define REF ref  
REF struct MyStruct0;   // C2144  
  
// OK  
#define REF1 ref struct  
REF1 MyStruct1;  
```  
  
## 使用例  
 次の例では C2144 エラーが生成されます。  
  
```  
// C2144_2.cpp  
// compile with: /clr /c  
ref struct X {  
  
   property double MultiDimProp[,,] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp[int , int, int] {  
      double get(int, int, int) { return 1; }  
      void set(int i, int j, int k, double l) {}  
   }  
  
   property double MultiDimProp2[] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp2[int] {  
      double get(int) { return 1; }  
      void set(int i, double l) {}  
   }  
};  
```