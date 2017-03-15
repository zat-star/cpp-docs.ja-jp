---
title: "変更可能なデータ メンバー (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "mutable_cpp"
  - "mutable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mutable キーワード [C++]"
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 変更可能なデータ メンバー (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このキーワードは、クラスの non\-static データ メンバーおよび non\-const データ メンバーにのみ適用できます。  データ メンバーが `mutable` として宣言されている場合、**const** メンバー関数からこのデータ メンバーに値を有効に割り当てることができます。  
  
## 構文  
  
```  
  
mutable member-variable-declaration;  
```  
  
## 解説  
 たとえば次のコードは、`m_accessCount` が `mutable` として宣言されており、したがって `GetFlag` が const メンバー関数であっても `GetFlag` によって変更できるために、エラーなくコンパイルされます。  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)