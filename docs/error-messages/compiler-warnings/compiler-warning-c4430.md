---
title: "コンパイラの警告 C4430 | Microsoft Docs"
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
  - "C4430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4430"
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 C4430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型指定子がありません \- int と仮定しました。メモ: C\+\+ は int を既定値としてサポートしていません  
  
 このエラーは、Visual C\+\+ 2005 で行われたコンパイラ準拠作業の結果として生成されることがあります。すべての宣言で、明示的に型を指定する必要があります。int が仮定されることはなくなりました。  
  
 C4430 は、常にエラーとして表示されます。この警告は、`#pragma warning` または **\/wd** を使用してオフにできます。詳細については、「[warning](../../preprocessor/warning.md)」または「[\/w、\/Wn、\/WX、\/Wall、\/wln、\/wdn、\/wen、\/won \(警告レベル\)](../../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
## 使用例  
 次の例では C4430 エラーが生成されます。  
  
```  
// C4430.cpp  
// compile with: /c  
struct CMyClass {  
   CUndeclared m_myClass;  // C4430  
   int m_myClass;  // OK  
};  
  
typedef struct {  
   POINT();   // C4430  
   // try the following line instead  
   // int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```