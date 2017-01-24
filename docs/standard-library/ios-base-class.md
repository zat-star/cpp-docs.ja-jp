---
title: "ios_base クラス | Microsoft Docs"
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
  - "ios_base"
  - "std.ios_base"
  - "std::ios_base"
  - "xiosbase/std::ios_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios_base クラス"
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ios_base クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このクラスは、テンプレート パラメーターに依存しない、入力ストリームと出力ストリームの両方に共通のストレージとメンバー関数を表します。  \(テンプレート クラス [basic\_ios](../Topic/basic_ios%20Class.md) は共通な要素を記述しますが、テンプレート パラメーターに依存します。\)  
  
 ios\_base クラスのオブジェクトには、次の情報で構成される書式設定情報が格納されます。  
  
-   [fmtflags](../Topic/ios_base::fmtflags.md) 型のオブジェクトの書式指定フラグ。  
  
-   [iostate](../Topic/ios_base::iostate.md) 型のオブジェクト内の例外マスク。  
  
-   `int` 型のオブジェクトのフィールド幅*。*  
  
-   `int` 型のオブジェクトの表示桁数。  
  
-   **locale** 型のオブジェクトのロケール オブジェクト。  
  
-   **long** 型と `void` ポインターの要素を含む 2 つの拡張可能な配列。  
  
 ios\_base クラスのオブジェクトでは、ストリームの状態情報が [iostate](../Topic/ios_base::iostate.md) 型のオブジェクトに格納されるほか、コールバックのスタックも格納されます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[ios\_base](../Topic/ios_base::ios_base.md)|`ios_base` オブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[event\_callback](../Topic/ios_base::event_callback.md)|[register\_call](../Topic/ios_base::register_callback.md) に渡される関数を記述します。|  
|[fmtflags](../Topic/ios_base::fmtflags.md)|出力の外観を指定する定数。|  
|[iostate](../Topic/ios_base::iostate.md)|ストリームの状態を表す定数を定義します。|  
|[openmode](../Topic/ios_base::openmode.md)|ストリームとの対話方法を記述します。|  
|[seekdir](../Topic/ios_base::seekdir.md)|オフセット演算の開始位置を指定します。|  
  
### 列挙体  
  
|||  
|-|-|  
|[イベント](../Topic/ios_base::event.md)|イベントの種類を指定します。|  
  
### 定数  
  
|||  
|-|-|  
|[adjustfield](../Topic/ios_base::fmtflags.md)|`internal` として定義されるビットマスク。                      &#124; `left` &#124; `right`.|  
|[app](../Topic/ios_base::openmode.md)|各挿入前にストリームの末尾にシークするように指定します。|  
|[ate](../Topic/ios_base::openmode.md)|コントロール オブジェクトが最初に作成されたときに、ストリームの末尾にシークするように指定します。|  
|[badbit](../Topic/ios_base::iostate.md)|ストリーム バッファーの整合性の損失を記録します。|  
|[basefield](../Topic/ios_base::fmtflags.md)|`dec` として定義されるビットマスク。                      &#124; `hex` &#124; `oct`.|  
|[beg](../Topic/ios_base::seekdir.md)|シーケンスの先頭からの相対シークを指定します。|  
|[バイナリ](../Topic/ios_base::openmode.md)|テキスト ストリームではなく、バイナリ ストリームとしてファイルを読み取るように指定します。|  
|[boolalpha](../Topic/ios_base::fmtflags.md)|`bool` 型のオブジェクトを数値ではなく名前 \(`true` や `false` など\) で挿入もしくは抽出するように指定します。|  
|[cur](../Topic/ios_base::seekdir.md)|シーケンス内の現在位置からの相対シークを指定します。|  
|[dec](../Topic/ios_base::fmtflags.md)|10 進形式で整数値を挿入もしくは抽出するように指定します。|  
|[End](../Topic/ios_base::seekdir.md)|シーケンスの末尾からの相対シークを指定します。|  
|[eofbit](../Topic/ios_base::iostate.md)|ストリームからの抽出中にファイルの終わりを記録します。|  
|[failbit](../Topic/ios_base::iostate.md)|ストリームからの有効フィールドの抽出エラーを記録します。|  
|[固定](../Topic/ios_base::fmtflags.md)|固定小数点形式 \(指数フィールドなし\) で浮動小数点値を挿入するように指定します。|  
|[floatfield](../Topic/ios_base::fmtflags.md)|`fixed` として定義されるビットマスク。                      &#124; `scientific`|  
|[goodbit](../Topic/ios_base::iostate.md)|状態ビットをすべてクリアします。|  
|[hex](../Topic/ios_base::fmtflags.md)|16 進数形式で整数値を挿入もしくは抽出するように指定します。|  
|[in](../Topic/ios_base::openmode.md)|ストリームからの抽出を指定します。|  
|[internal](../Topic/ios_base::fmtflags.md)|生成された数値フィールドの内部ポイントに充てん文字を挿入することにより、フィールド幅を埋めます。|  
|[左へ](../Topic/ios_base::fmtflags.md)|左揃えを指定します。|  
|[oct](../Topic/ios_base::fmtflags.md)|8 進数形式で整数値を挿入もしくは抽出するように指定します。|  
|[out](../Topic/ios_base::openmode.md)|ストリームへの挿入を指定します。|  
|[右](../Topic/ios_base::fmtflags.md)|右揃えを指定します。|  
|[指数](../Topic/ios_base::fmtflags.md)|指数形式 \(指数フィールドあり\) で浮動小数点値を挿入するように指定します。|  
|[showbase](../Topic/ios_base::fmtflags.md)|生成された整数フィールドのベースを示すプレフィックスを挿入するように指定します。|  
|[showpoint](../Topic/ios_base::fmtflags.md)|生成された浮動小数点フィールドに無条件で小数点を挿入するように指定します。|  
|[showpos](../Topic/ios_base::fmtflags.md)|生成された負の値を取らない数値フィールドにプラス記号を挿入するように指定します。|  
|[skipws](../Topic/ios_base::fmtflags.md)|特定の抽出の前に、先頭の空白文字をスキップすることを指定します。|  
|[trunc](../Topic/ios_base::openmode.md)|既存のファイルのコントロール オブジェクトが作成されたときに、そのファイルの内容を削除するように指定します。|  
|[unitbuf](../Topic/ios_base::fmtflags.md)|各挿入後に出力をフラッシュします。|  
|[大文字](../Topic/ios_base::fmtflags.md)|特定の挿入で小文字に対応する大文字を挿入するように指定します。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[エラー](../Topic/ios_base::failure.md)|このメンバー クラスは、テンプレート クラス [basic\_ios](../Topic/basic_ios%20Class.md) のメンバー関数 [clear](../Topic/basic_ios::clear.md) によってスローされるすべての例外の基底クラスとして機能します。|  
|[フラグ](../Topic/ios_base::flags.md)|現在のフラグ設定を設定するか返します。|  
|[getloc](../Topic/ios_base::getloc.md)|格納されているロケール オブジェクトを返します。|  
|[imbue](../Topic/ios_base::imbue.md)|ロケールを変更します。|  
|[Init](../Topic/ios_base::Init.md)|構築時に標準の iostream オブジェクトを作成します。|  
|[iword](../Topic/ios_base::iword.md)|`iword` として格納される値を割り当てます。|  
|[精度](../Topic/ios_base::precision.md)|浮動小数点数で表示する桁数を指定します。|  
|[pword](../Topic/ios_base::pword.md)|`pword` として格納される値を割り当てます。|  
|[register\_callback](../Topic/ios_base::register_callback.md)|コールバック関数を指定します。|  
|[setf](../Topic/ios_base::setf.md)|指定したフラグを設定します。|  
|[sync\_with\_stdio](../Topic/ios_base::sync_with_stdio.md)|iostream と C ランタイム ライブラリの処理が、ソース コードに現れる順序で実行されるようにします。|  
|[unsetf](../Topic/ios_base::unsetf.md)|指定したフラグをオフにします。|  
|[幅](../Topic/ios_base::width.md)|出力ストリームの長さを設定します。|  
|[xalloc](../Topic/ios_base::xalloc.md)|変数がストリームの一部となるように指定します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/ios_base::operator=.md)|`ios_base` オブジェクトの代入演算子。|  
  
## 必要条件  
 **ヘッダー:** \<ios\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)