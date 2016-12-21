---
title: "コンパイラの警告 (レベル 3) C4686 | Microsoft Docs"
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
  - "C4686"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4686"
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4686
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'ユーザー定義型' : 動作と UDT の戻り値の呼び出し規約に変更がある可能性があります。  
  
 クラス テンプレート指定が、戻り値の型で使用される前に定義されていませんでした。  クラスをインスタンス化するものより C4686 が解決されます。; インスタンスを宣言またはメンバー \(\<\>Cint::anything\) にアクセスするには、オプションです。  
  
 この警告は、Visual C\+\+ .NET 2003 コンパイラを ISO C\+\+ 標準に準拠させる作業の結果として生成されます。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 代わりに、次のコードを試してください。  
  
```  
// C4686.cpp  
// compile with: /W3  
#pragma warning (default : 4686)  
template <class T>  
class C;  
  
template <class T>  
C<T> f(T);  
  
template <class T>  
class C {};  
  
int main() {  
   f(1);   // C4686  
}  
  
template <class T>  
C<T> f(T) {  
   return C<int>();  
}  
```