---
title: "basic_ofstream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::basic_ofstream"
  - "basic_ofstream"
  - "std.basic_ofstream"
  - "fstream/std::basic_ofstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ofstream クラス"
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 24
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_ofstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Elem` 型の要素を含む [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> クラスのストリーム バッファーに要素とエンコードされたオブジェクトを挿入する際に、この処理を制御するオブジェクトを記述します。この型の特性は、`Tr` クラスによって決定されます。  
  
## 構文  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ofstream : public basic_ostream<Elem, Tr>  
```  
  
#### パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 \(通常は `char_traits`\<`Elem`\>\)。  
  
## 解説  
 `basic_ofstream` を `wchar_t` で特殊化したクラスがファイルに書き込みを行う場合、ファイルがテキスト モードで開かれていると、MBCS シーケンスが書き込まれます。  内部表現には `wchar_t` 文字のバッファーが使用されます。  
  
 このオブジェクトは、クラス `basic_filebuf`\<`Elem`, `Tr`\> のオブジェクトを格納します。  
  
## 使用例  
 次の例では、`basic_ofstream` オブジェクトを作成して、これにテキストを書き込む方法を示します。  
  
```  
// basic_ofstream_class.cpp  
// compile with: /EHsc  
#include <fstream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ofstream ofs("ofstream.txt");  
    if (!ofs.bad())  
    {  
        ofs << "Writing to a basic_ofstream object..." << endl;  
        ofs.close();  
    }  
}  
```  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_ofstream](../Topic/basic_ofstream::basic_ofstream.md)|`basic_ofstream` 型のオブジェクトを作成します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[閉じる](../Topic/basic_ofstream::close.md)|ファイルを閉じます。|  
|[is\_open](../Topic/basic_ofstream::is_open.md)|ファイルが開いているかどうかを判断します。|  
|[開く](../Topic/basic_ofstream::open.md)|ファイルを開きます。|  
|[rdbuf](../Topic/basic_ofstream::rdbuf.md)|格納されたストリーム バッファーのアドレスを返します。|  
|[swap](../Topic/basic_ofstream::swap.md)|この `basic_ofstream` の内容を、指定された `basic_ofstream` の内容と交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ofstream::operator=.md)|このストリーム オブジェクトの内容を割り当てます。  これは、`rvalue reference` が関係する移動代入で、コピーを残しません。|  
  
## 必要条件  
 **ヘッダー:** \<fstream\>  
  
 **名前空間:** std  
  
## 参照  
 [basic\_ostream クラス](../Topic/basic_ostream%20Class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)