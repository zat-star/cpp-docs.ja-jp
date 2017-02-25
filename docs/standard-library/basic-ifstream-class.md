---
title: "basic_ifstream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_ifstream"
  - "fstream/std::basic_ifstream"
  - "std::basic_ifstream"
  - "std.basic_ifstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ifstream クラス"
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# basic_ifstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Elem` 型の要素を含む [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> クラスのストリーム バッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを記述します。この型の特性は、`Tr` クラスによって決定されます。  
  
## 構文  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### パラメーター  
 `Elem`  
 ファイル バッファーの基本要素。  
  
 `Tr`  
 ファイル バッファーの基本要素の特徴 \(通常は `char_traits`\<`Elem`\>\)。  
  
## 解説  
 このオブジェクトは、クラス `basic_filebuf`\<`Elem`, `Tr`\> のオブジェクトを格納します。  
  
## 使用例  
 次の例は、ファイルからテキストを読み取る方法を示しています。  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## 入力: basic\_ifstream\_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## 出力  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_ifstream](../Topic/basic_ifstream::basic_ifstream.md)|`basic_ifstream` オブジェクトの新しいインスタンスを初期化します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[閉じる](../Topic/basic_ifstream::close.md)|ファイルを閉じます。|  
|[is\_open](../Topic/basic_ifstream::is_open.md)|ファイルが開いているかどうかを判断します。|  
|[開く](../Topic/basic_ifstream::open.md)|ファイルを開きます。|  
|[rdbuf](../Topic/basic_ifstream::rdbuf.md)|格納されたストリーム バッファーのアドレスを返します。|  
|[swap](../Topic/basic_ifstream::swap.md)|この `basic_ifstream` の内容を、指定された `basic_ifstream` の内容と交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_ifstream::operator=.md)|このストリーム オブジェクトの内容を割り当てます。  これは、`rvalue` が関係する移動代入で、コピーを残しません。|  
  
## 必要条件  
 **ヘッダー:** \<fstream\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)