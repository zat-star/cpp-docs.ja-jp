---
title: "コンパイラの警告 (レベル 3) C4580 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4580"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4580"
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 3) C4580
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\[attribute\] は使用できません。System::Attribute または Platform::Metadata を基底クラスとして指定してください  
  
 [attribute](../../windows/attribute.md) は、ユーザー定義の属性を作成するための構文として推奨されなくなりました。  詳細については、「[User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  CLR コードの場合は、[System::Attribute](assetId:///System::Attribute?qualifyHint=False&autoUpgrade=True) から属性を派生させます。  Windows ランタイム コードの場合は、`Platform::Metadata` から属性を派生させます。  
  
## 使用例  
 次の例では、C3454 を生成し、その修正方法を示しています。  
  
```  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```