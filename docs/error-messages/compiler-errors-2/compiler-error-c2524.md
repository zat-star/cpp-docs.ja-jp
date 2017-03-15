---
title: "コンパイラ エラー C2524 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2524"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2524"
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2524
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'デコンストラクター' : 'デコンストラクター\/ファイナライザー' には 'void' パラメーター リストを指定しなければなりません。  
  
 デストラクターまたはファイナライザーのパラメーター リストが [void](../../cpp/void-cpp.md) ではありません。  ほかの型のパラメーターは使用できません。  
  
## 使用例  
 次のコードでは C2524 エラーが生成されます。  
  
```  
// C2524.cpp  
// compile with: /c  
class A {  
   A() {}  
   ~A(int i) {}    // C2524  
   // try the following line instead  
   // ~A() {}  
};  
```  
  
## 使用例  
 次のコードでは C2524 エラーが生成されます。  
  
```  
// C2524_b.cpp  
// compile with: /clr /c  
ref struct I1 {  
protected:  
   !I1(int i);   // C2524  
   // try the following line instead  
   // !I1();  
};  
```