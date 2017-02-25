---
title: "出力ファイル ストリームのメンバー関数 | Microsoft Docs"
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
  - "出力ストリーム, メンバー関数"
ms.assetid: 38aaf710-8035-4a34-a0c4-123a5327f28a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 出力ファイル ストリームのメンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力ストリームのメンバー関数の 3 種類があります。: マニピュレーターと等価であり、フォーマットされていない書き込み操作を実行されるなどでストリームの状態を変更し、同等のマニピュレーターまたは出力ストリーム演算子が存在しないを。  順次では、書式付き出力、出力ストリーム演算子およびマニピュレーターのみ使用することがあります。  ランダム アクセス バイナリ ディスクの出力の出力ストリーム演算子の有無に関係なく他のメンバー関数を使用します。  
  
## 出力ストリームの Open 関数  
 出力ファイル ストリーム \([ofstream](../Topic/ofstream.md)\) を使用するには、コンストラクターまたは **開く** 関数の特定のディスク ファイルとストリームに関連付ける必要があります。  **開く** 関数を使用すると、一連のファイルと同じストリーム オブジェクトを再利用できます。  いずれの場合も、ファイルを説明する引数は同じです。  
  
 出力ストリームに関連付けられたファイルを開くときに一般的に **open\_mode** フラグを指定します。  ビットごとのの `ios` クラスの列挙子と、\(定義されたこれらのフラグを結合できます。&#124; 演算子\)。  列挙子のリストの [ios\_base::openmode](../Topic/ios_base::openmode.md) を参照してください。  
  
 3 個の出力ストリームの状況は、mode オプションが T:  
  
-   ファイルの作成。  ファイルが既に存在する場合、古いバージョンが削除されます。  
  
    ```  
    ostream ofile( "FILENAME" );  // Default is ios::out  
    ofstream ofile( "FILENAME", ios::out ); // Equivalent to above  
    ```  
  
-   あるレコードを既存のファイルまたは 1 個作成に付けます。  
  
    ```  
    ofstream ofile( "FILENAME", ios::app );  
    ```  
  
-   同じストリームの 2 種類のファイルについて一つずつ、開きます。  
  
    ```  
    ofstream ofile();  
    ofile.open( "FILE1", ios::in );  
    // Do some output  
    ofile.close(); // FILE1 closed  
    ofile.open( "FILE2", ios::in );  
    // Do some more output  
    ofile.close(); // FILE2 closed  
    // When ofile goes out of scope it is destroyed.  
    ```  
  
## Put 関数  
 **put** 関数は出力ストリームに 1 文字を書き込みます。  次の 2 種類のステートメントは既定で同じですが、2 番目はストリーム引数 format によって影響を受ける:  
  
```  
cout.put( 'A' ); // Exactly one character written  
cout << 'A'; // Format arguments 'width' and 'fill' apply   
```  
  
## Write 関数  
 **書き込み** 関数は出力ファイル ストリームのメモリ ブロックを作成します。  長さの引数を書き込むバイト数を指定します。  この例では、出力ファイル ストリームを作成し、`Date` 構造体のバイナリ値を書き込む:  
  
```  
// write_function.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
  
struct Date  
{  
   int mo, da, yr;  
};  
  
int main( )  
{  
   Date dt = { 6, 10, 92 };  
   ofstream tfile( "date.dat" , ios::binary );  
   tfile.write( (char *) &dt, sizeof dt );  
}  
```  
  
 **書き込み** 関数は null 文字に到達するため、完全なクラス構造体が書き込まれますと停止しません。  関数は 2 個の引数を受け取ります。: 文字の `char` のポインターと書き込む数。  構造体オブジェクト アドレスの前に **char\*** に必要なキャストに注意してください。  
  
## seekp と tellp 関数  
 出力ファイルのストリームはデータが次に書き込まれる位置に内部ポインターを指すです。  `seekp` のメンバー関数は、this ポインターを設定し、それによってランダム アクセス ディスク ファイルの出力を提供します。  `tellp` のメンバー関数は、ファイルの位置を返します。  `seekp` と `tellp`に入力ストリームの等価の使用例については、[seekg と tellg 関数](../standard-library/input-stream-member-functions.md)を参照してください。  
  
## 出力ストリームの終了関数  
 **閉じる** のメンバー関数では、出力ファイルのストリームに関連付けられているディスク ファイルを閉じます。  ファイルはディスク上のすべての出力を完了するために閉じる必要があります。  必要に応じて、`ofstream` のデストラクターによってファイルを閉じて、同じストリーム オブジェクトごとに個別のファイルを開く必要がある場合 **閉じる** 関数を使用できます。  
  
 出力ストリームのデストラクターは自動的にコンストラクターまたは **開く** のメンバー関数がファイルを開いたときにだけストリームのファイルを閉じます。  コンストラクターに既に開いているファイルへのファイル記述子を渡した場合、または **attach** メンバー関数を使用すると、ファイルを明示的に閉じる必要があります。  
  
##  <a name="vclrferrorprocessingfunctionsanchor10"></a> エラー処理機能  
 ストリームに書き込むときにエラーをテストするには、これらのメンバー関数を使用する:  
  
|関数|戻り値|  
|--------|---------|  
|[不適切な](../Topic/basic_ios::bad.md)|回復不能なエラーがある場合 **true** を返します。|  
|[失敗](../Topic/basic_ios::fail.md)|回復不能なエラーまたは「予測」状態が、変換エラーなど、か、ファイルが存在しない場合 **true** を返します。  処理は、ゼロと引数の **クリア** の呼び出し後に再開できます。|  
|[優れた](../Topic/basic_ios::good.md)|エラー条件 \(など\)、**true** を回復不能な返しますファイルの終端のフラグは設定されません。|  
|[eof](../Topic/basic_ios::eof.md)|終端の **true** ファイル ステータスを返します。|  
|[clear](../Topic/basic_ios::clear.md)|内部エラーの状態を設定します。  既定の引数があった場合、すべてのエラーをクリアします。|  
|[rdstate](../Topic/basic_ios::rdstate.md)|現在のエラー状態を返します。|  
  
 \#\#\#\!の演算子は **失敗** 関数と同じ機能を実行するためにオーバーロードされます。  したがって、式:  
  
```  
if( !cout)...  
```  
  
 上の式は、下の式と同等です。  
  
```  
if( cout.fail() )...  
```  
  
 **void\*\(\)** の演算子は \#\#\#\!の演算子の反対にオーバーロードされます; したがって、式:  
  
```  
if( cout)...  
```  
  
 と同等:  
  
```  
if( !cout.fail() )...  
```  
  
 **void\*\(\)** の演算子は、ファイルの終端をテストするため **good** と同等ではありません。  
  
## 参照  
 [出力ストリーム](../standard-library/output-streams.md)