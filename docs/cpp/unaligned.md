---
title: "__unaligned | Microsoft Docs"
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
  - "__unaligned_cpp"
  - "__unaligned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unaligned キーワード [C++]"
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __unaligned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__unaligned` 修飾子を使用してポインターを宣言すると、コンパイラは、ポインターがアラインされていないデータを指していると見なします。  その結果、IPF \(Itanium Processor Family\) コンピューターを対象とするアプリケーションの場合、コンパイラは、アラインされていないデータを 1 バイトずつ読み込むコードを生成します。  
  
## 解説  
 `__unaligned` 修飾子は、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] および [!INCLUDE[vcpritanium](../Token/vcpritanium_md.md)] コンパイラに有効ですが、IPF コンピューターを対象とするアプリケーションだけに影響します。  この修飾子は、アドレス指定されたデータのアラインメントのみを対象とします。ポインター自体はアラインされていると見なされます。  
  
 [!INCLUDE[vcpritanium](../Token/vcpritanium_md.md)] プロセッサは、適切にアラインされていないデータにアクセスするとアラインメント エラーを生成し、そのエラー処理によってパフォーマンスが低下します。  `__unaligned` 修飾子を使用してプロセッサが 1 バイトずつデータを読み取るようにすることで、エラーを回避してください。  [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] プロセッサは、適切にアラインされていないデータもエラーにせずに処理できるので、この修飾子は [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] アプリケーションでは必要ありません。  
  
 アラインメントの詳細については、次のトピックを参照してください。  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_alignof 演算子](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [\/Zp \(構造体メンバーの配置\)](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md)  
  
-   [構造体の配置例](../build/examples-of-structure-alignment.md)  
  
## 使用例  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)