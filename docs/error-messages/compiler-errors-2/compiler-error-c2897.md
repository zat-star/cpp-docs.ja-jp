---
title: "コンパイラ エラー C2897 | Microsoft Docs"
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
  - "C2897"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2897"
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2897
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デストラクター\/ファイナライザー' を関数テンプレートにすることはできません。  
  
 デストラクターまたはファイナライザーはオーバーロードできないため、一連のデストラクターを定義するテンプレートとしてデストラクターを宣言することはできません。  
  
 次の例では警告 C2897 が生成されます。  
  
## 使用例  
 次の例では C2897 エラーが生成されます。  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## 使用例  
 次の例では C2897 エラーが生成されます。  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```