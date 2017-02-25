---
title: "&lt;fstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::<fstream>"
  - "<fstream>"
  - "std.<fstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fstream ヘッダー"
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# &lt;fstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

外部ファイルに格納されているシーケンスの iostream の操作をサポートする複数のクラスを定義します。  
  
## 構文  
  
```  
  
#include <fstream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[filebuf](../Topic/filebuf.md)|`char` テンプレート パラメーターに特化された型 `basic_filebuf`。|  
|[fstream](../Topic/fstream.md)|`char` テンプレート パラメーターに特化された型 `basic_fstream`。|  
|[ifstream](../Topic/ifstream.md)|`char` テンプレート パラメーターに特化された型 `basic_ifstream`。|  
|[ofstream](../Topic/ofstream.md)|`char` テンプレート パラメーターに特殊化された型 `basic_ofstream`。|  
|[wfstream](../Topic/wfstream.md)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_fstream`。|  
|[wifstream](../Topic/wifstream.md)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_ifstream`。|  
|[wofstream](../Topic/wofstream.md)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_ofstream`。|  
|[wfilebuf](../Topic/wfilebuf.md)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_filebuf`。|  
  
### クラス  
  
|||  
|-|-|  
|[basic\_filebuf](../standard-library/basic-filebuf-class.md)|このテンプレート クラスは、**Elem** 型の要素と外部ファイルに格納されている要素のシーケンスとの間でやり取りされる転送を制御するストリーム バッファーを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
|[basic\_fstream](../standard-library/basic-fstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> クラスのストリーム バッファーを使用して要素とエンコードされたオブジェクトを挿入または抽出する際に、その処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
|[basic\_ifstream](../standard-library/basic-ifstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> クラスのストリーム バッファーから要素とエンコードされたオブジェクトを抽出する処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
|[basic\_ofstream](../standard-library/basic-ofstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**\> クラスのストリーム バッファーに要素とエンコードされたオブジェクトを挿入する処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)