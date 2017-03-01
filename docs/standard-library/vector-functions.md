---
title: "&lt;vector&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bb62c0c4e5b2965438539b17ec5a2c465e647ed7
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-functions"></a>&lt;vector&gt; 関数

  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 2 つのベクターの要素を交換します。  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 交換する要素を提供するベクター、またはベクター ` left` と要素を交換するベクター。  
  
 ` left`  
 ベクター ` right` と要素を交換するベクター。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス ベクターに特化したアルゴリズムであり、メンバー関数 ` left.` [vector::swap](../standard-library/vector-class.md) *( right*) を実行します。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
### <a name="example"></a>例  
  テンプレート バージョンの `swap` の使用例については、メンバー関数 [vector::swap](../standard-library/vector-class.md) のコード例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [\<vector>](../standard-library/vector.md)


