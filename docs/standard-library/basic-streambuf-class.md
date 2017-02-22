---
title: "basic_streambuf クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_streambuf"
  - "streambuf/std::basic_streambuf"
  - "std.basic_streambuf"
  - "std::basic_streambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_streambuf クラス"
ms.assetid: 136af6c3-13bf-4501-9288-b93da26efac7
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# basic_streambuf クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ストリームの特定の表現との相互間での要素の伝送を制御する、ストリーム バッファーを派生させるための抽象基底クラスについて説明します。  
  
## 構文  
  
```  
template<class Elem, class Tr = char_traits<Elem> >  
   class basic_streambuf;  
```  
  
#### パラメーター  
 `Elem`  
 [char\_type](../Topic/basic_streambuf::char_type.md)。  
  
 `Tr`  
 文字の [traits\_type](../Topic/basic_streambuf::traits_type.md)。  
  
## 解説  
 このテンプレート クラスは、ストリームの特定の表現との相互間での要素の伝送を制御する、ストリーム バッファーを派生させるための抽象基底クラスについて説明します。  クラス `basic_streambuf` のオブジェクトは、[char\_type](../Topic/basic_streambuf::char_type.md) とも呼ばれる型 `Tr` の要素を含むストリームを制御するのに役立ちます。この型の文字特性は、[traits\_type](../Topic/basic_streambuf::traits_type.md) とも呼ばれる [char\_traits](../standard-library/char-traits-struct.md) クラスによって決まります。  
  
 各ストリーム バッファーは、抽出 \(入力\) 用ストリームと挿入 \(出力\) 用ストリームという 2 つの独立したストリームを概念上制御します。  ただし、特定の表現によってこれらのストリームのいずれか、もしくは両方がアクセス不可になる場合があります。  通常、そのような表現は、これら 2 つのストリームの何らかの関係を保持しています。  たとえば、[basic\_stringbuf](../Topic/basic_stringbuf%20Class.md)\<`Elem`, `Tr`\> オブジェクトの出力ストリームに挿入したものが、その入力ストリームから後で抽出するものになります。  [basic\_filebuf](../standard-library/basic-filebuf-class.md)\<`Elem`, `Tr`\> オブジェクトの 1 つのストリームを配置するときは、もう一方のストリームを直列に配置します。  
  
 テンプレート クラス `basic_streambuf` のパブリック インターフェイスでは、すべてのストリーム バッファーに共通な操作をそれぞれに特殊化して行えます。  保護されたインターフェイスでは、ストリームの特定の表現を動作させるのに必要な操作を行えます。  プロテクト仮想メンバー関数を使用することにより、ストリームの特定の表現に対する派生ストリーム バッファーの動作を調整できます。  このライブラリ内の各派生ストリーム バッファーで、各バッファーのプロテクト仮想メンバー関数に特殊化した動作方法について記述します。  基底クラスに対する既定の動作については \(多くの場合、何の動作も発生しない\)、このトピックで説明します。  
  
 残りのプロテクト メンバー関数は、ストリームとのバッファーのやり取りに提供されるストレージとのコピーのやり取りを制御します。  たとえば、入力バッファーには以下の特性を指定できます。  
  
-   [eback](../Topic/basic_streambuf::eback.md)、バッファーの先頭を指すポインター。  
  
-   [gptr](../Topic/basic_streambuf::gptr.md)、次に読み取る要素を指すポインター。  
  
-   [egptr](../Topic/basic_streambuf::egptr.md)、バッファーの末尾の直後を指すポインター。  
  
 同様に、出力バッファーには以下の特性を指定できます。  
  
-   [pbase](../Topic/basic_streambuf::pbase.md)、バッファーの先頭を指すポインター。  
  
-   [pptr](../Topic/basic_streambuf::pptr.md)、次に書き込む要素を指すポインター。  
  
-   [epptr](../Topic/basic_streambuf::epptr.md)、バッファーの末尾の直後を指すポインター。  
  
 どのバッファーの場合も、次のプロトコルが使用されます。  
  
-   ネクスト ポインターが null の場合、バッファーは存在しません。  それ以外の場合、3 つのポインターはすべて同じシーケンスを指し示します。  これらは順序で比較できます。  
  
-   出力バッファーの場合、ネクスト ポインターの比較対象がエンド ポインター未満であれば、ネクスト ポインターで指定された書き込み位置に要素を格納できます。  
  
-   入力バッファーの場合、ネクスト ポインターの比較対象がエンド ポインター未満であれば、ネクスト ポインターで指定された読み取り位置で要素を読み取ることができます。  
  
-   入力バッファーの場合、開始ポインターの比較対象がネクスト ポインター未満であれば、デクリメントされたネクスト ポインターで指定された戻り位置の要素を戻すことができます。  
  
 `basic_streambuf`\<`Elem`, `Tr`\> の派生クラス用に作成するプロテクト仮想メンバー関数すべては、このプロトコルを維持する点で協調して動作する必要があります。  
  
 クラス `basic_streambuf`\<`Elem`, `Tr`\> のオブジェクトは、ここまでで説明した 6 つのポインターを格納します。  また、派生ストリーム バッファーが使用する可能性のある [locale](../standard-library/locale-class.md) 型のオブジェクトのロケール オブジェクトを格納します。  
  
### コンストラクター  
  
|||  
|-|-|  
|[basic\_streambuf](../Topic/basic_streambuf::basic_streambuf.md)|`basic_streambuf` 型のオブジェクトを構築します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/basic_streambuf::char_type.md)|型名を `Elem` テンプレート パラメーターに関連付けます。|  
|[int\_type](../Topic/basic_streambuf::int_type.md)|`basic_streambuf` スコープ内の型名と `Elem` テンプレート パラメーターを関連付けます。|  
|[off\_type](../Topic/basic_streambuf::off_type.md)|`basic_streambuf` スコープ内の型名と `Elem` テンプレート パラメーターを関連付けます。|  
|[pos\_type](../Topic/basic_streambuf::pos_type.md)|`basic_streambuf` スコープ内の型名と `Elem` テンプレート パラメーターを関連付けます。|  
|[traits\_type](../Topic/basic_streambuf::traits_type.md)|型名を `Tr` テンプレート パラメーターに関連付けます。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[eback](../Topic/basic_streambuf::eback.md)|入力バッファーの先頭を指すポインターを返すプロテクト関数。|  
|[egptr](../Topic/basic_streambuf::egptr.md)|入力バッファーの末尾の直後を指すポインターを返すプロテクト関数。|  
|[epptr](../Topic/basic_streambuf::epptr.md)|出力バッファーの末尾の直後を指すポインターを返すプロテクト関数。|  
|[gbump](../Topic/basic_streambuf::gbump.md)|`_Count` を入力バッファーのネクスト ポインターに追加するプロテクト関数。|  
|[getloc](../Topic/basic_streambuf::getloc.md)|`basic_streambuf` オブジェクトのロケールを取得します。|  
|[gptr](../Topic/basic_streambuf::gptr.md)|入力バッファーの次の要素を指すポインターを返すプロテクト関数。|  
|[imbue](../Topic/basic_streambuf::imbue.md)|[pubimbue](../Topic/basic_streambuf::pubimbue.md) によって呼び出されるプロテクト仮想関数。|  
|[in\_avail](../Topic/basic_streambuf::in_avail.md)|バッファーから読み取る準備が整っている要素の数を返します。|  
|[オーバーフロー](../Topic/basic_streambuf::overflow.md)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|  
|[pbackfail](../Topic/basic_streambuf::pbackfail.md)|要素を入力ストリームに戻そうと試み、その要素を現在の要素に \(ネクスト ポインターによって指されるように\) するプロテクト仮想メンバー関数。|  
|[pbase](../Topic/basic_streambuf::pbase.md)|出力バッファーの先頭を指すポインターを返すプロテクト関数。|  
|[pbump](../Topic/basic_streambuf::pbump.md)|`count` を出力バッファーのネクスト ポインターに追加するプロテクト関数。|  
|[pptr](../Topic/basic_streambuf::pptr.md)|出力バッファーの次の要素を指すポインターを返すプロテクト関数。|  
|[pubimbue](../Topic/basic_streambuf::pubimbue.md)|`basic_streambuf` オブジェクトのロケールを設定します。|  
|[pubseekoff](../Topic/basic_streambuf::pubseekoff.md)|派生クラスでオーバーライドされるプロテクト仮想関数 [seekoff](../Topic/basic_streambuf::seekoff.md) を呼び出します。|  
|[pubseekpos](../Topic/basic_streambuf::pubseekpos.md)|派生クラスでオーバーライドされ、現在のポインターの位置をリセットするプロテクト仮想関数 [seekpos](../Topic/basic_streambuf::seekpos.md) を呼び出します。|  
|[pubsetbuf](../Topic/basic_streambuf::pubsetbuf.md)|派生クラスでオーバーライドされるプロテクト仮想関数 [setbuf](../Topic/basic_streambuf::setbuf.md) を呼び出します。|  
|[pubsync](../Topic/basic_streambuf::pubsync.md)|派生クラスでオーバーライドされ、このバッファーに関連付けられた外部ストリームを更新するプロテクト仮想関数 [sync](../Topic/basic_streambuf::sync.md) を呼び出します。|  
|[sbumpc](../Topic/basic_streambuf::sbumpc.md)|ストリーム ポインターを移動させながら、現在の要素を読み取って返します。|  
|[seekoff](../Topic/basic_streambuf::seekoff.md)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|  
|[seekpos](../Topic/basic_streambuf::seekpos.md)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|  
|[setbuf](../Topic/basic_streambuf::setbuf.md)|プロテクト仮想メンバー関数が、各派生ストリーム バッファーに固有の操作を実行します。|  
|[setg](../Topic/basic_streambuf::setg.md)|開始ポインターの `_Gbeg`、ネクスト ポインターの `_Gnext`、およびエンド ポインターの `_Gend` を入力バッファー用に格納するプロテクト関数。|  
|[setp](../Topic/basic_streambuf::setp.md)|開始ポインターの `_Pbeg` およびエンド ポインターの `_Pend` を出力バッファー用に格納するプロテクト関数。|  
|[sgetc](../Topic/basic_streambuf::sgetc.md)|ストリーム内の位置を変更せずに、現在の要素を返します。|  
|[sgetn](../Topic/basic_streambuf::sgetn.md)|読み取られる要素数を返します。|  
|[showmanyc](../Topic/basic_streambuf::showmanyc.md)|入力ストリームから抽出できる文字数のカウントを返し、プログラムが無期限の待機状態にならないようにするプロテクト仮想メンバー関数。|  
|[snextc](../Topic/basic_streambuf::snextc.md)|現在の要素を読み取り、次の要素を返します。|  
|[sputbackc](../Topic/basic_streambuf::sputbackc.md)|`char_type` をストリームに渡します。|  
|[sputc](../Topic/basic_streambuf::sputc.md)|ストリームに単一の文字を渡します。|  
|[sputn](../Topic/basic_streambuf::sputn.md)|ストリームに文字列を渡します。|  
|[stossc](../Topic/basic_streambuf::stossc.md)|ストリーム内の現在の要素の直後に移動します。|  
|[sungetc](../Topic/basic_streambuf::sungetc.md)|ストリームから単一の文字を取得します。|  
|[swap](../Topic/basic_streambuf::swap.md)|このオブジェクトの値を、指定した `basic_streambuf` オブジェクト パラメーターの値と交換します。|  
|[sync](../Topic/basic_streambuf::sync.md)|制御されているストリームと関連付けられている外部ストリームとの同期を試みるプロテクト仮想関数。|  
|[uflow](../Topic/basic_streambuf::uflow.md)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|  
|[underflow](../Topic/basic_streambuf::underflow.md)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|  
|[xsgetn](../Topic/basic_streambuf::xsgetn.md)|入力ストリームから要素を抽出するプロテクト仮想関数。|  
|[xsputn](../Topic/basic_streambuf::xsputn.md)|出力ストリームに要素を挿入するプロテクト仮想関数。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../Topic/basic_streambuf::operator=.md)|別の `basic_streambuf` オブジェクトの値をこのオブジェクトに割り当てます。|  
  
## 必要条件  
 **ヘッダー:**\<streambuf\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)