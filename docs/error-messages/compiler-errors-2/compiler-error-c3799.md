---
title: "コンパイラ エラー C3799 | Microsoft Docs"
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
  - "C3799"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3799"
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3799
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インデックス付きプロパティは空のパラメーター リストを含むことはできません  
  
 インデックス付きプロパティの宣言が正しくありません。詳細については、「[方法: インデックス付きプロパティを使用する](../../misc/how-to-use-indexed-properties.md)」を参照してください。  
  
## 使用例  
 次の例では C3799 エラーが生成されます。  
  
```  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```