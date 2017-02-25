---
title: "入力ストリームのメンバー関数 | Microsoft Docs"
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
  - "入力ストリーム オブジェクト"
  - "入力ストリーム, メンバー関数"
ms.assetid: b4b9465d-0da9-4ccf-859d-72a68418982e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 入力ストリームのメンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力ストリームのメンバー関数は、ディスクの入力に使用されます。  このメンバー関数は、次のとおりです。:  
  
-   [入力ストリームの Open 関数](#vclrftheopenfunctionforinputstreamsanchor11)  
  
-   [Get 関数](#vclrfthegetfunctionanchor12)  
  
-   [getline 関数](#vclrfthegetlinefunctionanchor13)  
  
-   [Read 関数](#vclrfthereadfunctionanchor14)  
  
-   [seekg と tellg 関数](#vclrftheseekgandtellgfunctionsanchor7)  
  
-   [入力ストリームの終了関数](#vclrftheclosefunctionforinputstreamsanchor15)  
  
##  <a name="vclrftheopenfunctionforinputstreamsanchor11"></a> 入力ストリームの Open 関数  
 入力ファイル ストリーム \(ifstream\) を使用すると、特定のディスク ファイルとそのストリームを関連付ける必要があります。  コンストラクターでこれを行うことも、**開く** 関数を使用できます。  いずれの場合も、引数は同じです。  
  
 入力ストリームに関連付けられたファイルを開くときに一般的に [ios\_base::openmode](../Topic/ios_base::openmode.md) フラグを指定します \(既定のモードでは、**ios::in**です\)。  **open\_mode** フラグの一覧については、[Open 関数](#vclrftheopenfunctionforinputstreamsanchor11)を参照してください。  フラグはビットごとのと組み合わせることができます。または、\(&#124; 演算子\)。  
  
 ファイルを読み取るには、最初にあるかどうかを判断するに **失敗** メンバー関数を使用する:  
  
```  
istream ifile( "FILENAME" );  
if ( ifile.fail() )  
// The file does not exist ...  
```  
  
##  <a name="vclrfthegetfunctionanchor12"></a> Get 関数  
 **取得** のフォーマットされていないメンバー関数は 2 点を除き **\>\>** の演算子と同様に機能します。  まず、**取得** 関数は [skipws](../Topic/skipws.md) フラグが設定されている場合抽出器が null 以外の場合、null 文字が含まれています \(既定\)。  第 2 に、**取得** 関数は結ばれた出力ストリーム \(`cout`フラッシュしますあまりなど\)。  
  
 **取得** 関数のバリエーションが読み取ることができる文字バッファーのアドレスと最大回数を指定します。  これは、この例に示すように、特定の変数に送信される文字数を制限する場合に便利です:  
  
```  
// ioo_get_function.cpp  
// compile with: /EHsc  
// Type up to 24 characters and a terminating character.   
// Any remaining characters can be extracted later.  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   char line[25];  
   cout << " Type a line terminated by carriage return\n>";  
   cin.get( line, 25 );  
   cout << line << endl;  
}  
```  
  
### 入力  
  
```  
1234  
```  
  
### 出力例  
  
```  
1234  
```  
  
##  <a name="vclrfthegetlinefunctionanchor13"></a> getline 関数  
 **getline** のメンバー関数は **取得** 関数に似ています。  関数は、両方の入力に終端文字を指定する 3 番目の引数を有効にします。  既定値は改行文字です。  関数は、必須の終端文字の 1 文字が予約されています。  ただし、**取得** はストリームに終端文字を残し、**getline** は終端文字を削除します。  
  
 次の例では、入力ストリームに終端文字を示します。:  
  
```  
// getline_func.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char line[100];  
   cout << " Type a line terminated by 't'" << endl;  
   cin.getline( line, 100, 't' );  
   cout << line;  
}  
```  
  
### 入力  
  
```  
test  
```  
  
##  <a name="vclrfthereadfunctionanchor14"></a> Read 関数  
 **読み取り** のメンバー関数では、ファイルから指定されたメモリ領域にバイトを読み取ります。  長さの引数は読み取ったバイト数が決まります。  この引数を指定しないと、読み取ることは `EOF` の埋め込まれたな文字が読み込まれたとき物理 EOF が見つかりました。テキストモードがファイルの場合は、達したら停止します。  
  
 この例では、構造体の給与ファイルからバイナリ レコードを読み込みます:  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   struct  
   {  
      double salary;  
      char name[23];  
   } employee;  
  
   ifstream is( "payroll" );  
   if( is ) {  // ios::operator void*()  
      is.read( (char *) &employee, sizeof( employee ) );  
      cout << employee.name << ' ' << employee.salary << endl;  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 プログラムでデータ レコードを復帰またはライン フィードの終端を持たない構造で指定したとおりに設定されていると仮定しています。  
  
##  <a name="vclrftheseekgandtellgfunctionsanchor7"></a> seekg と tellg 関数  
 入力ファイル ストリームはデータが次に読み取られるファイルの位置に内部ポインターを保持します。  次に示すように `seekg` 関数の this ポインターを設定する:  
  
```  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
      tfile.seekg( 8 );        // Seek 8 bytes in (past salary)  
      while ( tfile.good() ) { // EOF or failure stops the reading  
         tfile.get( ch );  
         if( !ch ) break;      // quit on null  
         cout << ch;  
      }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
 `seekg` をレコード指向のデータ管理システムを実装するために使用するには、ファイルの末尾に関連するバイトの位置を取得するために固定長レコード サイズをレコード番号増加し、レコードを読み取るために **取得** オブジェクトを使用します。  
  
 `tellg` のメンバー関数は、読み取り用のファイルの現在の位置を返します。  iostream ライブラリで \<定義されている型の値 `streampos`、`typedef` です\>。  次の例では、ファイルを読み取り、領域の位置を示すメッセージが表示されます。  
  
```  
#include <fstream>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char ch;  
   ifstream tfile( "payroll" );  
   if( tfile ) {  
       while ( tfile.good( ) ) {  
          streampos here = tfile.tellg();  
          tfile.get( ch );  
          if ( ch == ' ' )  
             cout << "\nPosition " << here << " is a space";  
       }  
   }  
   else {  
      cout << "ERROR: Cannot open file 'payroll'." << endl;  
   }  
}  
```  
  
##  <a name="vclrftheclosefunctionforinputstreamsanchor15"></a> 入力ストリームの終了関数  
 **閉じる** のメンバー関数は、入力ファイル ストリームに関連付けられているディスク ファイルを閉じ、オペレーティング システムのファイル ハンドルを解放します。  [ifstream](../standard-library/basic-ifstream-class.md) のデストラクターによってファイルを閉じて、同じストリーム オブジェクトごとに個別のファイルを開く必要がある場合 **閉じる** 関数を使用できます。  
  
## 参照  
 [入力ストリーム](../standard-library/input-streams.md)