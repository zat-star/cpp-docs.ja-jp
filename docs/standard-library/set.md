---
title: '&lt;set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83a933c889ad89ed7b5361217608303a9b42f500
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltsetgt"></a>&lt;set&gt;
コンテナー テンプレート クラスの set と multiset、およびそのサポート用テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <set>  
  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="operators"></a>演算子  
  
|set のバージョン|multiset のバージョン|説明|  
|-----------------|----------------------|-----------------|  
|[operator!= (set)](../standard-library/set-operators.md#op_neq)|[operator!= (multiset)](../standard-library/set-operators.md#op_neq)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しくないかどうかをテストします。|  
|[operator< (set)](../standard-library/set-operators.md#op_lt)|[operator< (multiset)](../standard-library/set-operators.md#op_lt_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト未満かどうかをテストします。|  
|[operator<= (set)](../standard-library/set-operators.md#op_lt_eq)|[operator\<= (multiset)](../standard-library/set-operators.md#op_lt_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以下かどうかをテストします。|  
|[operator== (set)](../standard-library/set-operators.md#op_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#op_eq_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトと等しいかどうかをテストします。|  
|[operator> (set)](../standard-library/set-operators.md#op_gt)|[operator> (multiset)](../standard-library/set-operators.md#op_gt_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクトより大きいかどうかをテストします。|  
|[operator>= (set)](../standard-library/set-operators.md#op_gt_eq)|[operator>= (multiset)](../standard-library/set-operators.md#op_gt_eq_multiset)|演算子の左側の set または multiset のオブジェクトが、右側の set または multiset のオブジェクト以上かどうかをテストします。|  
  
### <a name="specialized-template-functions"></a>特殊テンプレート関数  
  
|set のバージョン|multiset のバージョン|説明|  
|-----------------|----------------------|-----------------|  
|[swap](../standard-library/set-functions.md#swap)|[swap (multiset)](../standard-library/set-functions.md#swap_multiset)|2 つの set または multiset の要素を交換します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[set クラス](../standard-library/set-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意です。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|  
|[multiset クラス](../standard-library/multiset-class.md)|コレクションのデータを格納および取得するために使用されます。このコレクションに含まれる要素の値は一意とは限りません。この値はキー値として使用され、これに基づいてデータが自動的に順序付けられます。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



