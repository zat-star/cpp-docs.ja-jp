---
title: "コンパイラ エラー C3914 | Microsoft Docs"
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
  - "C3914"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3914"
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3914
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定プロパティはスタティックであることはできません  
  
 既定のプロパティの宣言が正しくありません。詳細については、「[方法: インデックス付きプロパティを使用する](../../misc/how-to-use-indexed-properties.md)」を参照してください。  
  
## 使用例  
 次の例では C3914 エラーが生成されます。  
  
```  
// C3914.cpp  
// compile with: /clr /c  
ref struct X {  
   static property int default[int] {   // C3914  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```