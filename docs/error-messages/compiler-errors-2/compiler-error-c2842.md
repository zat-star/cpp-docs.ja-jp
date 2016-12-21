---
title: "コンパイラ エラー C2842 | Microsoft Docs"
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
  - "C2842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2842"
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : マネージ型または WinRT 型はそれ自体の 'operator new' または 'operator delete' を定義できません  
  
 独自の [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) または [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md) を定義して、ネイティブ ヒープでのメモリの割り当てを管理できます。  ただし、これらの演算子はマネージ ヒープでのみ割り当てられるため、参照クラスでは定義できません。  
  
 詳細については、「[ユーザー定義の演算子](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。  
  
## 使用例  
 次の例では C2842 が生成されます。  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
  
## 使用例  
 次の例では C2842 が生成されます。  
  
```  
// C2842_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```