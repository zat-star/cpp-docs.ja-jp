---
title: "コンパイラ エラー C2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2085"
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 仮引数リスト内にありません。  
  
 この識別子は、関数定義の中の仮パラメーター リストではないところで宣言されました。これは、ANSI C だけに対応します。  
  
 次の例では警告 C2085 が生成されます。  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 解決方法 :  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 セミコロンがない場合、`func1()` はプロトタイプではなく関数定義と見なされます。このため、`main` が `func1()` で定義され、識別子 `main` に対して C2085 エラーが生成されます。