---
title: "basic_fstream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_fstream"
  - "basic_fstream"
  - "fstream/std::basic_fstream"
  - "std.basic_fstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_fstream クラス"
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# basic_fstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Elem` 型の要素を含む [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> クラスのストリーム バッファーを使用して要素とエンコードされたオブジェクトを挿入および抽出する際に、この処理を制御するオブジェクトを記述します。この型の特性は、`Tr` クラスによって決定されます。  
  
## 構文  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_fstream : public basic_iostream<Elem, Tr>  
```  
  
#### パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 \(通常は `char_traits`\<`Elem`\>\)。  
  
## 解説  
 このオブジェクトは、クラス `basic_filebuf`\<`Elem`, `Tr`\>  のオブジェクトを格納します。  
  
> [!NOTE]
>  fstream オブジェクトの get ポインターおよび put ポインターは、互いに独立したポインターでは**ありません**。  get ポインターが移動すると、put ポインターも移動します。  
  
## 使用例  
 次の例で、読み取りと書き込みが可能な `basic_fstream` オブジェクトの作成方法を示します。  
  
```  
// basic_fstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);  
    if (!fs.bad())  
    {  
        // Write to the file.  
        fs << "Writing to a basic_fstream object..." << endl;  
        fs.close();  
  
        // Dump the contents of the file to cout.  
        fs.open("fstream.txt", ios::in);  
        cout << fs.rdbuf();  
        fs.close();  
    }  
}  
```  
  
  **basic\_fstream オブジェクトに書き込んでいます...**   
### コンストラクター  
  
|||  
|-|-|  
|[basic\_fstream](../Topic/basic_fstream::basic_fstream.md)|`basic_fstream` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[閉じる](../Topic/basic_fstream::close.md)|ファイルを閉じます。|  
|[is\_open](../Topic/basic_fstream::is_open.md)|ファイルが開いているかどうかを判断します。|  
|[開く](../Topic/basic_fstream::open.md)|ファイルを開きます。|  
|[rdbuf](../Topic/basic_fstream::rdbuf.md)|pointer 型の格納されたストリーム バッファーのアドレスを [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> に返します。|  
|[swap](../Topic/basic_fstream::swap.md)|このオブジェクトの内容を別の `basic_fstream` オブジェクトの内容と交換します。|  
  
## 必要条件  
 **ヘッダー:** \<fstream\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)