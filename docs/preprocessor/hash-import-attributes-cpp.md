---
title: "#import の属性 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#import ディレクティブ, 属性"
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #import の属性 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\#import ディレクティブと共に使用される属性のリンクを示します。  
  
 **Microsoft 固有の仕様 →**  
  
 次の属性は、\#import ディレクティブで使用できます。  
  
|属性|説明|  
|--------|--------|  
|[auto\_rename](../preprocessor/auto-rename.md)|潜在的な名前の競合を解決するため、変数名に 2 つのアンダースコア \(\_\_\) を追加して C\+\+ の予約語の名前を変更します。|  
|[auto\_search](../preprocessor/auto-search.md)|タイプ ライブラリが \#import を使用して参照され、自身が別のタイプ ライブラリを参照している場合、コンパイラが他のタイプ ライブラリに対して暗黙の \#import を実行できることを指定します。|  
|[embedded\_idl](../preprocessor/embedded-idl.md)|属性が生成されたコードを保持して、タイプ ライブラリを .tlh ファイルに書き込むことを指定します。|  
|[exclude](../preprocessor/exclude-hash-import.md)|生成されるタイプ ライブラリのヘッダー ファイルから項目を除外します。|  
|[high\_method\_prefix](../preprocessor/high-method-prefix.md)|高レベルのプロパティおよびメソッドの名前付けで使用されるプレフィックスを指定します。|  
|[high\_property\_prefixes](../Topic/high_property_prefixes.md)|3 つのプロパティ メソッドの代替プレフィックスを指定します。|  
|[implementation\_only](../preprocessor/implementation-only.md)|.tlh ヘッダー ファイル \(プライマリ ヘッダー ファイル\) の生成を抑制します。|  
|[include\(\)](../preprocessor/include-parens.md)|自動除外を無効にします。|  
|[inject\_statement](../preprocessor/inject-statement.md)|タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。|  
|[named\_guids](../preprocessor/named-guids.md)|**LIBID\_MyLib**、**CLSID\_MyCoClass**、**IID\_MyInterface**、および **DIID\_MyDispInterface** 形式に対して、旧スタイルの GUID 変数を定義し、初期化するようコンパイラに指示します。|  
|[no\_auto\_exclude](../preprocessor/no-auto-exclude.md)|自動除外を無効にします。|  
|[no\_dual\_interfaces](../preprocessor/no-dual-interfaces.md)|コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。|  
|[no\_implementation](../preprocessor/no-implementation.md)|ラッパー メンバー関数の実装を含む .tli ヘッダーの生成を抑制します。|  
|[no\_namespace](../Topic/no_namespace.md)|名前空間名がコンパイラによって生成されないことを指定します。|  
|[no\_registry](../Topic/no_registry.md)|タイプ ライブラリのレジストリを検索しないようコンパイラに指示します。|  
|[no\_search\_namespace](../preprocessor/no-search-namespace.md)|[no\_namespace](../Topic/no_namespace.md) 属性と同じ機能ですが、[auto\_search](../preprocessor/auto-search.md) 属性で \#import ディレクティブを使用するタイプ ライブラリに対して使用されます。|  
|[no\_smart\_pointers](../preprocessor/no-smart-pointers.md)|タイプ ライブラリのすべてのインターフェイスに対して、スマート ポインターの作成を抑制します。|  
|[raw\_dispinterfaces](../Topic/raw_dispinterfaces.md)|**IDispatch::Invoke** を呼び出して `HRESULT` エラー コードを返すディスパッチインターフェイス メソッドおよびプロパティに対して、低レベルのラッパー関数を生成するようコンパイラに指示します。|  
|[raw\_interfaces\_only](../Topic/raw_interfaces_only.md)|エラー処理ラッパー関数およびそのラッパー関数を使用する [プロパティ](../cpp/property-cpp.md) 宣言の生成を抑制します。|  
|[raw\_method\_prefix](../preprocessor/raw-method-prefix.md)|名前の衝突を避けるために異なるプレフィックスを指定します。|  
|[raw\_native\_types](../Topic/raw_native_types.md)|高レベルのラッパー関数の COM サポート クラスの使用を無効にし、代わりに低レベルのデータ型の使用を強制します。|  
|[raw\_property\_prefixes](../preprocessor/raw-property-prefixes.md)|3 つのプロパティ メソッドの代替プレフィックスを指定します。|  
|[名前の変更](../preprocessor/rename-hash-import.md)|名前の衝突の問題を回避します。|  
|[rename\_namespace](../preprocessor/rename-namespace.md)|タイプ ライブラリの内容を含む名前空間の名前を変更します。|  
|[rename\_search\_namespace](../preprocessor/rename-search-namespace.md)|[rename\_namespace](../preprocessor/rename-namespace.md) 属性と同じ機能ですが、[auto\_search](../preprocessor/auto-search.md) 属性で \#import ディレクティブを使用するタイプ ライブラリに対して使用されます。|  
|[tlbid](../preprocessor/tlbid.md)|プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。|  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)