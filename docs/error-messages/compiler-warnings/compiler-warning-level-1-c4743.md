---
title: "コンパイラの警告 (レベル 1) C4743 | Microsoft Docs"
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
  - "C4743"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4743"
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4743
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'*type*' に '*file1*' と '*file2*'で異なるサイズがあります: *number* と *number* バイト  
  
 *file1* の変数のサイズが *file2*の変数のサイズが異なるという 2 種類のファイルで参照または定義された外部変数は、それぞれのファイルで定義された、型、およびコンパイラがあります。  
  
 この警告が C\+\+ に対して出された場合は、次の点が重要になります。  2 つのファイルに同じタイプを同じ名前で宣言した場合、これらの宣言に仮想関数が含まれている場合、および宣言が異なる場合は、仮想関数テーブルに関して C4744 警告が出されます。  この警告が出されるのは、同じ型に対してサイズの異なる仮想関数テーブルが 2 つあるので、リンカーはどちらか 1 つを選択して実行可能ファイルに結合する必要があるからです。この結果、プログラムが間違った仮想関数を呼び出すことがあります。  
  
 この警告を解決するには、同じ型定義を使用するか、異なる型名または変数名を指定します。  
  
## 使用例  
 次の例では、1 つの型定義を使用します。  
  
```  
// C4743a.cpp  
// compile with: /c  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
};  
  
void C::f1(void) {}  
void C::f2(void) {}  
void C::f3(void) {}  
C q;  
```  
  
## 使用例  
 次の例では C4743 エラーが生成されます。  
  
```  
// C4743b.cpp  
// compile with: C4743a.cpp /W1 /GL /O2  
// C4743 expected  
class C {  
public:  
    virtual void f1(void);  
    virtual void f2(void);  
    virtual void f3(void);  
    virtual void f4(void);  
    virtual void f5(void);  
};  
  
void C::f4(void) {}  
void C::f5(void) {}  
C x;  
  
int main() {}   
```