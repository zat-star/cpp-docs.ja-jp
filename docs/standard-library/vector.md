---
title: "&lt; vector &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<vector>"
  - "std.<vector>"
  - "std::<vector>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector ヘッダー"
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# &lt; vector &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナー テンプレート クラス vector と、いくつかのサポート テンプレートを定義します。  
  
 `vector` 指定された型の要素を直線上のシーケンスに編成するコンテナーです。 このシーケンスでは、任意の要素を高速にランダム アクセスしたり、動的に追加および削除したりできます。 `vector` は、ランダム アクセスのパフォーマンスを重視するシーケンスに適したコンテナーです。  
  
 クラスの詳細については `vector`, を参照してください [vector クラス](../standard-library/vector-class.md)します。 特殊化について `vector<bool>`, を参照してください [vector \< bool> クラス](../Topic/vector%3Cbool%3E%20Class.md)します。  
  
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
 比較演算の 2 つ目の (右辺の) ベクター。  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子。=](../Topic/%3Cvector%3E%20operators.md#operator_neq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しくないかどうかを調べます。|  
|[演算子 <](../Topic/%3Cvector%3E%20operators.md#operator_lt_)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより小さいかどうかを調べます。|  
|[operator \< =](../Topic/%3Cvector%3E%20operators.md#operator_lt__eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以下かどうかを調べます。|  
|[演算子 = =](../Topic/%3Cvector%3E%20operators.md#operator_eq_eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトと等しいかどうかを調べます。|  
|[演算子 >](../Topic/%3Cvector%3E%20operators.md#operator_gt_)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクトより大きいかどうかを調べます。|  
|[operator > =](../Topic/%3Cvector%3E%20operators.md#operator_gt__eq)|演算子の左辺のベクター オブジェクトが右辺のベクター オブジェクト以上かどうかを調べます。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[vector クラス](../standard-library/vector-class.md)|指定された型の要素を直線上に配置し、任意の要素に対する高速なランダム アクセスを可能にするシーケンス コンテナーのテンプレート クラスです。|  
  
### <a name="specializations"></a>特殊化  
  
|||  
|-|-|  
|[vector \< bool> クラス](../Topic/vector%3Cbool%3E%20Class.md)|テンプレート クラス vector を型 `bool` の要素に対して完全に特殊化したもので、基になる型のアロケーターを特殊化で使用します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \< ベクトル>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)

