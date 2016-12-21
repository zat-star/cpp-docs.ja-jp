---
title: "for each を使用した STL コレクションの反復処理 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DTL コレクション, 反復処理"
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for each を使用した STL コレクションの反復処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準 C\+\+ ライブラリ \(STL\) のコレクションを反復処理するために `for each` キーワードを使用できます。  
  
## すべてのプラットフォーム  
 **解説**  
  
 STL コレクションは、*コンテナー*です。  詳細については、「[STL コンテナー](../standard-library/stl-containers.md)」を参照してください。  
  
## 例  
 **例**  
  
 次のコード例は [\< map \>](../Topic/%3Cmap%3E.md)を反復処理するために `for each` を使用します。  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **出力**  
  
  **30 日の月 \= 4** **例**  
  
 次のコード例は STL コンテナーと反復変数に const 参照 \(`const&`\) を使用します。  *T*`&`として宣言できる型の各コレクションの反復変数として参照 \(`&`\) を使用できます。  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **出力**  
  
  **out: 60**   
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **解説**  
  
 この機能のプラットフォーム固有の解説がありません。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **解説**  
  
 この機能のプラットフォーム固有の解説がありません。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
## 参照  
 [for each、in](../dotnet/for-each-in.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)