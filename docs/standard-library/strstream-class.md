---
title: "strstream クラス | Microsoft Docs"
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
  - "std::strstream"
  - "strstream"
  - "std.strstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream クラス"
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
caps.latest.revision: 21
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strstream クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。  
  
## 構文  
  
```  
  
class strstream : public iostream  
  
```  
  
## 解説  
 このオブジェクトは、クラス `strstreambuf` のオブジェクトを格納します。  
  
> [!NOTE]
>  このクラスは使用されていません。  代わりに、[stringstream](../Topic/stringstream.md) または [wstringstream](../Topic/wstringstream.md) を使用することを検討してください。  
  
### コンストラクター  
  
|||  
|-|-|  
|[strstream](../Topic/strstream::strstream.md)|`strstream` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[freeze](../Topic/strstream::freeze.md)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|  
|[pcount](../Topic/strstream::pcount.md)|被制御シーケンスに書き込まれる要素の数を返します。|  
|[rdbuf](../Topic/strstream::rdbuf.md)|ストリームの関連付けられた `strstreambuf` オブジェクトへのポインターを返します。|  
|[str](../Topic/strstream::str.md)|[freeze](../Topic/strstreambuf::freeze.md) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|  
  
## 必要条件  
 **ヘッダー:** \<strstream\>  
  
 **名前空間:** std  
  
## 参照  
 [iostream](../Topic/iostream.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)