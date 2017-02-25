---
title: "strstreambuf クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.strstreambuf"
  - "strstreambuf"
  - "std::strstreambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstreambuf クラス"
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# strstreambuf クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`char` 配列オブジェクトに格納されている要素のシーケンスとの間で行う、要素の送信を制御するストリーム バッファーを表します。  
  
## 構文  
  
```  
  
class strstreambuf : public streambuf  
  
```  
  
## 解説  
 オブジェクトの構築方法に応じて、シーケンスにおける変更に対応できるように割り当て、拡張、解放を必要に応じて行えます。  
  
 クラス `strstreambuf` のオブジェクトは、`strstreambuf` モードのモード情報が入っているいくつかのビットを格納します。 これらのビットは、制御対象シーケンスに関して次の情報を示します。  
  
-   割り当てがなされていて、最終的に解放する必要があるかどうか。  
  
-   変更可能かどうか。  
  
-   記憶域の再割り当てによって拡張可能かどうか。  
  
-   操作できないようにされていて、オブジェクトを破棄する前に操作できるようにする必要があるかどうか、またはオブジェクト以外のエージェンシーで解放する必要があるかどうか \(割り当てがなされている場合\)。  
  
 操作できないようにされている制御対象シーケンスは、これらの別個のモード ビットに関係なく、変更も拡張もできません。  
  
 またオブジェクトは、`strstreambuf` 割り当てを制御する 2 つの関数へのポインターも格納します。 これらが null ポインターである場合、オブジェクトは制御対象シーケンスに対して記憶域の割り当ておよび解放を行う独自のメソッドを考案します。  
  
> [!NOTE]
>  このクラスは使用されていません。 使用を検討して [stringbuf](../Topic/stringbuf.md) または [wstringbuf](../Topic/wstringbuf.md) 代わりにします。  
  
### コンストラクター  
  
|||  
|-|-|  
|[strstreambuf](../Topic/strstreambuf::strstreambuf.md)|`strstreambuf` 型のオブジェクトを構築します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[freeze](../Topic/strstreambuf::freeze.md)|ストリーム バッファーの操作により、ストリーム バッファーを使用不可にします。|  
|[オーバーフロー](../Topic/strstreambuf::overflow.md)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|  
|[pbackfail](../Topic/strstreambuf::pbackfail.md)|要素を入力ストリームに戻してから、その要素を現在の要素 \(ネクスト ポインターによって指される\) にしようとするプロテクト仮想メンバー関数。|  
|[pcount](../Topic/strstreambuf::pcount.md)|被制御シーケンスに書き込まれる要素の数を返します。|  
|[seekoff](../Topic/strstreambuf::seekoff.md)|制御対象ストリームの現在の位置を変更しようと試みるプロテクト仮想メンバー関数。|  
|[seekpos](../Topic/strstreambuf::seekpos.md)|制御対象ストリームの現在の位置を変更しようと試みるプロテクト仮想メンバー関数。|  
|[str](../Topic/strstreambuf::str.md)|[freeze](../Topic/strstreambuf::freeze.md) を呼び出し、被制御シーケンスの先頭へのポインターを返します。|  
|[underflow](../Topic/strstreambuf::underflow.md)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|  
  
## 必要条件  
 **ヘッダー:** \<strstream\>  
  
 **名前空間:** std  
  
## 参照  
 [streambuf](../Topic/streambuf.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)