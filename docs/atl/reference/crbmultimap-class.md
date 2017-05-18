---
title: "CRBMultiMap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
dev_langs:
- C++
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a72ddfbf4944f0de5e979f7046872d594017b9cf
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="crbmultimap-class"></a>CRBMultiMap クラス
このクラスは、各キーは、レッド ブラック バイナリ ツリーを使用して、1 つ以上の値を関連付けることができるをできるマップの構造体を表します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キーの要素の型。  
  
 *V*  
 値の要素型。  
  
 `KTraits`  
 コピーまたは主要な要素を移動するために使用するコードです。 参照してください[CElementTraits クラス](../../atl/reference/celementtraits-class.md)詳細です。  
  
 `VTraits`  
 コピーまたは値の要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|コンストラクターです。|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|指定したキーを持つ最初の要素の位置を検索するには、このメソッドを呼び出します。|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|指定されたキーに関連付けられている値を取得するには、このメソッドを呼び出すし、位置の値を更新します。|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|このメソッドを呼び出して、指定されたキーに関連付けられている要素を取得し、位置の値を更新します。|  
|[CRBMultiMap::Insert](#insert)|要素のペアをマップに挿入するには、このメソッドを呼び出します。|  
|[CRBMultiMap::RemoveKey](#removekey)|指定されたキーのキー/値の要素をすべて削除するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CRBMultiMap`主要な要素と値の順序付けられた配列を管理する、指定された型のマッピングの配列のサポートを提供します。 異なり、 [CRBMap](../../atl/reference/crbmap-class.md)クラスでは、各キーが&1; つ以上の値を関連付けることができます。  
  
 バイナリ ツリーの要素 (キーおよび値で構成される) が格納されている構造体を使用して、 [CRBMultiMap::Insert](#insert)メソッドです。 使用して要素を削除できる、 [CRBMultiMap::RemoveKey](#removekey)メソッドで、指定したキーに一致するすべての要素を削除します。  
  
 ツリーの走査を可能にメソッドのなど[CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition)、 [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext)、および[CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue)します。 アクセスする、キーごと可能性のある複数の値が可能なを使用して、 [CRBMultiMap::FindFirstWithKey](#findfirstwithkey)、 [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)、および[CRBMultiMap::GetNextWithKey](#getnextwithkey)メソッドです。 例を参照してください[CRBMultiMap::CRBMultiMap](#crbmultimap)説明については、この実習でします。  
  
 `KTraits`と`VTraits`パラメーターは、特徴 (traits) クラスをコピーまたは要素を移動するために必要な補足コードが含まれています。  
  
 `CRBMultiMap`派生した[CRBTree](../../atl/reference/crbtree-class.md)、レッド ブラック アルゴリズムを使用してバイナリ ツリーを実装します。 代わりに`CRBMultiMap`と`CRBMap`によって提供される、 [CAtlMap](../../atl/reference/catlmap-class.md)クラスです。 要素の数が少ないのみを格納する必要が、ときに、使用を検討して、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスの代わりにします。  
  
 さまざまなコレクション クラスとその機能とパフォーマンス特性の詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap  
 コンストラクターです。  
  
```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 `nBlockSize`パラメーターは、新しい要素が必要なときに割り当てられたメモリの量の測定値。 ブロック サイズの増加はメモリ割り当てルーチンの呼び出しを減らすためより多くのリソースを使用します。 既定値に、一度に 10 個の要素の領域を割り当てます。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&85;](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMultiMap:: ~ CRBMultiMap  
 デストラクターです。  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
##  <a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey  
 指定したキーを持つ最初の要素の位置を検索するには、このメソッドを呼び出します。  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素を識別するキーを指定します。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかった場合、NULL それ以外の場合は、キー/値の最初の要素の位置を返します。  
  
### <a name="remarks"></a>コメント  
 内のキー、 `CRBMultiMap`&1; つまたは複数の関連する値を持つことができます。 このメソッドでは、特定のキーに関連付けられている最初の値 (可能性のある、実際には、唯一の値) の位置の値を提供します。 と共に返される位置の値を使用して[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)または[CRBMultiMap::GetNextWithKey](#getnextwithkey)値を取得し、位置を更新します。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
### <a name="example"></a>例  
 例を参照してください[CRBMultiMap::CRBMultiMap](#crbmultimap)します。  
  
##  <a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey  
 指定されたキーに関連付けられている値を取得するには、このメソッドを呼び出すし、位置の値を更新します。  
  
```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 呼び出しで取得した位置の値[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)または[CRBMultiMap::GetNextWithKey](#getnextwithkey)、または前回の呼び出しに`GetNextValueWithKey`します。  
  
 `key`  
 検索する要素を識別するキーを指定します。  
  
### <a name="return-value"></a>戻り値  
 指定したキーに関連付けられている要素のペアを返します。  
  
### <a name="remarks"></a>コメント  
 位置の値は、キーに関連付けられている次の値を指すように更新されます。 値が存在しない場合、位置の値は NULL に設定しません。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
### <a name="example"></a>例  
 例を参照してください[CRBMultiMap::CRBMultiMap](#crbmultimap)します。  
  
##  <a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey  
 このメソッドを呼び出して、指定したキーに関連付けられている要素を取得し、位置の値を更新します。  
  
```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 呼び出しで取得した位置の値[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)または[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)、または前回の呼び出しに`GetNextWithKey`します。  
  
 `key`  
 検索する要素を識別するキーを指定します。  
  
### <a name="return-value"></a>戻り値  
 次を返す[CRBTree::CPair クラス](crbtree-class.md#cpair_class)指定したキーに関連付けられた要素。  
  
### <a name="remarks"></a>コメント  
 位置の値は、キーに関連付けられている次の値を指すように更新されます。 値が存在しない場合、位置の値は NULL に設定しません。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
##  <a name="insert"></a>CRBMultiMap::Insert  
 要素のペアをマップに挿入するには、このメソッドを呼び出します。  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 追加するキー値、`CRBMultiMap`オブジェクトです。  
  
 *value*  
 追加する値、`CRBMultiMap`に関連付けられたオブジェクト`key`します。  
  
### <a name="return-value"></a>戻り値  
 キー/値要素のペアの位置を返す、`CRBMultiMap`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
### <a name="example"></a>例  
 例を参照してください[CRBMultiMap::CRBMultiMap](#crbmultimap)します。  
  
##  <a name="removekey"></a>CRBMultiMap::RemoveKey  
 指定されたキーのキー/値の要素をすべて削除するには、このメソッドを呼び出します。  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 削除する要素を識別するキーを指定します。  
  
### <a name="return-value"></a>戻り値  
 指定したキーに関連付けられている値の数を返します。  
  
### <a name="remarks"></a>コメント  
 `RemoveKey`一致するキーを持っているキー/値の要素をすべて削除`key`します。  
  
 基本クラスのドキュメントを参照して[CRBTree](../../atl/reference/crbtree-class.md)利用可能なその他の方法についてです。  
  
### <a name="example"></a>例  
 例を参照してください[CRBMultiMap::CRBMultiMap](#crbmultimap)します。  
  
## <a name="see-also"></a>関連項目  
 [CRBTree クラス](../../atl/reference/crbtree-class.md)   
 [CAtlMap クラス](../../atl/reference/catlmap-class.md)   
 [CRBMap クラス](../../atl/reference/crbmap-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

