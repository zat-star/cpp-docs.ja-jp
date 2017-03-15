---
title: '&lt;vector&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <vector>
- std.<vector>
- std::<vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 99aa5d5df1367dfb6e6f6c0b9333783240a12690
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt"></a>&lt;vector&gt;
コンテナー テンプレート クラス vector と、いくつかのサポート テンプレートを定義します。  
  
 `vector` 指定された型の要素を直線上のシーケンスに編成するコンテナーです。 このシーケンスでは、任意の要素を高速にランダム アクセスしたり、動的に追加および削除したりできます。 `vector` は、ランダム アクセスのパフォーマンスを重視するシーケンスに適したコンテナーです。  
  
 クラス `vector` の詳細については、「[vector クラス](../standard-library/vector-class.md)」をご覧ください。 特殊化 `vector<bool>` の詳細については、「[vector\<bool> クラス](../standard-library/vector-bool-class.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>パラメーター  
 型  
 ベクター内に格納されるデータ型に対するテンプレート パラメーター。  
  
 アロケーター  
 メモリの割り当てと解放を担当する格納されたアロケーター オブジェクトのテンプレート パラメーター。  
  
 ` left`  
 比較演算の最初の (左辺の) ベクター  
  
 ` right`  
 比較演算の&2; つ目の (右辺の) ベクター。  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator! =](../standard-library/vector-operators.md#operator_neq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しくないかどうかを調べます。|  
|[operator<](../standard-library/vector-operators.md#operator_lt_)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより小さいかどうかを調べます。|  
|[operator\<=](../standard-library/vector-operators.md#operator_lt__eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以下かどうかを調べます。|  
|[operator==](../standard-library/vector-operators.md#operator_eq_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しいかどうかを調べます。|  
|[operator>](../standard-library/vector-operators.md#operator_gt_)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより大きいかどうかを調べます。|  
|[operator>=](../standard-library/vector-operators.md#operator_gt__eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以上かどうかを調べます。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[vector クラス](../standard-library/vector-class.md)|指定された型の要素を直線上に配置し、任意の要素に対する高速なランダム アクセスを可能にするシーケンス コンテナーのテンプレート クラスです。|  
  
### <a name="specializations"></a>特殊化  
  
|||  
|-|-|  
|[vector\<bool> クラス](../standard-library/vector-bool-class.md)|テンプレート クラス vector を型 `bool` の要素に対して完全に特殊化したもので、基になる型のアロケーターを特殊化で使用します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<vector>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)


