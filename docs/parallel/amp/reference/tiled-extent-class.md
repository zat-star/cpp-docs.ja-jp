---
title: "tiled_extent クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
dev_langs:
- C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: e295b56290435a1d87ac2f0dbc0951850600534d
ms.lasthandoff: 03/31/2017

---
# <a name="tiledextent-class"></a>tiled_extent クラス
`tiled_extent` オブジェクトは 3 つの次元のいずれかの `extent` オブジェクトであり、範囲空間を 1、2、または 3 次元のタイルに再分割します。  
  
### <a name="syntax"></a>構文  
  
```  
template <
    int _Dim0,  
    int _Dim1,  
    int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
 
template <
    int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dim0`  
 最上位の次元の長さ。  
  
 `_Dim1`  
 最上位の次の次元の長さ。  
  
 `_Dim2`  
 最下位の次元の長さ。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[tiled_extent コンス トラクター](#ctor)|`tiled_extent` クラスの新しいインスタンスを初期化します。|  

  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_tile_extent](#get_tile_extent)|`extent` テンプレート引数 `tiled_extent`、`_Dim0`、および `_Dim1` の値をキャプチャする `_Dim2` オブジェクトを返します。|  
|[パッド](#pad)|タイルの次元によって均等に分割できる範囲を上方調整した新しい `tiled_extent` オブジェクトを返します。|  
|[truncate](#truncate)|タイルの次元によって均等に分割できるように範囲を下方調整した新しい `tiled_extent` オブジェクトを返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|指定された `tiled_index` オブジェクトの内容をこのオブジェクトにコピーします。|  

  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[tile_dim0 定数](#tile_dim0)|最上位の次元の長さを格納します。|  
|[tile_dim1 定数](#tile_dim1)|最上位の次の次元の長さを格納します。|  
|[tile_dim2 定数](#tile_dim2)|最下位の次元の長さを格納します。|  

  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[tile_extent](#tile_extent)|`extent` テンプレート引数 `tiled_extent`、`_Dim0`、および `_Dim1` の値をキャプチャする `_Dim2` オブジェクトを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  

## <a name="ctor"></a> tiled_extent コンス トラクター  
`tiled_extent` クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
tiled_extent();  
  
tiled_extent(  
    const Concurrency::extent<rank>& _Other );  
  
tiled_extent(  
    const tiled_extent& _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `extent` オブジェクトまたは `tiled_extent` オブジェクト。  
  

  

## <a name="get_tile_extent"></a> get_tile_extent   
返します、`extent`オブジェクトの値をキャプチャする、`tiled_extent`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`です。  
  
### <a name="syntax"></a>構文  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>戻り値  
 この `extent` インスタンスの次元をキャプチャする `tiled_extent` オブジェクト。  
  

## <a name="pad"></a>  pad   
タイルの次元によって均等に分割できる範囲を上方調整した新しい `tiled_extent` オブジェクトを返します。  
  
### <a name="syntax"></a>構文  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>戻り値  
 新しい `tiled_extent` オブジェクト、値渡し。 
## <a name="truncate"></a> truncate   
タイルの次元によって均等に分割できるように範囲を下方調整した新しい `tiled_extent` オブジェクトを返します。  
  
### <a name="syntax"></a>構文  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タイルの次元によって均等に分割できるように範囲を下方調整した新しい `tiled_extent` オブジェクトを返します。  

## <a name="operator_eq"></a>演算子 =   
指定された `tiled_index` オブジェクトの内容をこのオブジェクトにコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `tiled_index` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `tiled_index` インスタンスへの参照。  

## <a name="tile_dim0"></a> tile_dim0   
最上位の次元の長さを格納します。  
  
### <a name="syntax"></a>構文  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tile_dim1"></a> tile_dim1   
最上位の次の次元の長さを格納します。  
  
### <a name="syntax"></a>構文  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tile_dim2"></a> tile_dim2   
最下位の次元の長さを格納します。  
  
### <a name="syntax"></a>構文  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tile_extent"></a> tile_extent   
  取得、`extent`オブジェクトの値をキャプチャする、`tiled_extent`テンプレート引数`_Dim0`、 `_Dim1`、および`_Dim2`です。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)

