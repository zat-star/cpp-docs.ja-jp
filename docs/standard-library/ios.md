---
title: "&lt;ios&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<ios>"
  - "std::<ios>"
  - "<ios>"
  - "ios/std::<ios>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios ヘッダー"
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;ios&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

iostream 操作の基礎となる型と関数を定義します。  このヘッダーは通常、別の iostream ヘッダーによってインクルードされており、ユーザーが直接インクルードすることはほとんどありません。  
  
## 構文  
  
```  
  
#include <ios>  
  
```  
  
## 解説  
 マニピュレーターとは、多種類の関数のグループです。  \<ios\> 内で宣言されたマニピュレーターは、[ios\_base](../standard-library/ios-base-class.md) クラスの引数オブジェクトに格納された値を変更します。  その他のマニピュレーターは、[basic\_istream](../Topic/basic_istream%20Class.md) と [basic\_ostream](../Topic/basic_ostream%20Class.md) のいずれかのテンプレート クラスの特殊化など、ios\_base クラスから派生した型のオブジェクトによって制御されるストリームに対して操作を実行します。  たとえば、[noskipws](../Topic/noskipws.md)\(**str**\) は、ios\_base クラスから派生する型の 1 つであり、**str** オブジェクトの書式フラグ `ios_base::skipws` をオフにします。  
  
 マニピュレーターは、出力ストリームに挿入したり、入力ストリームから抽出したりすることでも呼び出すことができます。これは、`ios_base` から派生したクラスに特殊な挿入演算子と抽出演算子が指定されるためです。  例:  
  
```  
istr >> noskipws;  
```  
  
 [noskipws](../Topic/noskipws.md)\(**istr**\) を呼び出します。  
  
### Typedefs  
  
|||  
|-|-|  
|[ios](../Topic/ios.md)|従来の iostream ライブラリの ios クラスをサポートします。|  
|[streamoff](../Topic/streamoff.md)|内部操作をサポートします。|  
|[streampos](../Topic/streampos.md)|バッファー ポインターまたはファイル ポインターの現在の位置を保持します。|  
|[streamsize](../Topic/streamsize.md)|ストリームのサイズを指定します。|  
|[wios](../Topic/wios.md)|従来の iostream ライブラリの wios クラスをサポートします。|  
|[wstreampos](../Topic/wstreampos.md)|バッファー ポインターまたはファイル ポインターの現在の位置を保持します。|  
  
### マニピュレーター  
  
|||  
|-|-|  
|[boolalpha](../Topic/boolalpha.md)|[bool](../cpp/bool-cpp.md) 型の変数をストリームで **true** または **false** として表示するように指定します。|  
|[dec](../Topic/dec.md)|整数変数を 10 進表記で表示するように指定します。|  
|[defaultfloat](../Topic/%3Cios%3E%20defaultfloat.md)|浮動小数値に既定の表示形式を使用するように、`ios_base` オブジェクトのフラグを構成します。|  
|[固定](../Topic/fixed.md)|浮動小数点数を固定 10 進表記で表示するように指定します。|  
|[hex](../Topic/hex.md)|整数変数を 16 進表記で表示するように指定します。|  
|[internal](../Topic/internal%20\(Standard%20C++%20Library\).md)|数値の符号を左揃え、数値を右揃えにします。|  
|[左へ](../Topic/left.md)|出力幅に満たないテキストをストリーム フラッシュで左揃えに表示します。|  
|[noboolalpha](../Topic/noboolalpha.md)|[bool](../cpp/bool-cpp.md) 型の変数をストリームで 1 または 0 として表示するように指定します。|  
|[noshowbase](../Topic/noshowbase.md)|指定している数値表記の基底の設定をオフにします。|  
|[noshowpoint](../Topic/noshowpoint.md)|小数部分が 0 の浮動小数点数の整数部分のみを表示します。|  
|[noshowpos](../Topic/noshowpos.md)|正の数値に明示的に符号を付けないようにします。|  
|[noskipws](../Topic/noskipws.md)|入力ストリームで空白を読み取るようにします。|  
|[nounitbuf](../Topic/nounitbuf.md)|出力をバッファーし、バッファーが一杯になると、出力を処理します。|  
|[nouppercase](../Topic/nouppercase.md)|16 進数と指数表記の指数を小文字で表示します。|  
|[oct](../Topic/oct%20\(%3Cios%3E\).md)|整数変数を 8 進表記で表示するように指定します。|  
|[右](../Topic/right.md)|出力幅に満たないテキストをストリーム フラッシュで右揃えに表示します。|  
|[指数](../Topic/scientific.md)|浮動小数点数値を指数表記を使用して表示します。|  
|[showbase](../Topic/showbase.md)|数値表記の基底を指定します。|  
|[showpoint](../Topic/showpoint.md)|小数部分が 0 のときも浮動小数点数の整数部分と小数点の右側にある数字を表示します。|  
|[showpos](../Topic/showpos.md)|正の数値に明示的に符号を付けます。|  
|[skipws](../Topic/skipws.md)|入力ストリームで空白を読み飛ばします。|  
|[unitbuf](../Topic/unitbuf.md)|バッファーが空ではないときに、出力を処理します。|  
|[大文字](../Topic/uppercase.md)|16 進数と指数表記の指数を大文字で表示します。|  
  
### クラス  
  
|||  
|-|-|  
|[basic\_ios](../Topic/basic_ios%20Class.md)|このテンプレート クラスは、テンプレート パラメーターに依存する、入力ストリーム\([basic\_istream](../Topic/basic_istream%20Class.md) テンプレート クラス\) と出力ストリーム \([basic\_ostream](../Topic/basic_ostream%20Class.md) テンプレート クラス\) の両方に共通のストレージとメンバー関数を表します。|  
|[fpos](../Topic/fpos%20Class.md)|このテンプレート クラスは、システム内の任意のファイル位置インジケーターを復元するために必要なすべての情報を格納できるオブジェクトを表します。|  
|[ios\_base](../standard-library/ios-base-class.md)|このクラスは、テンプレート パラメーターに依存しない、入力ストリームと出力ストリームの両方に共通のストレージとメンバー関数を表します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)