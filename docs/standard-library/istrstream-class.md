---
title: "istrstream クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istrstream"
  - "std::istrstream"
  - "std.istrstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istrstream クラス"
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# istrstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。  
  
## 構文  
  
```  
  
class istrstream : public istream  
  
```  
  
## 解説  
 このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。  
  
> [!NOTE]
>  このクラスは使用されていません。 使用を検討して [istringstream](../Topic/istringstream.md) または [wistringstream](../Topic/wistringstream.md) 代わりにします。  
  
### コンストラクター  
  
|||  
|-|-|  
|[istrstream](../Topic/istrstream::istrstream.md)|`istrstream` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[rdbuf](../Topic/istrstream::rdbuf.md)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|  
|[str](../Topic/istrstream::str.md)|[freeze](../Topic/strstreambuf::freeze.md) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|  
  
## 必要条件  
 **ヘッダー:** \<strstream\>  
  
 **名前空間:** std  
  
## 参照  
 [istream](../Topic/istream.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)