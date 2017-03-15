---
title: "Interface Attributes | Microsoft Docs"
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
  - "interface attributes"
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Interface Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の属性は [インターフェイスが \(または\)](../Topic/__interface.md) C\+\+ のキーワードが適用されます。  
  
|属性|Description|  
|--------|-----------------|  
|[async\_uuid](../Topic/async_uuid.md)|MIDL コンパイラの COM インターフェイスを同期的および非同期バージョンを定義するように指示する UUID を指定します。|  
|[custom](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[dispinterface](../windows/dispinterface.md)|ディスパッチ インターフェイスとして .idl ファイルを配置します。|  
|[dual](../Topic/dual.md)|デュアル インターフェイスとして .idl ファイルを配置します。|  
|[export](../windows/export.md)|データ構造を .idl ファイル内に配置します。|  
|[helpcontext](../windows/helpcontext.md)|ヘルプ ファイルに要素に関するユーザーの情報を表示できるようにするためのコンテキスト ID を指定します。|  
|[helpfile](../Topic/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用先の要素の記述に使用される文字列を指定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.hlp または .chm ファイルでヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|DLL の名前を文書内の文字列の参照 \(ローカリゼーション\) を実行するように指定します。|  
|[hidden](../Topic/hidden.md)|項目が存在してもユーザー指向ブラウザーに表示されないことを示します。|  
|[library\_block](../windows/library-block.md)|.idl ファイルのライブラリ ブロック内の構造を配置します。|  
|[local](../windows/local-cpp.md)|インターフェイスのヘッダーで使用するとヘッダーのジェネレーターとして MIDL コンパイラを使用できます。  個々の関数ではスタブが生成されないローカル プロシージャを指定します。|  
|[nonextensible](../Topic/nonextensible.md)|`IDispatch` のインターフェイスを実装の詳細に示すプロパティとメソッドのみを含め実行時のメンバーによって拡張することができないことを指定します。  この属性は [double](../Topic/dual.md) のインターフェイスでのみ有効です。|  
|[odl](../windows/odl.md)|オブジェクト記述言語のインターフェイスとしてインターフェイスを \(ODL\) 識別します。|  
|[object](../Topic/object%20\(C++\).md)|カスタム インターフェイスを識別します。|  
|[oleautomation](../windows/oleautomation.md)|インターフェイスはオートメーションとの互換性があることを示します。|  
|[pointer\_default](../windows/pointer-default.md)|パラメーター リストに表示される最上位のポインターを除くすべての既定のポインターの属性を指定します。|  
|[ptr](../windows/ptr.md)|完全なポインターとしてポインターを指定します。|  
|[restricted](../windows/restricted.md)|ライブラリのメンバーを任意に呼び出すことができないかを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|ライブラリに一意の ID を提供します。|  
  
 インターフェイスを定義するには次の規則に従う必要があります :  
  
-   既定の呼び出し規約は [\_\_stdcall](../cpp/stdcall.md) です。  
  
-   GUID はに 1 を指定して指定されます。  
  
-   オーバーロードされたメソッドは使用できません。  
  
 [uuid](../windows/uuid-cpp-attributes.md) の属性を指定しないと別の属性に同じインターフェイス名を使用することはプロジェクトと同じ GUID が生成されます。  
  
## 参照  
 [Attributes by Usage](../windows/attributes-by-usage.md)