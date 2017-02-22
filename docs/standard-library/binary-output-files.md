---
title: "バイナリ出力ファイル | Microsoft Docs"
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
  - "バイナリ データ, バイナリ出力ファイル"
  - "ファイル [C++], バイナリ出力ファイル"
  - "I/O [C++], バイナリ出力ファイル"
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# バイナリ出力ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ストリームは、テキストに最初に設計されているため、既定の出力モードはテキストです。  テキスト モードでは、改行文字 \(16 進数 10\) はキャリッジ return–linefeed \(16 ビットのみ\) に展開します。  展開は次に示すように、問題が発生することがあります:  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 バイト シーケンス{99、0、10、0 を出力すると、このプログラムが予想される可能性がある; 代わりに、バイナリの入力を要求するプログラムの問題が発生する場合は、{99、0、13、10、0}出力します。  文字が未変換で記述された実際のバイナリ出力が必要な場合は、[ofstream](../Topic/ofstream.md) のコンストラクターの mode 引数を使用してバイナリ出力を指定することがあります:  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## 参照  
 [出力ストリーム](../standard-library/output-streams.md)