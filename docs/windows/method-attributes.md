---
title: "Method Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "method attributes"
  - "attributes [C++], reference topics"
ms.assetid: b2313352-480d-488b-8c35-6242ffd3a549
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Method Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の属性はコクラス クラスまたはインターフェイスのメソッドに適用されます。  
  
|属性|Description|  
|--------|-----------------|  
|[bindable](../windows/bindable.md)|プロパティがデータ連結をサポートすることを示します。|  
|[call\_as](../windows/call-as.md)|リモート関数にマップするリモート関数を有効にします。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db\_column](../windows/db-column.md)|行セットに指定した列をバインドします。|  
|[db\_command](../windows/db-command.md)|OLE DB のコマンドを作成します。|  
|[db\_param](../windows/db-param.md)|指定したメンバー変数を入力または出力パラメーターに関連付け変数を区切ります。|  
|[db\_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db\_table](../windows/db-table.md)|OLE DB テーブルを開きます。|  
|[defaultbind](../windows/defaultbind.md)|最適なオブジェクトを表すを一つの連結できるプロパティを示します。|  
|[defaultcollelem](../windows/defaultcollelem.md)|Visual Basic コードの最適化に使用されます。|  
|[displaybind](../windows/displaybind.md)|バインドできるようにユーザーに表示するプロパティを示します。|  
|[helpcontext](../windows/helpcontext.md)|ヘルプ ファイルに要素に関するユーザーの情報を表示できるようにするためのコンテキスト ID を指定します。|  
|[helpfile](../Topic/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用先の要素の記述に使用される文字列を指定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.hlp または .chm ファイルでヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|DLL の名前を文書内の文字列の参照 \(ローカリゼーション\) を実行するように指定します。|  
|[hidden](../Topic/hidden.md)|項目が存在してもユーザー指向ブラウザーに表示されないことを示します。|  
|[id](../windows/id.md)|メンバー関数 \(インターフェイスのプロパティまたはメソッドまたはディスパッチ インターフェイス\) に DISPID を指定します。|  
|[immediatebind](../windows/immediatebind.md)|データベースにデータ バインド オブジェクトのプロパティに対するすべての変更がすぐに通知されることを示します。|  
|[&#91;in&#93;](../Topic/in%20\(C++\).md)|パラメーターが呼び出し元のプロシージャから呼び出し先のプロシージャに渡す必要があることを示します。|  
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用するとヘッダーのジェネレーターとして MIDL コンパイラを使用できます。  個々の関数ではスタブが生成されないローカル プロシージャを指定します。|  
|[nonbrowsable](../Topic/nonbrowsable.md)|インターフェイス メンバーをプロパティ ブラウザーに表示されないことを示します。|  
|[propget](../windows/propget.md)|アクセサー関数を指定します。|  
|[propput](../windows/propput.md)|プロパティ設定の関数を指定します。|  
|[propputref](../windows/propputref.md)|値ではなく参照を使用するプロパティ設定の関数を指定します。|  
|[ptr](../windows/ptr.md)|完全なポインターとしてポインターを指定します。|  
|[範囲](../Topic/range%20\(C++\).md)|値が実行時に設定されたフィールドまたは引数に許可される値の範囲を指定します。|  
|[requestedit](../windows/requestedit.md)|プロパティが **OnRequestEdit** 通知をサポートすることを示します。|  
|[restricted](../windows/restricted.md)|モジュールインターフェイスまたはディスパッチ インターフェイスのメンバーを任意に呼び出すことができないことを指定します。|  
|[satype](../windows/satype.md)|**SAFEARRAY** 構造体のデータ型を指定します。|  
|[source](../Topic/source%20\(C++\).md)|クラスにコネクション ポイントにコントロールのソース インターフェイスを指定します。  プロパティまたはメソッドで **ソース**  の属性にはメンバーがイベントのソースであるかバリアント オブジェクトを返すことを示します。|  
|[同期](../windows/synchronize.md)|ターゲット メソッドへのアクセスを同期します。|  
|[vararg](../windows/vararg.md)|関数が引数の数が可変であることを指定します。|  
  
## 参照  
 [Attributes by Usage](../windows/attributes-by-usage.md)