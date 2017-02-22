---
title: "texture_view クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# texture_view クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

テクスチャへの読み取りアクセスおよび書き込みアクセスを提供します。  `texture_view` は、既定の 32 ビット bpse である `int`、`unsigned int`、または `float` の値型のテクスチャを読み取るためにのみ使用できます。  他のテクスチャ形式を読み取るには、`texture_view<const _Value_type, _Rank>` を使用します。  
  
## 構文  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view : public details::_Texture_base<_Value_type, _Rank>;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view<const _Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
```  
  
#### パラメーター  
 `_Value_type`  
 テクスチャ集合体の要素型です。  
  
 `_Rank`  
 `texture_view` のランクです。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`value_type`|テクスチャ集合体の要素型です。|  
|`coordinates_type`|`texture_view` のテクセルを指定するために使用する座標の型。つまり、値型が `float` である関連するテクスチャと同じランクの `short_vector` です。|  
|`gather_return_type`|操作を収集するために使用される戻り値の型。つまり、サンプリングされた 4 つのテクセル値から収集された 4 つの同種の色要素を保持するランク 4 の `short_vector` です。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[texture\_view::texture\_view コンストラクター](../Topic/texture_view::texture_view%20Constructor.md)|オーバーロードされます。  `texture_view` インスタンスを構築します。|  
|[texture\_view::~texture\_view デストラクター](../Topic/texture_view::~texture_view%20Destructor.md)|`texture_view` インスタンスを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[texture\_view::gather\_alpha メソッド](../Topic/texture_view::gather_alpha%20Method.md)|オーバーロードされます。  指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルのアルファ \(w\) 要素を返します。|  
|[texture\_view::gather\_blue メソッド](../Topic/texture_view::gather_blue%20Method.md)|オーバーロードされます。  指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの青 \(z\) 要素を返します。|  
|[texture\_view::gather\_green メソッド](../Topic/texture_view::gather_green%20Method.md)|オーバーロードされます。  指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの緑 \(y\) 要素を返します。|  
|[texture\_view::gather\_red メソッド](../Topic/texture_view::gather_red%20Method.md)|オーバーロードされます。  指定されたサンプリング構成を使用して指定された座標でテクスチャをサンプリングし、4 つのサンプリングされたテクセルの赤 \(x\) 要素を返します。|  
|[texture\_view::get メソッド](../Topic/texture_view::get%20Method.md)|オーバーロードされます。  インデックスで要素の値を取得します。|  
|[texture\_view::sample メソッド](../Topic/texture_view::sample%20Method.md)|オーバーロードされます。  指定されたサンプリング構成を使用して詳細な指定された座標およびレベルでテクスチャをサンプリングします。|  
|[texture\_view::set メソッド](../Topic/texture_view::set%20Method.md)|インデックスで要素の値を設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[texture\_view::operator\(\) 演算子](../Topic/texture_view::operator\(\)%20Operator.md)|オーバーロードされます。  インデックスで要素の値を取得します。|  
|[texture\_view::operatorOperator](../Topic/texture_view::operatorOperator.md)|オーバーロードされます。  インデックスで要素の値を取得します。|  
|[texture\_view::operator\= 演算子](../Topic/texture_view::operator=%20Operator.md)|オーバーロードされます。  代入演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[texture\_view::value\_type データ メンバー](../Topic/texture_view::value_type%20Data%20Member.md)|`texture_view` の要素の値型です。|  
  
## 継承階層  
 `_Texture_base`  
  
 `texture_view`  
  
## 必要条件  
 **ヘッダー:** amp\_graphics.h  
  
 **名前空間:** concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)