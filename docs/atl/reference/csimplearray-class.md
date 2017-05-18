---
title: "CSimpleArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e261f95a375a2edda1d543a36b605d23fc718b99
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearray-class"></a>CSimpleArray クラス
このクラスは、単純な配列を管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>  
class CSimpleArray
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 配列に格納するデータの種類。  
  
 `TEqual`  
 型の要素に対して等値テストを定義する、特徴オブジェクト`T`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleArray::CSimpleArray](#csimplearray)|単純な配列のコンス トラクターです。|  
|[CSimpleArray:: ~ CSimpleArray](#dtor)|単純な配列のデストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleArray::Add](#add)|新しい要素を配列に追加します。|  
|[CSimpleArray::Find](#find)|配列の要素を検索します。|  
|[CSimpleArray::GetData](#getdata)|配列に格納されているデータへのポインターを返します。|  
|[CSimpleArray::GetSize](#getsize)|配列に格納されている要素の数を返します。|  
|[CSimpleArray::Remove](#remove)|配列から指定された要素を削除します。|  
|[CSimpleArray::RemoveAll](#removeall)|配列からすべての要素を削除します。|  
|[CSimpleArray::RemoveAt](#removeat)|配列から指定された要素を削除します。|  
|[CSimpleArray::SetAtIndex](#setatindex)|指定した要素を配列に設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleArray::operator\[\]](#operator_at)|配列から要素を取得します。|  
|[CSimpleArray::operator =](#operator_eq)|代入演算子。|  

  
## <a name="remarks"></a>コメント  
 `CSimpleArray`作成して、指定された型の単純な配列を管理するメソッドを提供`T`します。  
  
 パラメーター`TEqual`型の&2; つの要素に対して等値関数を定義する手段を提供`T`します。 ようなクラスを作成して[CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)、指定した配列に等値テストの動作を変更することはできます。 たとえば、ポインターの配列を扱う場合、ポインターが参照値に応じてとして等価性を定義すると便利ですがあります。 既定の実装を利用**operator=()**します。  
  
 両方とも`CSimpleArray`と[CSimpleMap](../../atl/reference/csimplemap-class.md)要素の数が少ない場合に設計されています。 [CAtlArray](../../atl/reference/catlarray-class.md)と[CAtlMap](../../atl/reference/catlmap-class.md)配列には、多くの要素が含まれている場合に使用する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&86;](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleArray::Add  
 新しい要素を配列に追加します。  
  
```
BOOL Add(const T& t);
```  
  
### <a name="parameters"></a>パラメーター  
 *t*  
 配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 かどうか、要素が正常に追加した配列を FALSE にそれ以外の場合は TRUE を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&87;](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]  
  
##  <a name="csimplearray"></a>CSimpleArray::CSimpleArray  
 配列オブジェクトのコンス トラクターです。  
  
```
CSimpleArray(const CSimpleArray<T, TEqual>& src);  
CSimpleArray();
```     
  
### <a name="parameters"></a>パラメーター  
 *src*  
 既存の `CSimpleArray` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 新しい空の作成、データ メンバーは初期化`CSimpleArray`オブジェクト、または、既存のコピー`CSimpleArray`オブジェクトです。  
  
##  <a name="dtor"></a>CSimpleArray:: ~ CSimpleArray  
 デストラクターです。  
  
```
~CSimpleArray();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているすべてのリソースを解放します。  
  
##  <a name="find"></a>CSimpleArray::Find  
 配列の要素を検索します。  
  
```
int Find(const T& t) const;
```  
  
### <a name="parameters"></a>パラメーター  
 *t*  
 検索対象の要素。  
  
### <a name="return-value"></a>戻り値  
 要素が見つからない場合は、検出された要素のインデックスを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&88;](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]  
  
##  <a name="getdata"></a>CSimpleArray::GetData  
 配列に格納されているデータへのポインターを返します。  
  
```
T* GetData() const;
```  
  
### <a name="return-value"></a>戻り値  
 配列内のデータへのポインターを返します。  
  
##  <a name="getsize"></a>CSimpleArray::GetSize  
 配列に格納されている要素の数を返します。  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 配列に格納されている要素の数を返します。  
  
##  <a name="operator_at"></a>CSimpleArray::operator\[\]  
 配列から要素を取得します。  
  
```
T& operator[](int nindex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 によって参照される配列の要素を返します`nIndex`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&89;](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]  
  
##  <a name="operator_eq"></a>CSimpleArray::operator =  
 代入演算子。  
  
```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 コピー先の配列。  
  
### <a name="return-value"></a>戻り値  
 更新後にポインターを返す`CSimpleArray`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 すべての要素をコピー、`CSimpleArray`によって参照されるオブジェクト*src*現在の配列オブジェクトにすべての既存のデータを交換します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&90;](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]  
  
##  <a name="remove"></a>CSimpleArray::Remove  
 配列から指定された要素を削除します。  
  
```
BOOL Remove(const T& t);
```  
  
### <a name="parameters"></a>パラメーター  
 *t*  
 配列から削除する要素。  
  
### <a name="return-value"></a>戻り値  
 かどうか要素が見つかったおよび削除された場合は FALSE それ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 要素が削除されると、配列内の残りの要素が空の領域がいっぱいに番号が変更されます。  
  
##  <a name="removeall"></a>CSimpleArray::RemoveAll  
 配列からすべての要素を削除します。  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 配列に格納されているすべての要素を削除します。  
  
##  <a name="removeat"></a>CSimpleArray::RemoveAt  
 配列から指定された要素を削除します。  
  
```
BOOL RemoveAtint nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 削除する要素を指すインデックス。  
  
### <a name="return-value"></a>戻り値  
 要素が削除された、インデックスが有効な場合は FALSE のかどうかは TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 要素が削除されると、配列内の残りの要素が空の領域がいっぱいに番号が変更されます。  
  
##  <a name="setatindex"></a>CSimpleArray::SetAtIndex  
 配列の指定した要素を設定します。  
  
```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 変更する要素のインデックス。  
  
 *t*  
 指定された要素に代入する値。  
  
### <a name="return-value"></a>戻り値  
 True の正常終了した場合のインデックスが有効なかどうか。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

