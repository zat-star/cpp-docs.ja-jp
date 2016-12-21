---
title: "&lt;hash_set&gt; | Microsoft Docs"
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
  - "<hash_set>"
  - "std.<hash_set>"
  - "std::<hash_set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set ヘッダー"
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;hash_set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  このヘッダーは廃止され、互換性のために残されています。 代わりに、[\<unordered\_set\>](../standard-library/unordered-set.md) を使用してください。  
  
 コンテナー テンプレート クラスの hash\_set と hash\_multiset、およびそのサポート用テンプレートを定義します。  
  
## 構文  
  
```  
  
#include <hash_set>  
  
```  
  
## 解説  
 Visual C\+\+ .NET 2003 では、[\<hash\_map\>](../standard-library/hash-map.md) ヘッダー ファイルと [\<hash\_set\>](#vclrfhash_set_header_file) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext Namespace](../Topic/stdext%20Namespace.md)」を参照してください。  
  
### 演算子  
  
|Hash\_set バージョン|Hash\_multiset バージョン|説明|  
|---------------------|--------------------------|--------|  
|[operator\!\= \(hash\_set\)](../Topic/operator!=%20\(hash_set\).md)|[operator\!\= \(hash\_multiset\)](../Topic/operator!=%20\(hash_multiset\).md)|演算子の左側の hash\_set または hash\_multiset オブジェクトが右側の hash\_set または hash\_multiset オブジェクトと等しくないかどうかをテストします。|  
|[operator\=\= \(hash\_set\)](http://msdn.microsoft.com/ja-jp/791b95bd-f917-4716-aea6-add50badbfac)|[operator\=\= \(hash\_multiset\)](http://msdn.microsoft.com/ja-jp/cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|演算子の左側の hash\_set または hash\_multiset オブジェクトが右側の hash\_set または hash\_multiset オブジェクトと等しいかどうかをテストします。|  
  
### 特殊テンプレート関数  
  
|Hash\_set バージョン|Hash\_multiset バージョン|説明|  
|---------------------|--------------------------|--------|  
|[swap \(hash\_set\)](../Topic/swap%20\(hash_set\).md)|[swap \(hash\_multiset\)](../Topic/swap%20\(hash_multiset\).md)|2 つの hash\_set または hash\_multiset の要素を交換します。|  
  
### クラス  
  
|||  
|-|-|  
|[hash\_compare クラス](../standard-library/hash-compare-class.md)|任意のハッシュ連想コンテナー \(hash\_map、hash\_multimap、hash\_set、または hash\_multiset\) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。|  
|[hash\_set クラス](../standard-library/hash-set-class.md)|コレクションのデータを格納し、迅速に取得するために使用されます。このコレクションに含まれる要素の値は一意で、キー値として機能します。|  
|[hash\_multiset クラス](../Topic/hash_multiset%20Class.md)|コレクションのデータを格納し、迅速に取得するために使用されます。このコレクションに含まれる要素の値は一意で、キー値として機能します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)