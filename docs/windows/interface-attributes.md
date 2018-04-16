---
title: "インターフェイス属性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ff84939b3211633e199066e1a38da2e91efb1c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="interface-attributes"></a>インターフェイス属性
次の属性に適用される、[インターフェイス (または _ _interface)](../cpp/interface.md) C++ のキーワードです。  
  
|属性|説明|  
|---------------|-----------------|  
|[async_uuid](../windows/async-uuid.md)|COM インターフェイスの同期および非同期の両方のバージョンを定義する MIDL コンパイラに指示する UUID を指定します。|  
|[カスタム](../windows/custom-cpp.md)|独自の属性を定義できます。|  
|[dispinterface](../windows/dispinterface.md)|ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。|  
|[dual](../windows/dual.md)|.Idl ファイル内のインターフェイスをデュアル インターフェイスとして配置します。|  
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造が発生します。|  
|[helpcontext](../windows/helpcontext.md)|コンテキスト ID をユーザーに関する情報を表示、ヘルプ ファイル内のこの要素を指定します。|  
|[helpfile](../windows/helpfile.md)|タイプ ライブラリのヘルプ ファイルの名前を設定します。|  
|[helpstring](../windows/helpstring.md)|適用すると、要素の記述に使用される文字の文字列を指定します。|  
|[helpstringcontext](../windows/helpstringcontext.md)|.Hlp または .chm ファイルには、ヘルプ トピックの ID を指定します。|  
|[helpstringdll](../windows/helpstringdll.md)|ドキュメントの文字列の検索 (ローカリゼーション) の実行に使用する DLL の名前を指定します。|  
|[hidden](../windows/hidden.md)|項目が存在しますが、ユーザー指向ブラウザーで表示する必要がありますされませんを示します。|  
|[library_block](../windows/library-block.md)|.Idl ファイルのライブラリ ブロックの内部構造を配置します。|  
|[地元の](../windows/local-cpp.md)|インターフェイスのヘッダーで使用する場合は、ヘッダー ジェネレーターとして MIDL コンパイラを使用できます。 個々 の関数で使用する場合は、対象のスタブが生成されないローカル プロシージャを指定します。|  
|[nonextensible](../windows/nonextensible.md)|指定する、`IDispatch`実装にはプロパティのみが含まれます、メソッドのインターフェイスの説明で一覧表示および実行時にメンバーを追加して拡張することはできません。 この属性でのみ有効です、[デュアル](../windows/dual.md)インターフェイスです。|  
|[odl](../windows/odl.md)|オブジェクト記述言語 (ODL) インターフェイスとしてインターフェイスを識別します。|  
|[object](../windows/object-cpp.md)|カスタムのインターフェイスを識別します。|  
|[oleautomation](../windows/oleautomation.md)|インターフェイスに Automation では互換性があることを示します。|  
|[pointer_default](../windows/pointer-default.md)|パラメーター リストに表示される最上位のポインターを除くすべてのポインターの既定のポインターの属性を指定します。|  
|[ptr](../windows/ptr.md)|すべてのポインターとしてのポインターを指定します。|  
|[restricted](../windows/restricted.md)|ライブラリのどのメンバーを任意に呼び出すことはできませんを指定します。|  
|[uuid](../windows/uuid-cpp-attributes.md)|ライブラリの一意の ID を提供します。|  
  
 インターフェイスを定義するため、これらの規則に従う必要があります。  
  
-   既定の呼び出し規約は[_ _stdcall](../cpp/stdcall.md)です。  
  
-   いずれかを指定しない場合、GUID が指定されます。  
  
-   オーバー ロードされたメソッドは許可されません。  
  
 指定しない場合、 [uuid](../windows/uuid-cpp-attributes.md)属性し、同じインターフェイスの名前を使用して、別の属性をプロジェクトでは、同じ GUID が生成されます。  
  
## <a name="see-also"></a>参照  
 [使用法別の属性](../windows/attributes-by-usage.md)