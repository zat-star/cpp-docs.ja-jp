---
title: "exit または return の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit 関数"
  - "return キーワード [C++], プログラムの終了のための使用"
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# exit または return の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**exit** を呼び出すか **main** から `return` ステートメントを実行すると、静的オブジェクトが初期化と逆の順序で破棄されます。  次の例は、こうした初期化やクリーンアップがどのように機能するのかを示します。  
  
## 使用例  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 前の例では、静的オブジェクト `sd1` と `sd2` は、`main` に入る前に作成および初期化されます。  このプログラムが `return` ステートメントを使用して終了した後、最初に `sd2` が破棄され、その後に `sd1` が破棄されます。  `ShowData` クラスのデストラクターは、これらの静的オブジェクトに関連付けられたファイルを閉じます  \(初期化、コンストラクター、およびデストラクターに関する詳細については、「[特殊なメンバー関数](../misc/special-member-functions-cpp.md)」を参照してください\)。  
  
 このコードを作成するもう 1 つの方法は、ブロック スコープを持つ `ShowData` オブジェクトを宣言して、スコープ外に出ると破棄できるようにすることです。  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## 参照  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)