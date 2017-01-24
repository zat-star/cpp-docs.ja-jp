---
title: "&lt;strstream&gt; | Microsoft Docs"
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
  - "std.<strstream>"
  - "std::<strstream>"
  - "<strstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream ヘッダー"
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;strstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`char` オブジェクトに割り当てられた配列に格納されているシーケンスの iostreams 操作をサポートする複数のクラスを定義します。  このようなシーケンスは、C 文字列と簡単に相互変換できます。  
  
## 構文  
  
```  
  
#include <strstream>  
  
```  
  
## 解説  
 型 `strstream` のオブジェクトは C 文字列の `char` \* を使用します。  [\<sstream\>](../standard-library/sstream.md) を使用して、型 [basic\_string](../standard-library/basic-string-class.md) のオブジェクトを操作します。  
  
> [!NOTE]
>  `<strstream>` のクラスの使用は推奨されていません。  代わりに、`<sstream>` のクラスの使用を検討してください。  
  
### クラス  
  
|||  
|-|-|  
|[strstreambuf クラス](../standard-library/strstreambuf-class.md)|このクラスは `char` 配列オブジェクトに格納されている要素のシーケンス間で要素の送信を制御するストリーム バッファーを表します。|  
|[istrstream クラス](../standard-library/istrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。|  
|[ostrstream クラス](../Topic/ostrstream%20Class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。|  
|[strstream クラス](../standard-library/strstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。|  
  
## 参照  
 [\<strstream\>](../standard-library/strstream.md)   
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)