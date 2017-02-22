---
title: "1 つの引数 (int または long) を使用する出力ストリーム マニピュレーター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "出力ストリーム, int または long 引数のマニピュレーター"
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 1 つの引数 (int または long) を使用する出力ストリーム マニピュレーター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

iostream クラス ライブラリはパラメーター化されたなマニピュレーターを作成するためのマクロが用意されています。  `long` の単一の `int` または引数を持つマニピュレーターは特殊なケースです。  一つの `int` を受け入れるか、`long` の引数出力ストリームのマニピュレーターを作成するには \(`setw`など\) を iomanip\>で \<定義されている\_Smanip マクロを使用する必要があります。  この例では、指定した数のストリームに空白を挿入する `fillblank` のマニピュレーターを定義し、T:  
  
## 使用例  
  
```  
// output_stream_manip.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
void fb( ios_base& os, int l )  
{  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
}  
  
_Smanip<int>  
   __cdecl fillblank(int no)  
   {     
   return (_Smanip<int>(&fb, no));  
   }  
  
int main( )  
{  
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";  
}  
```  
  
## 参照  
 [引数を使用するカスタム マニピュレーター](../standard-library/custom-manipulators-with-arguments.md)