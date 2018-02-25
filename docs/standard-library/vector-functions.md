---
title: "&lt;vector&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: e752c3d39787466928b11ff8d644cf9a6558b656
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 関数

  
##  <a name="swap"></a>  swap  
 2 つのベクターの要素を交換します。  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供するベクター、またはベクター `left` と要素を交換するベクター。  
  
 `left`  
 ベクター `right` と要素を交換するベクター。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を実行するコンテナー クラス vector に特化したアルゴリズムは、テンプレート関数は`left`します。 [vector::swap](../standard-library/vector-class.md) *(右*)。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
### <a name="example"></a>例  
  テンプレート バージョンの `swap` の使用例については、メンバー関数 [vector::swap](../standard-library/vector-class.md) のコード例をご覧ください。  
  
## <a name="see-also"></a>参照  
 [\<vector>](../standard-library/vector.md)

