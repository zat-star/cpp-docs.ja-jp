---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<hash_map>
- <hash_map>
- std::<hash_map>
dev_langs:
- C++
helpviewer_keywords:
- hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a1c256df1182c00c1b6045923ba9975f02c9bfa2
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  このヘッダーは廃止され、互換性のために残されています。 代わりに、[<unordered_map>](../standard-library/unordered-map.md) を使用してください。  
  
 コンテナーのテンプレート クラス hash_map と hash_multimap、およびそのサポート用テンプレートを定義します。  
  
 Visual C++ .NET 2003 では、<hash_map> ヘッダー ファイルと <hash_set> ヘッダー ファイルのメンバーは std 名前空間に存在しなくなったのではなく、stdext 名前空間に移動されました。 詳細については、「[stdext Namespace](../standard-library/stdext-namespace.md)」(stdext 名前空間) をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>演算子  
  
|hash_map バージョン|hash_multimap バージョン|説明|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_map)](../standard-library/hash-map-operators.md#op_neq)|`operator!= (hash_multimap)`|演算子の左側の hash_map または hash_multimap オブジェクトが右側の hash_map または hash_multimap オブジェクトと等しくないかどうかをテストします。|  
|[operator== (hash_map)](../standard-library/hash-map-operators.md#op_eq_eq)|`operator== (hash_multimap)`|演算子の左側の hash_map または hash_multimap オブジェクトが右側の hash_map または hash_multimap オブジェクトと等しいかどうかをテストします。|  
  
### <a name="specialized-template-functions"></a>特殊テンプレート関数  
  
|hash_map バージョン|hash_multimap バージョン|説明|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_map)](../standard-library/hash-map-class.md#swap)|[swap (hash_multimap)](../standard-library/hash-multimap-class.md#swap)|2 つの hash_map または hash_multimap の要素を交換します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[hash_compare クラス](../standard-library/hash-compare-class.md)|任意のハッシュ連想コンテナー (hash_map、hash_multimap、hash_set、または hash_multiset) によって使用可能なオブジェクトを示しています。既定では **Traits** パラメーター オブジェクトを使用して、含まれる要素の順序付けおよびハッシュを行います。|  
|[value_compare クラス](../standard-library/value-compare-class.md)|要素のキーの値を比較し、要素の hash_map 内の相対順序を決定して、hash_map の要素を比較できる関数オブジェクトを提供します。|  
|[hash_map クラス](../standard-library/hash-map-class.md)|一意の並べ替えキーとそれに関連付けられている値のペアを要素として持つコレクションのデータを格納したり、迅速に取得したりするために使用されます。|  
|[hash_multimap クラス](../standard-library/hash-multimap-class.md)|必ずしも一意ではない並べ替えキーとそれに関連付けられている値のペアを要素として持つコレクションのデータを格納したり、迅速に取得したりするために使用されます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<hash_map>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




