---
title: "Typedef, Enum, Union, and Struct Attributes | Microsoft Docs"
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
  - "union attributes"
  - "attributes [C++], reference topics"
  - "struct attributes"
  - "typedef attributes"
  - "enum attributes"
ms.assetid: f8a4fe94-dc02-4aed-bc31-3e500d42f4c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Typedef, Enum, Union, and Struct Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の属性は [型定義](http://msdn.microsoft.com/ja-jp/cc96cf26-ba93-4179-951e-695d1f5fdcf1)[構造体](../cpp/struct-cpp.md) と [列挙](../cpp/enumerations-cpp.md) C\+\+ キーワードに適用されます。  
  
### typedef  
  
|属性|Description|  
|--------|-----------------|  
|[case](../windows/case-cpp.md)|**共用体**  で [switch\_type](../windows/switch-type.md) の属性を使用します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[export](../windows/export.md)|データ構造を .idl ファイル内に配置します。|  
|[first\_is](../windows/first-is.md)|送信される最初の要素のインデックスを指定します。|  
|[helpcontext](../windows/helpcontext.md)|ヘルプ ファイルに要素に関するユーザーの情報を表示できるようにするためのコンテキスト ID を指定します。|  
|[helpfile](../Topic/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用先の要素の記述に使用される文字列を指定します。|  
|[library\_block](../windows/library-block.md)|.idl ファイルのライブラリ ブロック内の構造を配置します。|  
|[ptr](../windows/ptr.md)|完全なポインターとしてポインターを指定します。|  
|[public](../windows/public-cpp-attributes.md)|.idl ファイル内で参照されていない場合でも型定義をタイプ ライブラリに入ることを確認します。|  
|[ref](../windows/ref-cpp.md)|参照のポインターを指定します。|  
|[switch\_is](../windows/switch-is.md)|discriminant クラスを選択する共用体として機能する式または識別子を指定します。|  
|[switch\_type](../windows/switch-type.md)|discriminant 共用体として使用されている変数の型を指定します。|  
|[一意](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[wire\_marshal](../windows/wire-marshal.md)|アプリケーション固有のデータ型の代わりに転送に使用されるデータ型を指定します。|  
  
### enum  
  
|属性|Description|  
|--------|-----------------|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[export](../windows/export.md)|データ構造を .idl ファイル内に配置します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[v1\_enum](../windows/v1-enum.md)|指定した列挙体が16 ビットの既定値ではなく 32 ビット エンティティとして送信されることを指定します。|  
  
### union  
  
|属性|Description|  
|--------|-----------------|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[export](../windows/export.md)|データ構造を .idl ファイル内に配置します。|  
|[first\_is](../windows/first-is.md)|送信される最初の要素のインデックスを指定します。|  
|[last\_is](../windows/last-is.md)|送信する最後の要素のインデックスを指定します。|  
|[length\_is](../windows/length-is.md)|送信される配列要素の数を指定します。|  
|[max\_is](../windows/max-is.md)|有効な配列インデックスの最大値を指定します。|  
|[size\_is](../Topic/size_is.md)|付きサイズポインター サイズ設定されたポインター用に設定されたポインター サイズおよび単一または多次元配列に割り当てられているメモリのサイズを指定します。|  
|[一意](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
  
### Nonencapsulated の共用体  
  
|属性|Description|  
|--------|-----------------|  
|[ms\_union](../windows/ms-union.md)|nonencapsulated 共用体のネットワーク データ表現の配置を制御します。|  
|[no\_injected\_text](../windows/no-injected-text.md)|コンパイラで属性を使用した結果としてコードを挿入できません。|  
  
### struct  
  
|属性|Description|  
|--------|-----------------|  
|[aggregatable](../Topic/aggregatable.md)|クラスが集約をサポートすることを示します。|  
|[集約](../windows/aggregates.md)|コントロールが対象のクラスを集約することを示します。|  
|[appobject](../Topic/appobject.md)|コクラスを完全な .exe アプリケーションに関連付けられている特定しコクラスの関数とプロパティがこのタイプ ライブラリでグローバルに使用できるオブジェクトとしてアプリケーションを示します。|  
|[コクラス](../windows/coclass.md)|ActiveX コントロールを作成します。|  
|[com\_interface\_entry](../Topic/com_interface_entry%20\(C++\).md)|COM インターフェイス マップにエントリを追加します。|  
|[コントロール](../windows/control.md)|ユーザー定義型はコントロールであることを指定します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[db\_column](../windows/db-column.md)|行セットに指定した列をバインドします。|  
|[db\_command](../windows/db-command.md)|OLE DB のコマンドを作成します。|  
|[db\_param](../windows/db-param.md)|指定したメンバー変数を入力または出力パラメーターに関連付け変数を区切ります。|  
|[db\_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db\_table](../windows/db-table.md)|OLE DB テーブルを開きます。|  
|[default](../windows/default-cpp.md)|コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。|  
|[defaultvtable](../windows/defaultvtable.md)|コントロールの既定の vtable インターフェイスとインターフェイスを定義します。|  
|[event\_receiver](../windows/event-receiver.md)|イベント レシーバーを作成します。|  
|[ソース](../windows/event-source.md)|イベント ソースを作成します。|  
|[export](../windows/export.md)|データ構造を .idl ファイル内に配置します。|  
|[first\_is](../windows/first-is.md)|送信される最初の要素のインデックスを指定します。|  
|[hidden](../Topic/hidden.md)|項目が存在してもユーザー指向ブラウザーに表示されないことを示します。|  
|[implements\_category](../Topic/implements_category.md)|によってクラスのコンポーネント カテゴリを実行します。|  
|[last\_is](../windows/last-is.md)|送信する最後の要素のインデックスを指定します。|  
|[length\_is](../windows/length-is.md)|送信される配列要素の数を指定します。|  
|[max\_is](../windows/max-is.md)|有効な配列インデックスの最大値を指定します。|  
|[requires\_category](../windows/requires-category.md)|ターゲット クラスの必須コンポーネントのカテゴリを指定します。|  
|[size\_is](../Topic/size_is.md)|付きサイズポインター サイズ設定されたポインター用に設定されたポインター サイズおよび単一または多次元配列に割り当てられているメモリのサイズを指定します。|  
|[source](../Topic/source%20\(C++\).md)|クラスではコネクション ポイントに COM オブジェクトのソース インターフェイスを指定します。  プロパティまたはメソッドでメンバーがイベントのソースであるかバリアント オブジェクトを返すことを示します。|  
|[スレッド](../windows/threading-cpp.md)|COM オブジェクトに対してスレッド モデルを指定します。|  
|[一意](../windows/unique-cpp.md)|一意のポインターを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|クラスまたはインターフェイスの一意の ID を指定します。|  
|[version](../windows/version-cpp.md)|クラスの複数のバージョンでの特定のバージョンを指定します。|  
|[vi\_progid](../windows/vi-progid.md)|ProgID のバージョンに依存しない形式を指定します。|  
  
## 参照  
 [Attributes by Usage](../windows/attributes-by-usage.md)