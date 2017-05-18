---
title: "コンパイラの警告 (レベル 1) C4503 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: f999fcb73860bfd2fabb3484e78f313a32240dee
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4503"></a>コンパイラの警告 (レベル 1) C4503
'identifier': 装飾名の長さを超えると、名前は切り詰められました  
  
 装飾名は、コンパイラの制限 (4096) よりも長い、切り捨てられました。 この警告とを切り捨てを回避するには、引数の数または使用される識別子の名の長さを減らしてください。  
  
 この警告が発行される状況の&1; つは、コードが含まれているテンプレートに繰り返しテンプレートの特殊化です。  たとえば、マップ (C++ 標準ライブラリ) からのマップです。  このような状況で行うことができます、typedef、マップを含んでいる型 (たとえば構造体など)。  
  
 しないコードを再構築する場合、ただし、します。  C4503 を生成するアプリケーションを出荷することが切り捨てられたシンボルにリンク時のエラーが発生するエラー内の記号の種類を特定するにくくあります。  デバッグも難しくなります。デバッガーでは、困難になるからマップ シンボル名の名前を入力することがあります。  ただし、切り捨てられた名前によって影響を受けるは、プログラムの正確性です。  
  
 次の例では、C4503 が生成されます。  
  
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
  
 次の例は、C4503 を解決するのには、コードを書き換える方法を示しています。  
  
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
