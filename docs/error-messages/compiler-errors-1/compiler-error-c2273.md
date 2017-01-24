---
title: "コンパイラ エラー C2273 | Microsoft Docs"
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
  - "C2273"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2273"
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2273
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

「型」: 」\-\>' 演算子の右側として無効  
  
 `->` 演算子の右側のオペランドとして型が使用されています。  
  
 このエラーは、ユーザー定義型の変換にアクセスしようとしたことが原因で発生する場合があります。  キーワード `operator`\) \> と `type`間を使用します。  
  
 次の例では警告 C2273 が生成されます。  
  
```  
// C2273.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
int main() {  
   MyClass * ClassPtr = new MyClass;  
   int i = ClassPtr->int();   // C2273  
   int j = ClassPtr-> operator int();   // OK  
}  
```