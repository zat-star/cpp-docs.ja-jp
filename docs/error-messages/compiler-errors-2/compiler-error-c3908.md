---
title: "コンパイラ エラー C3908 | Microsoft Docs"
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
  - "C3908"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3908"
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3908
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'コンストラクト' よりも制限が少ないアクセス レベルです  
  
 プロパティのアクセサー メソッド \(get または set\) に、プロパティ自体に指定されているアクセス レベルよりも制限が少ないアクセス レベルを指定できません。イベントのアクセサー メソッドについても同様です。  
  
 詳細については、「[プロパティ](../../windows/property-cpp-component-extensions.md)」、および「[イベント](../../windows/event-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3908 が生成されます。  
  
```  
// C3908.cpp  
// compile with: /clr  
ref class X {  
protected:  
   property int i {  
   public:   // C3908 property i is protected   
      int get();  
   private:  
      void set(int);   // OK more restrictive  
   };  
};  
```