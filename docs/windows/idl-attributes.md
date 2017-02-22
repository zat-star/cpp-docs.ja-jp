---
title: "IDL Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], reference topics"
  - "IDL attributes"
  - ".idl files, attributes"
  - "IDL files, attributes"
  - ".idl files"
ms.assetid: 04c596f4-c97b-4952-8053-316678b1d0b6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDL Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

従来.idl ファイルを維持する必要があることを意味しています :  
  
-   変更できるように.idl ファイルの構造と構文を使い慣れている。  
  
-   .idl ファイルにある要素を変更するウィザードを使用します。  
  
 ここではVisual C\+\+ の IDL 属性を使用してソース・コード ファイルの .idl ファイル内でを変更できます。  多くの場合Visual C\+\+ の IDL 属性に MIDL の属性と同じ名前になります。  Visual C\+\+ の IDL 属性名と MIDL の属性は同じである場合同じ名の MIDL の属性を含む .idl ファイルのソース・コード ファイルにはVisual C\+\+ 属性を配置できるようになることを意味します。  ただしVisual C\+\+ の IDL 属性は属性のすべての機能を提供しないものもあります。  
  
 [COM 属性](../Topic/COM%20Attributes.md) に使用しない場合IDL 属性はインターフェイスを定義することもできます。  ソース・コードをコンパイルするときに作成された .idl ファイルを定義するには属性を使用します。  IDL 属性はATL プロジェクトで COM 属性を使用すると **コクラス**  などコードをプロジェクトに挿入します。  
  
 [idl\_quote](../windows/idl-quote.md) はVisual C\+\+ の現在のバージョンでサポートされていない MIDL の構造を使用できることに注意してください。  [importlib](../windows/importlib.md) と [includelib](../windows/includelib-cpp.md) のヘルプなどこれとそのほかの属性現在の Visual C\+\+ である .idl ファイルを使用するプロジェクト。  
  
|属性|Description|  
|--------|-----------------|  
|[aggregatable](../Topic/aggregatable.md)|コントロールを別のコントロールによって集約できることを示します。|  
|[appobject](../Topic/appobject.md)|コクラスを完全な EXE のアプリケーションに関連付けられている特定しコクラスの関数とプロパティがこのタイプ ライブラリでグローバルに使用できるオブジェクトとしてアプリケーションを示します。|  
|[async\_uuid](../Topic/async_uuid.md)|MIDL コンパイラの COM インターフェイスを同期的および非同期バージョンを定義するように指示する UUID を指定します。|  
|[bindable](../windows/bindable.md)|プロパティがデータ連結をサポートすることを示します。|  
|[call\_as](../windows/call-as.md)|リモート関数にマップするリモート関数を有効にします。|  
|[case](../windows/case-cpp.md)|共用体で [switch\_type](../windows/switch-type.md) の属性を使用します。|  
|[コクラス](../windows/coclass.md)|コクラスとして .idl ファイルの場所のクラス定義。|  
|[コントロール](../windows/control.md)|ユーザー定義型はコントロールであることを指定します。|  
|[cpp\_quote](../Topic/cpp_quote.md)|生成されるヘッダー ファイルに引用符なしで指定された文字列を生成します。|  
|[defaultbind](../windows/defaultbind.md)|最適なオブジェクトを表すを一つの連結できるプロパティを示します。|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic コードの最適化に使用されます。|  
|[defaultvalue](../Topic/defaultvalue.md)|指定された省略可能なパラメーターの既定値を指定できます。|  
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|  
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとインターフェイスを定義します。|  
|[dispinterface](../windows/dispinterface.md)|ディスパッチ インターフェイスとして .idl ファイルを配置します。|  
|[displaybind](../windows/displaybind.md)|バインドできるようにユーザーに表示するプロパティを示します。|  
|[dual](../Topic/dual.md)|デュアル インターフェイスとして .idl ファイルを配置します。|  
|[エントリ](../windows/entry.md)|DLL のエントリ ポイントを指定してモジュール内のエクスポート関数または定数を指定します。|  
|[first\_is](../windows/first-is.md)|送信される最初の要素のインデックスを指定します。|  
|[helpcontext](../windows/helpcontext.md)|ヘルプ ファイルに要素に関するユーザーの情報を表示できるようにするためのコンテキスト ID を指定します。|  
|[helpfile](../Topic/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.hlp または .chm ファイルでヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|DLL の名前を文書内の文字列の参照 \(ローカリゼーション\) を実行するように指定します。|  
|[helpstring](../windows/helpstring.md)|適用先の要素の記述に使用される文字列を指定します。|  
|[hidden](../Topic/hidden.md)|項目が存在してもユーザー指向ブラウザーに表示されないことを示します。|  
|[idl\_module](../windows/idl-module.md)|DLL のエントリ ポイントを指定します。|  
|[idl\_quote](../windows/idl-quote.md)|Visual C\+\+ の現在のバージョンでサポートされていない属性を使用するまたは IDL の構造体。|  
|[id](../windows/id.md)|メンバー関数 \(インターフェイスのプロパティまたはメソッドまたはディスパッチ インターフェイス\) に DISPID を指定します。|  
|[iid\_is](../windows/iid-is.md)|指す COM インターフェイスの IID をインターフェイス ポインターを指定します。|  
|[immediatebind](../windows/immediatebind.md)|データベースにデータ バインド オブジェクトのプロパティに対するすべての変更がすぐに通知されることを示します。|  
|[importlib](../windows/importlib.md)|作成されたタイプ ライブラリに別のタイプ ライブラリで使用できるようにコンパイル済みの型を作成します。|  
|[import](../windows/import.md)|主要な .idl ファイルから参照する定義を含む別の .idl.odlまたはヘッダー ファイルを指定します。|  
|[必要](../windows/include-cpp.md)|生成された .idl ファイルに含める一つ以上のヘッダー ファイルを指定します。|  
|[includelib](../windows/includelib-cpp.md)|生成された .idl ファイルに含める .idl ファイルまたは .h ファイルを指定します。|  
|[&#91;in&#93;](../Topic/in%20\(C++\).md)|パラメーターが呼び出し元のプロシージャから呼び出し先のプロシージャに渡す必要があることを示します。|  
|[last\_is](../windows/last-is.md)|送信する最後の要素のインデックスを指定します。|  
|[lcid](../windows/lcid.md)|関数にロケール ID を渡すことができます。|  
|[length\_is](../windows/length-is.md)|送信される配列要素の数を指定します。|  
|[Licensed](../windows/licensed.md)|これを適用するコクラスはライセンスされたコントロール **IClassFactory2** を使用してをインスタンス化する必要があります。|  
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用するとヘッダーのジェネレーターとして MIDL コンパイラを使用できます。  個々の関数ではスタブが生成されないローカル プロシージャを指定します。|  
|[max\_is](../windows/max-is.md)|有効な配列インデックスの最大値を指定します。|  
|[module](../windows/module-cpp.md)|.idl ファイルのライブラリ ブロックを定義します。|  
|[ms\_union](../windows/ms-union.md)|nonencapsulated 共用体のネットワーク データ表現の配置を制御します。|  
|[no\_injected\_text](../windows/no-injected-text.md)|コンパイラで属性を使用した結果としてコードを挿入できません。|  
|[nonbrowsable](../Topic/nonbrowsable.md)|インターフェイス メンバーをプロパティ ブラウザーに表示されないことを示します。|  
|[作成](../windows/noncreatable.md)|単独ではインスタンス化できないオブジェクトを定義します。|  
|[nonextensible](../Topic/nonextensible.md)|`IDispatch` のインターフェイスを実装の詳細に示すプロパティとメソッドのみを含め実行時のメンバーによって拡張することができないことを指定します。|  
|[object](../Topic/object%20\(C++\).md)|カスタム インターフェイスを識別します ; カスタム属性と同じ意味です。|  
|[odl](../windows/odl.md)|オブジェクト記述言語のインターフェイスとしてインターフェイスを \(ODL\) 識別します。|  
|[oleautomation](../windows/oleautomation.md)|インターフェイスはオートメーションとの互換性があることを示します。|  
|[省略可能](../windows/optional-cpp.md)|メンバー関数に省略可能なパラメーターを指定します。|  
|[&#91;out&#93;](../Topic/out%20\(C++\).md)|呼び出し先のプロシージャから呼び出し元のプロシージャから返されたポインターのパラメーターを識別します \(サーバーからクライアントに\)。|  
|[pointer\_default](../windows/pointer-default.md)|パラメーター リストに表示される最上位のポインターを除くすべての既定のポインターの属性を指定します。|  
|[プラグマ](../windows/pragma.md)|生成された .idl ファイルに引用符なしで指定された文字列を生成します。|  
|[ProgID](../Topic/progid.md)|COM オブジェクトに ProgID を指定します。|  
|[propget](../windows/propget.md)|プロパティ アクセサー \(取得関数\) を指定します。|  
|[propputref](../windows/propputref.md)|値ではなく参照を使用するプロパティ設定の関数を指定します。|  
|[propput](../windows/propput.md)|プロパティ設定の関数を指定します。|  
|[ptr](../windows/ptr.md)|完全なポインターとしてポインターを指定します。|  
|[public](../windows/public-cpp-attributes.md)|.idl ファイル内で参照されていない場合でも型定義をタイプ ライブラリに入ることを確認します。|  
|[範囲](../Topic/range%20\(C++\).md)|値が実行時に設定されたフィールドまたは引数に許可される値の範囲を指定します。|  
|[readonly](../windows/readonly-cpp.md)|変数に代入を禁止します。|  
|[ref](../windows/ref-cpp.md)|参照のポインターを指定します。|  
|[requestedit](../windows/requestedit.md)|プロパティが **OnRequestEdit** 通知をサポートすることを示します。|  
|[restricted](../windows/restricted.md)|モジュールインターフェイスまたはディスパッチ インターフェイス ライブラリまたはメンバーを任意に呼び出すことができないことを指定します。|  
|[retval](../windows/retval.md)|メンバーの戻り値を受け取るパラメーターを指定します。|  
|[size\_is](../Topic/size_is.md)|付きサイズポインター サイズ設定されたポインター用に設定されたポインター サイズおよび単一または多次元配列に割り当てられているメモリのサイズを指定します。|  
|[source](../Topic/source%20\(C++\).md)|クラスプロパティまたはメソッドのメンバーがイベントのソースであることを示します。|  
|[string](../windows/string-cpp.md)|配列の 1 番 `char``wchar_t` **バイト** または同等の配列またはポインターが文字列のように扱うことを示します。|  
|[switch\_is](../windows/switch-is.md)|discriminant クラスを選択する共用体として機能する式または識別子を指定します。|  
|[switch\_type](../windows/switch-type.md)|discriminant 共用体として使用されている変数の型を指定します。|  
|[transmit\_as](../windows/transmit-as.md)|コンパイラにクライアント アプリケーションとサーバー アプリケーションが処理する転送された型と指定の型に関連付けるように指示します。|  
|[uidefault](../Topic/uidefault.md)|型情報のメンバーがユーザー インターフェイスの既定のメンバーであることを示します。|  
|[一意](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[usesgetlasterror](../windows/usesgetlasterror.md)|この関数を呼び出すとエラー コードを取得するために呼び出し元は`GetLastError` を呼び出すことができるエラーがある場合は呼び出し元が表示されます。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[v1\_enum](../windows/v1-enum.md)|指定した列挙体が16 ビットの既定値ではなく 32 ビット エンティティとして送信されることを指定します。|  
|[vararg](../windows/vararg.md)|関数が引数の数が可変であることを指定します。|  
|[vi\_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|  
|[wire\_marshal](../windows/wire-marshal.md)|アプリケーション固有のデータ型の代わりに転送に使用されるデータ型を指定します。|  
  
## 参照  
 [Attributes by Group](../windows/attributes-by-group.md)   
 [Attribute Limitations](http://msdn.microsoft.com/ja-jp/6e6c4329-f667-4869-b991-cbe9cb7a8f61)