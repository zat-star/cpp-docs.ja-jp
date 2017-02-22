---
title: "コンパイラの警告 (レベル 1) C4503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4503"
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 装飾された名前の長さが限界を越えました。名前は切り捨てられます。  
  
 装飾名の長さがコンパイラの制限 \(4096 文字\) を超えたため、切り捨てられました。  この警告を回避し、名前が切り捨てられないようにするには、引数の数を減らすか、または識別子名を短くしてください。  
  
 この警告が発生する状況の 1 つは、テンプレート上で繰り返し特殊化されるテンプレートがコードに含まれている場合です。たとえば、C\+\+ 標準ライブラリのマップの割り当てなどです。この場合は、typedefs をマップを含む型 \(たとえば構造体など\) にできます。  
  
 ただし、コードの再構築をしたくない場合もあります。C4503 を生成するアプリケーションを出荷することはできます。しかし、切り捨てられたシンボルに関するリンク時エラーが発生した場合に、エラーが発生したシンボルの型の特定が通常より困難になります。また、デバッグもより難しくなります。デバッガーがシンボル名を型名に割り当てる操作も困難になるからです。ただし、名前が切り捨てられてもプログラムの正確さには影響しません。  
  
 次の例では警告 C4503 が生成されます。  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 次の例は、コードを書き直して C4503 を解決する方法の 1 つを示しています。  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```