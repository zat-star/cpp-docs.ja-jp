---
title: "basic_filebuf クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.basic_filebuf"
  - "fstream/std::basic_filebuf"
  - "std::basic_filebuf"
  - "basic_filebuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_filebuf クラス"
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_filebuf クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素と、外部ファイルに格納されている要素のシーケンスとの間でやり取りされる転送を制御するストリーム バッファーを記述します。  
  
## 構文  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_filebuf : public basic_streambuf<Elem, Tr>  
```  
  
#### パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 \(通常は `char_traits`\<`Elem`\>\)。  
  
## 解説  
 このテンプレート クラスは、文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素と、外部ファイルに格納されている要素のシーケンスとの間でやり取りされる転送を制御するストリーム バッファーを記述します。  
  
> [!NOTE]
>  型パラメーター `Elem` で指定された `char_type` に関係なく、`basic_filebuf` 型のオブジェクトが `char *` 型の内部バッファーと共に作成されます。  これは、\(`wchar_t` 文字を含む\) Unicode 文字列が内部バッファーに書き込まれる前に \(`char` 文字を含む\) ANSI 文字列に変換されることを意味します。  Unicode 文字列をバッファーに格納するには、`wchar_t` 型の新しいバッファーを作成し、[basic\_streambuf::pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)`()` メソッドを使用して設定します。  この動作を示す例については、以降のセクションを参照してください。  
  
 `basic_filebuf`\<`Elem`, `Tr`\>  クラスのオブジェクトは、開いているファイルに関連付けられているストリームを制御する `FILE` オブジェクトを示すファイル ポインターを格納します。  さらに、プロテクト メンバー関数である [overflow](../Topic/basic_filebuf::overflow.md) と [underflow](../Topic/basic_filebuf::underflow.md) で使用される 2 つのファイル変換ファセットへのポインターも格納します。  詳細については、「[basic\_filebuf::open](../Topic/basic_filebuf::open.md)」を参照してください。  
  
## 使用例  
 次の例では、`pubsetbuf()` メソッドを呼び出して、`basic_filebuf<wchar_t>` 型のオブジェクトの内部バッファーに Unicode 文字を強制的に格納しています。  
  
```  
// unicode_basic_filebuf.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
#include <fstream>  
#include <iomanip>  
#include <memory.h>  
#include <string.h>  
  
#define IBUFSIZE 16  
  
using namespace std;  
  
void hexdump(const string& filename);  
  
int main()  
{  
    wchar_t* wszHello = L"Hello World";  
    wchar_t wBuffer[128];  
  
    basic_filebuf<wchar_t> wOutFile;  
  
    // Open a file, wcHello.txt, then write to it, then dump the  
    // file's contents in hex  
    wOutFile.open("wcHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wcHello.txt\n";  
        return -1;  
    }  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";  
    hexdump(string("wcHello.txt"));  
  
    // Open a file, wwHello.txt, then set the internal buffer of  
    // the basic_filebuf object to be of type wchar_t, then write  
    // to the file and dump the file's contents in hex  
    wOutFile.open("wwHello.txt",  
        ios_base::out | ios_base::trunc | ios_base::binary);  
    if(!wOutFile.is_open())  
    {  
        cout << "Error Opening wwHello.txt\n";  
        return -1;  
    }  
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);  
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));  
    wOutFile.close();  
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";  
    hexdump(string("wwHello.txt"));  
  
    return 0;  
}  
  
// dump contents of filename to stdout in hex  
void hexdump(const string& filename)  
{  
    fstream ifile(filename.c_str(),  
        ios_base::in | ios_base::binary);  
    char *ibuff = new char[IBUFSIZE];  
    char *obuff = new char[(IBUFSIZE*2)+1];  
    int i;  
  
    if(!ifile.is_open())  
    {  
        cout << "Cannot Open " << filename.c_str()  
             << " for reading\n";  
        return;  
    }  
    if(!ibuff || !obuff)  
    {  
        cout << "Cannot Allocate buffers\n";  
        ifile.close();  
        return;  
    }  
  
    while(!ifile.eof())  
    {  
        memset(obuff,0,(IBUFSIZE*2)+1);  
        memset(ibuff,0,IBUFSIZE);  
        ifile.read(ibuff,IBUFSIZE);  
  
        // corner case where file is exactly a multiple of  
        // 16 bytes in length  
        if(ibuff[0] == 0 && ifile.eof())  
            break;  
  
        for(i = 0; i < IBUFSIZE; i++)  
        {  
            if(ibuff[i] >= ' ')  
                obuff[i] = ibuff[i];  
            else  
                obuff[i] = '.';  
  
            cout << setfill('0') << setw(2) << hex  
                 << (int)ibuff[i] << ' ';  
        }  
        cout << "  " << obuff << endl;  
    }  
    ifile.close();  
}  
```  
  
  **Hex Dump of wcHello.txt \- note that output is ANSI chars:**  
**48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....  Hex Dump of wwHello.txt \- note that output is wchar\_t chars:**  
**48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o.  .W.o.  72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........**    
### コンストラクター  
  
|||  
|-|-|  
|[basic\_filebuf](../Topic/basic_filebuf::basic_filebuf.md)|`basic_filebuf` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_filebuf::char_type.md)|型名を `Elem` テンプレート パラメーターに関連付けます。|  
|[int\_type](../Topic/basic_filebuf::int_type.md)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|  
|[off\_type](../Topic/basic_filebuf::off_type.md)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|  
|[pos\_type](../Topic/basic_filebuf::pos_type.md)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|  
|[traits\_type](../Topic/basic_filebuf::traits_type.md)|型名を `Tr` テンプレート パラメーターに関連付けます。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[閉じる](../Topic/basic_filebuf::close.md)|ファイルを閉じます。|  
|[is\_open](../Topic/basic_filebuf::is_open.md)|ファイルが開いているかどうかを示します。|  
|[開く](../Topic/basic_filebuf::open.md)|ファイルを開きます。|  
|[オーバーフロー](../Topic/basic_filebuf::overflow.md)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|  
|[pbackfail](../Topic/basic_filebuf::pbackfail.md)|プロテクト仮想メンバー関数が要素を入力ストリームに戻そうと試み、その要素を現在の要素に \(次のポインターによって指されるように\) します。|  
|[seekoff](../Topic/basic_filebuf::seekoff.md)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|  
|[seekpos](../Topic/basic_filebuf::seekpos.md)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|  
|[setbuf](../Topic/basic_filebuf::setbuf.md)|プロテクト仮想メンバー関数が、各派生ストリーム バッファーに固有の操作を実行します。|  
|[swap](../Topic/basic_filebuf::swap.md)|この `basic_filebuf` の内容を、指定された `basic_filebuf` パラメーターの内容と交換します。|  
|[sync](../Topic/basic_filebuf::sync.md)|プロテクト仮想関数が、制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。|  
|[uflow](../Topic/basic_streambuf::uflow.md)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|  
|[underflow](../Topic/basic_filebuf::underflow.md)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|  
  
## 必要条件  
 **ヘッダー:** \<fstream\>  
  
 **名前空間:** std  
  
## 参照  
 [\<fstream\>](../standard-library/fstream.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)