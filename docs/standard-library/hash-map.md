---
title: "&lt;hash_map&gt; | Microsoft Docs"
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
  - "std.<hash_map>"
  - "<hash_map>"
  - "std::<hash_map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_map ヘッダー"
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_map&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  このヘッダーは廃止され、互換性のために残されています。 代わりに、[\<unordered\_map\>](../standard-library/unordered-map.md) を使用してください。  
  
 コンテナーのテンプレート クラス hash\_map と hash\_multimap、およびそのサポート用テンプレートを定義します。  
  
 Visual C\+\+ .NET 2003 では、[\<hash\_map\>](#vclrfhash_map_header_file) ヘッダー ファイルと [\<hash\_set\>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間から stdext 名前空間に移動されました。 詳細については、「[stdext 名前空間](../Topic/stdext%20Namespace.md)」を参照してください。  
  
## 構文  
  
```  
  
#include <hash_map>  
  
```  
  
### 演算子  
  
|hash\_map バージョン|hash\_multimap バージョン|説明|  
|---------------------|--------------------------|--------|  
|[operator\!\= \(hash\_map\)](../Topic/operator!=%20\(hash_map\).md)|[operator\!\= \(hash\_multimap\)](../Topic/operator!=%20\(hash_multimap\).md)|演算子の左側の hash\_map または hash\_multimap オブジェクトが右側の hash\_map または hash\_multimap オブジェクトと等しくないかどうかをテストします。|  
|[operator\=\= \(hash\_map\)](http://msdn.microsoft.com/ja-jp/f933cb1c-934d-43f5-aa9e-0b325eb95b85)|[operator\=\= \(hash\_multimap\)](http://msdn.microsoft.com/ja-jp/3fa378b1-0250-4e3f-a130-dc14103fc5e9)|演算子の左側の hash\_map または hash\_multimap オブジェクトが右側の hash\_map または hash\_multimap オブジェクトと等しいかどうかをテストします。|  
  
### 特殊テンプレート関数  
  
|hash\_map バージョン|hash\_multimap バージョン|説明|  
|---------------------|--------------------------|--------|  
|[swap \(hash\_map\)](../Topic/hash_map::swap.md)|[swap \(hash\_multimap\)](../Topic/hash_multimap::swap.md)|2 つの hash\_map または hash\_multimap の要素を交換します。|  
  
### クラス  
  
|||  
|-|-|  
|[hash\_compare クラス](../standard-library/hash-compare-class.md)|任意のハッシュ連想コンテナー \(hash\_map、hash\_multimap、hash\_set、または hash\_multiset\) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。|  
|[value\_compare クラス](../Topic/value_compare%20Class.md)|要素のキーの値を比較し、要素の hash\_map 内の相対順序を決定して、hash\_map の要素を比較できる関数オブジェクトを提供します。|  
|[hash\_map クラス](../standard-library/hash-map-class.md)|一意の並べ替えキーとそれに関連付けられている値のペアを要素として持つコレクションのデータを格納したり、迅速に取得したりするために使用されます。|  
|[hash\_multimap クラス](../standard-library/hash-multimap-class.md)|必ずしも一意ではない並べ替えキーとそれに関連付けられている値のペアを要素として持つコレクションのデータを格納したり、迅速に取得したりするために使用されます。|  
  
## 必要条件  
 **ヘッダー:** \<hash\_map\>  
  
 **名前空間:** stdext  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)