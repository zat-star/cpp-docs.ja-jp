---
title: "public (C++) | Microsoft Docs"
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
  - "public"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "public キーワード [C++]"
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# public (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## 解説  
 クラス メンバーのリストを前に置くと、**public** キーワードは、それらのメンバーが任意の関数からアクセスできることを指定します。  これは、次のアクセス指定子またはクラスの末尾までで宣言されているすべてのメンバーに適用されます。  
  
 基底クラスの名前を指定すると、**public** キーワードは、基底クラスのパブリック、プロテクト メンバーが派生クラスのそれぞれパブリックおよびプロテクト メンバーであることを指定します。  
  
 クラスのメンバーの既定のアクセスはプライベートです。  構造体または共用体のメンバーの既定のアクセスはパブリックです。  
  
 基底クラスの既定のアクセスは、クラスの場合はプライベートで、構造体の場合はパブリックです。  共用体に基底クラスを設定することはできません。  
  
 詳細については、「[private](../Topic/private%20\(C++\).md)」、「[protected](../Topic/protected%20\(C++\).md)」、「[friend](../cpp/friend-cpp.md)」および「[クラス メンバーへのアクセスの制御](../misc/controlling-access-to-class-members.md)」のメンバー アクセス テーブルを参照してください。  
  
## \/clr 固有  
 CLR 型では、C\+\+ アクセス指定子のキーワード \(**public**、`private`、および `protected`\) がアセンブリに関連する型およびメソッドの可視性に影響を与える可能性があります。  詳細については、「[型およびメンバーの可視性](../Topic/Type%20and%20Member%20Visibility.md)」を参照してください。  
  
> [!NOTE]
>  [\/LN](../build/reference/ln-create-msil-module.md) でコンパイルされるファイルは、この動作に影響を受けません。  この場合、すべてのマネージ クラス \(パブリックかプライベート\) が表示されます。  
  
## END \/clr 固有  
  
## 使用例  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## 参照  
 [クラス メンバーへのアクセス制御](../misc/controlling-access-to-class-members.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)