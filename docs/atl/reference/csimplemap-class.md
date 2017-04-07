---
title: "CSimpleMap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 21
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c02ef1d9d3fafebf38abaaa55d77511f4476a02f
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemap-class"></a>CSimpleMap クラス
このクラスは、単純なマッピングの配列のサポートを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>  
class CSimpleMap
```  
  
#### <a name="parameters"></a>パラメーター  
 `TKey`  
 キーの要素の型。  
  
 `TVal`  
 値の要素型。  
  
 `TEqual`  
 型の要素に対して等値テストを定義する、特徴オブジェクト`T`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|値型の Typedef。|  
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|キーの種類の Typedef。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMap::CSimpleMap](#csimplemap)|コンストラクターです。|  
|[CSimpleMap:: ~ CSimpleMap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMap::Add](#add)|マップの配列をキーと関連付けられている値を追加します。|  
|[CSimpleMap::FindKey](#findkey)|特定のキーを検索します。|  
|[:Findval](#findval)|特定の値を検索します。|  
|[CSimpleMap::GetKeyAt](#getkeyat)|指定したキーを取得します。|  
|[CSimpleMap::GetSize](#getsize)|マップ配列のエントリの数を返します。|  
|[CSimpleMap::GetValueAt](#getvalueat)|指定した値を取得します。|  
|[CSimpleMap::Lookup](#lookup)|指定したキーに関連付けられている値を返します。|  
|[CSimpleMap::Remove](#remove)|キーと一致する値を削除します。|  
|[CSimpleMap::RemoveAll](#removeall)|すべてのキーと値を削除します。|  
|[CSimpleMap::RemoveAt](#removeat)|特定のキーと一致する値を削除します。|  
|[CSimpleMap::ReverseLookup](#reverselookup)|指定した値に関連付けられているキーを返します。|  
|[CSimpleMap::SetAt](#setat)|指定したキーに関連付けられている値を設定します。|  
|[CSimpleMap::SetAtIndex](#setatindex)|特定のキーと値を設定します。|  
  
## <a name="remarks"></a>コメント  
 `CSimpleMap`では、特定の型の単純なマッピング配列`T`、主要な要素と関連付けられている値の順序なしの配列を管理します。  
  
 パラメーター`TEqual`型の&2; つの要素に対して等値関数を定義する手段を提供`T`します。 ようなクラスを作成して[CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)、指定した配列に等値テストの動作を変更することはできます。 たとえば、ポインターの配列を扱う場合、ポインターが参照値に応じてとして等価性を定義すると便利ですがあります。 既定の実装を利用**operator==()**します。  
  
 両方とも`CSimpleMap`と[CSimpleArray](../../atl/reference/csimplearray-class.md)が提供されて以前の ATL との互換性は、次のリリース、およびによってより完全なと効率的なコレクションの実装が提供される[CAtlArray](../../atl/reference/catlarray-class.md)と[CAtlMap](../../atl/reference/catlmap-class.md)します。  
  
 ATL と MFC での他のマップ コレクションとは異なりこのクラスは、単純な配列と検索一方向の検索が必要です。 `CAtlMap`配列には、多くの要素が含まれている場合に使用する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&91;](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleMap::Add  
 マップの配列をキーと関連付けられている値を追加します。  
  
```
BOOL Add(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キー。  
  
 *val*  
 関連する値。  
  
### <a name="return-value"></a>戻り値  
 キーと値が正常に追加され、FALSE それ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 各キーと値のペアが追加されると、マップ配列のメモリが解放され、再割り当てされた場合、それぞれのデータは常に連続して保存するためにします。 2 番目のキー要素常に直接依存してメモリ内の最初のキー要素にします。  
  
##  <a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType  
 キーの種類の typedef。  
  
```
typedef TVal _ArrayElementType;
```  
  
##  <a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType  
 値型の typedef。  
  
```
typedef TKey _ArrayKeyType;
```  
  
##  <a name="csimplemap"></a>CSimpleMap::CSimpleMap  
 コンストラクターです。  
  
```
CSimpleMap();
```  
  
### <a name="remarks"></a>コメント  
 データ メンバーを初期化します。  
  
##  <a name="dtor"></a>CSimpleMap:: ~ CSimpleMap  
 デストラクターです。  
  
```
~CSimpleMap();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="findkey"></a>CSimpleMap::FindKey  
 特定のキーを検索します。  
  
```
int FindKey(const TKey& key) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索対象のキー。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合が存在する場合はキーのインデックスを返すには、-1 が返されます。  
  
##  <a name="findval"></a>:Findval  
 特定の値を検索します。  
  
```
int FindVal(const TVal& val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *val*  
 検索対象の値です。  
  
### <a name="return-value"></a>戻り値  
 値のインデックスが見つかった場合は、それ以外の場合は-1 を返しますが返されます。  
  
##  <a name="getkeyat"></a>CSimpleMap::GetKeyAt  
 指定したインデックスにキーを取得します。  
  
```
TKey& GetKeyAt(int nIndex) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 返されるキーのインデックス。  
  
### <a name="return-value"></a>戻り値  
 によって参照されるキーを返す`nIndex`します。  
  
### <a name="remarks"></a>コメント  
 渡されたインデックス`nIndex`意味を持つように、戻り値に対して有効である必要があります。  
  
##  <a name="getsize"></a>CSimpleMap::GetSize  
 マップ配列のエントリの数を返します。  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 マップ配列のエントリ (キーと値は&1; つのエントリ) の数を返します。  
  
##  <a name="getvalueat"></a>CSimpleMap::GetValueAt  
 特定のインデックス位置にある値を取得します。  
  
```
TVal& GetValueAt(int nIndex) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 返される値のインデックス。  
  
### <a name="return-value"></a>戻り値  
 によって参照される値を返す`nIndex`します。  
  
### <a name="remarks"></a>コメント  
 渡されたインデックス`nIndex`意味を持つように、戻り値に対して有効である必要があります。  
  
##  <a name="lookup"></a>CSimpleMap::Lookup  
 指定したキーに関連付けられている値を返します。  
  
```
TVal Lookup(const TKey& key) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キー。  
  
### <a name="return-value"></a>戻り値  
 関連付けられている値を返します。 一致するキーがない場合が存在すると、NULL が返されます。  
  
##  <a name="remove"></a>CSimpleMap::Remove  
 キーと一致する値を削除します。  
  
```
BOOL Remove(const TKey& key);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キー。  
  
### <a name="return-value"></a>戻り値  
 かどうか、キーと一致する値は、正常に削除された場合は FALSE それ以外の場合は TRUE を返します。  
  
##  <a name="removeall"></a>CSimpleMap::RemoveAll  
 すべてのキーと値を削除します。  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 マップの配列オブジェクトからすべてのキーと値を削除します。  
  
##  <a name="removeat"></a>CSimpleMap::RemoveAt  
 キーと指定したインデックスに関連付けられている値を削除します。  
  
```
BOOL RemoveAt(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 キーと関連付けられている値を削除するインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定されたインデックスが無効なインデックスの場合は、成功した場合、FALSE の TRUE を返します。  
  
##  <a name="reverselookup"></a>CSimpleMap::ReverseLookup  
 指定した値に関連付けられているキーを返します。  
  
```
TKey ReverseLookup(const TVal& val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *val*  
 値。  
  
### <a name="return-value"></a>戻り値  
 関連付けられているキーを返します。 一致するキーがない場合が存在すると、NULL が返されます。  
  
##  <a name="setat"></a>CSimpleMap::SetAt  
 指定したキーに関連付けられている値を設定します。  
  
```
BOOL SetAt(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 キー。  
  
 *val*  
 割り当てる新しい値。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかり、その値が正常に変更された、それ以外の場合は TRUE を返します。  
  
##  <a name="setatindex"></a>CSimpleMap::SetAtIndex  
 指定したインデックス位置には、キーと値を設定します。  
  
```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 キーと値のペアを変更するを参照するインデックス。  
  
 `key`  
 新しいキー。  
  
 *val*  
 新しい値。  
  
### <a name="return-value"></a>戻り値  
 True の正常終了した場合のインデックスが有効なかどうか。  
  
### <a name="remarks"></a>コメント  
 更新、キーと値の両方が指す`nIndex`します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

