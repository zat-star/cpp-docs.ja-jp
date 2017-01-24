---
title: "コンパイラ エラー C3076 | Microsoft Docs"
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
  - "C3076"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3076"
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3076
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'インスタンス' : 参照型 '型' のインスタンスをネイティブ型に埋め込むことはできません  
  
 ネイティブ型には CLR 型のインスタンスを含めることはできません。  
  
 詳細については、「[参照型の C\+\+ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。  
  
## 使用例  
 次の例では C3076 エラーが生成されます。  
  
```  
// C3076.cpp  
// compile with: /clr /c  
ref struct U {};  
  
struct V {  
   U y;   // C3076  
};  
  
ref struct W {  
   U y;   // OK  
};  
```