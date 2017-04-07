---
title: "CAtlMap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3730827a56c47497db2fd8324f54c7ba88a584d6
ms.lasthandoff: 02/24/2017

---
# <a name="catlmap-class"></a>CAtlMap クラス
このクラスは、作成して、map オブジェクトを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>>
class CAtlMap
```  
  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キーの要素の型。  
  
 V  
 値の要素型。  
  
 `KTraits`  
 コピーまたは主要な要素を移動するために使用するコードです。 参照してください[CElementTraits クラス](../../atl/reference/celementtraits-class.md)詳細です。  
  
 `VTraits`  
 コピーまたは値の要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|キーが入力引数として渡されるときに使用される型|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|キーが出力引数として返されるときに使用される型。|  
|[CAtlMap::VINARGTYPE](#vinargtype)|値が入力引数として渡されるときに使用される型。|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|値が出力引数として渡されるときに使用される型。|  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::CPair クラス](#cpair_class)|キーと値の要素を含むクラスです。|  

  
### <a name="cpair-data-members"></a>CPair データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|キーの要素を格納するデータ メンバーです。|  
|[CPair::m_value](#m_value)|値の要素を格納するデータ メンバーです。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|コンストラクターです。|  
|[CAtlMap:: ~ CAtlMap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|アサートが発生する場合にこのメソッドを呼び出して、`CAtlMap`が無効です。|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|自動再ハッシュを無効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|自動再ハッシュを有効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::GetAt](#getat)|マップの指定した位置にある要素を返すには、このメソッドを呼び出します。|  
|[CAtlMap::GetCount](#getcount)|マップ内の要素の数を取得するには、このメソッドを呼び出します。|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|マップのハッシュ テーブル内のビンの数を確認するには、このメソッドを呼び出します。|  
|[CAtlMap::GetKeyAt](#getkeyat)|指定された位置に格納されているキーを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクトです。|  
|[で](#getnext)|ペアが格納されている次の要素へのポインターを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクトです。|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CAtlMap::GetNextKey](#getnextkey)|次のキーを取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::GetNextValue](#getnextvalue)|次の値を取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::GetStartPosition](#getstartposition)|マップの反復処理を開始するには、このメソッドを呼び出します。|  
|[CAtlMap::GetValueAt](#getvalueat)|指定された位置に格納されている値を取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[格納します。](#inithashtable)|このメソッドでは、ハッシュ テーブルを初期化します。|  
|[CAtlMap::IsEmpty](#isempty)|空のマップ オブジェクトをテストするには、このメソッドを呼び出します。|  
|[CAtlMap::Lookup](#lookup)|キーまたは値を検索するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::Rehash](#rehash)|Rehash にこのメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::RemoveAll](#removeall)|すべての要素を削除するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::RemoveAtPos](#removeatpos)|指定された位置に要素を削除するには、このメソッドを呼び出す、`CAtlMap`オブジェクトです。|  
|[CAtlMap::RemoveKey](#removekey)|要素を削除するには、このメソッドを呼び出して、`CAtlMap`キーが指定されたオブジェクト。|  
|[CAtlMap::SetAt](#setat)|要素のペアをマップに挿入するには、このメソッドを呼び出します。|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|最適なロードを設定するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
|[CAtlMap::SetValueAt](#setvalueat)|内の指定位置に格納された値を変更するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|置換したり、新しい要素を追加したり、`CAtlMap`です。|  

  
## <a name="remarks"></a>コメント  
 `CAtlMap`主要な要素と関連付けられている値の順序なしの配列を管理する、指定された型のマッピングの配列のサポートを提供します。 (キーおよび値で構成される) の要素は、大量のデータを効率よく格納および取得できるように、ハッシュ アルゴリズムを使用して格納されます。  
  
 `KTraits`と`VTraits`パラメーターは、特徴 (traits) クラスをコピーまたは要素を移動するために必要な補足コードが含まれています。  
  
 代わりに`CAtlMap`によって提供される、 [CRBMap](../../atl/reference/crbmap-class.md)クラスです。 `CRBMap`さまざまなパフォーマンスの特徴はキー/値ペアを保存します。 所要時間を項目を挿入しますが、キーを検索またはからキーを削除、`CRBMap`の注文オブジェクトでは*log (n)*ここで、 *n*要素の数です。 `CAtlMap`、注文の最悪のシナリオがあります。 通常、定数時間がかかるこれらすべての操作*n*します。 一般的な例でそのため、`CAtlMap`高速です。  
  
 その他の違い`CRBMap`と`CAtlMap`格納されている要素を反復処理するときに、明らかになります。 `CRBMap`、並べ替えられた順序で要素にアクセスする方法です。 `CAtlMap`要素の順序がありません、および順序を推論できません。  
  
 少数の要素を格納する必要がある場合は、使用を検討して、 [CSimpleMap](../../atl/reference/csimplemap-class.md)クラスの代わりにします。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="assertvalid"></a>CAtlMap::AssertValid  
 アサートが発生する場合にこのメソッドを呼び出して、`CAtlMap`オブジェクトが無効です。  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、このメソッドは、アサート場合、`CAtlMap`オブジェクトが無効です。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="catlmap"></a>CAtlMap::CAtlMap  
 コンストラクターです。  
  
```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBins`  
 格納されている要素へのポインターを提供するビンの数。 ビンの詳細については、このトピックの後半の「解説」を参照してください。  
  
 `fOptimalLoad`  
 最適な読み込みの比率です。  
  
 `fLoThreshold`  
 負荷率の下限のしきい値。  
  
 `fHiThreshold`  
 負荷率の上限のしきい値。  
  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 `CAtlMap`キーのハッシュ アルゴリズムを使用してインデックスを作成して、格納されている要素のすべてを参照します。 このインデックスは、格納されている要素へのポインターを含む"bin"を参照します。 箱が既に使用されている、後続の要素にアクセスするリンクされたリストが作成されます。 正しい要素に直接アクセスするよりも遅くなりますが、リスト内の移動と、マップの構造がパフォーマンスとストレージ要件のバランスを取る必要があるためです。 ほとんどの場合最適な結果を提供する既定のパラメーターが選択されました。  
  
 読み込みの比率は、マップ オブジェクト内に格納されている要素の数のビンの数の比率です。 マップの構造が再計算するとき、 *fOptimalLoad*パラメーター値が必要なビンの数を計算に使用されます。 使用して、この値を変更することができます、 [CAtlMap::SetOptimalLoad](#setoptimalload)メソッドです。  
  
 `fLoThreshold`パラメーターは、前に負荷率に到達可能な下限値`CAtlMap`マップの最適なサイズを再計算されます。  
  
 `fHiThreshold`パラメーターは、前に負荷率を取得できる上限の値、`CAtlMap`オブジェクトは、マップの最適なサイズを再計算されます。  
  
 この再計算プロセス (再ハッシュと呼ばれます) は既定で有効にします。 大量のデータで同時に呼び出しを入力するときに、このプロセスを無効にする場合、 [CAtlMap::DisableAutoRehash](#disableautorehash)メソッドです。 再アクティブ化することで、 [CAtlMap::EnableAutoRehash](#enableautorehash)メソッドです。  
  
 `nBlockSize`パラメーターは、新しい要素が必要なときに割り当てられたメモリの量の測定値。 ブロック サイズの増加はメモリ割り当てルーチンの呼び出しを減らすためより多くのリソースを使用します。  
  
 すべてのデータを格納できる前への呼び出しでハッシュ テーブルを初期化する必要が[格納する](#inithashtable)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&72;](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlMap:: ~ CAtlMap  
 デストラクターです。  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたリソースを解放します。  
  
##  <a name="cpair_class"></a>CAtlMap::CPair クラス  
 キーと値の要素を含むクラスです。  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>コメント  
 このクラスは、メソッドによって使用[で](#getnext)と[CAtlMap::Lookup](#lookup)マップの構造体に格納されているキーと値の要素にアクセスします。  
  
##  <a name="disableautorehash"></a>CAtlMap::DisableAutoRehash  
 自動再ハッシュを無効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>コメント  
 自動再ハッシュには、(既定である) 有効な場合は、ハッシュ テーブルでビンの数が自動的に再計算されます負荷値 (配列に格納されている要素の数のビンの数の比率) が、マップの作成時に指定された最大値または最小値を超えています。  
  
 `DisableAutoRehash`最も役立つ多数の要素を一度にマップに追加されます。 呼び出す方が効率的です rehashing プロセスをトリガーする制限を超えるたびに、代わりに`DisableAutoRehash`、要素を追加し、最後を呼び出して、 [CAtlMap::EnableAutoRehash](#enableautorehash)します。  
  
##  <a name="enableautorehash"></a>CAtlMap::EnableAutoRehash  
 自動再ハッシュを有効にするには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>コメント  
 自動再ハッシュには、(既定である) 有効な場合は、ハッシュ テーブルでビンの数が自動的に再計算されます負荷値 (配列に格納されている要素の数のビンの数の比率) が、マップの作成時に指定された最大値または最小値を超えています。  
  
 **EnableAutoRefresh**への呼び出し後に最も頻繁に使用[CAtlMap::DisableAutoRehash](#disableautorehash)します。  
  
##  <a name="getat"></a>CAtlMap::GetAt  
 マップの指定した位置にある要素を返すには、このメソッドを呼び出します。  
  
```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
 `key`  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 *value*  
 マップの値の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 マップに格納されているキー/値要素の現在の組み合わせへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドで、アサーション エラーが発生場合`pos`が NULL です。  
  
##  <a name="getcount"></a>CAtlMap::GetCount  
 マップ内の要素の数を取得するには、このメソッドを呼び出します。  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 マップ オブジェクト内の要素の数を返します。 1 つの要素は、キー/値ペアです。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="gethashtablesize"></a>CAtlMap::GetHashTableSize  
 マップのハッシュ テーブル内のビンの数を確認するには、このメソッドを呼び出します。  
  
```
UINT GetHashTableSize() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ハッシュ テーブルには、ビンの数を返します。 参照してください[CAtlMap::CAtlMap](#catlmap)説明します。  
  
##  <a name="getkeyat"></a>CAtlMap::GetKeyAt  
 指定された位置に格納されているキーを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクトです。  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
### <a name="return-value"></a>戻り値  
 指定された位置に格納されたキーへの参照を返す、`CAtlMap`オブジェクトです。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="getnext"></a>で  
 ペアが格納されている次の要素へのポインターを取得するには、このメソッドを呼び出す、`CAtlMap`オブジェクトです。  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
### <a name="return-value"></a>戻り値  
 マップに格納されているキー/値要素の次の組み合わせへのポインターを返します。 `pos`位置カウンターは、各呼び出しの後に更新します。 取得した要素が、マップ内の最後の場合`pos`は NULL に設定します。  
  
##  <a name="getnextassoc"></a>CAtlMap::GetNextAssoc  
 反復処理するためには、次の要素を取得します。  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
 `key`  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 *value*  
 マップの値の型を指定するテンプレート パラメーター。  
  
### <a name="remarks"></a>コメント  
 `pos`位置カウンターは、各呼び出しの後に更新します。 取得した要素が、マップ内の最後の場合`pos`は NULL に設定します。  
  
##  <a name="getnextkey"></a>CAtlMap::GetNextKey  
 次のキーを取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
### <a name="return-value"></a>戻り値  
 マップ内の次のキーへの参照を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`します。 マップのエントリがある場合、位置カウンターは NULL に設定します。  
  
##  <a name="getnextvalue"></a>CAtlMap::GetNextValue  
 次の値を取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
### <a name="return-value"></a>戻り値  
 マップ内の次の値への参照を返します。  
  
### <a name="remarks"></a>コメント  
 現在の位置のカウンターを更新`pos`します。 マップのエントリがある場合、位置カウンターは NULL に設定します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="getstartposition"></a>CAtlMap::GetStartPosition  
 マップの反復処理を開始するには、このメソッドを呼び出します。  
  
```
POSITION GetStartPosition() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 マップが空の場合に、開始位置、または NULL が返されますが返されます。  
  
### <a name="remarks"></a>コメント  
 返すことによって、マップの反復処理を開始するには、このメソッドを呼び出して、**位置**値を渡すことができる、`GetNextAssoc`メソッドです。  
  
> [!NOTE]
>  繰り返しシーケンスは予測できません。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="getvalueat"></a>CAtlMap::GetValueAt  
 指定された位置に格納されている値を取得するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
### <a name="return-value"></a>戻り値  
 指定された位置に格納されている値への参照を返す、`CAtlMap`オブジェクトです。  
  
##  <a name="inithashtable"></a>格納します。  
 このメソッドでは、ハッシュ テーブルを初期化します。  
  
```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBins`  
 ハッシュ テーブルで使用されるビンの数。 参照してください[CAtlMap::CAtlMap](#catlmap)説明します。  
  
 `bAllocNow`  
 メモリを割り当てる必要がある場合にフラグの兆候。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**初期化が成功する、 **false**失敗します。  
  
### <a name="remarks"></a>コメント  
 `InitHashTable`すべての要素がハッシュ テーブルに保存される前に呼び出す必要があります。  このメソッドが明示的に呼び出されない場合に自動的に呼び出すを初めてによって指定されたビン数を使用して要素を追加、 **CAtlMap**コンス トラクターです。  指定された新しいビン数を使用して、マップを初期化、それ以外の場合、`nBins`パラメーター。  
  
 場合、`bAllocNow`パラメーターが false では、まず必要になるまで、ハッシュ テーブルに必要なメモリを割り当てられませんが。 マップを使用する場合は、確定されていない場合に役立ちます。 ことができます。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="isempty"></a>CAtlMap::IsEmpty  
 空のマップ オブジェクトをテストするには、このメソッドを呼び出します。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**マップが空である場合**false**それ以外の場合。  
  
##  <a name="kinargtype"></a>CAtlMap::KINARGTYPE  
 キーが入力引数として渡されるときに使用される型。  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CAtlMap::KOUTARGTYPE  
 キーが出力引数として返されるときに使用される型。  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="lookup"></a>CAtlMap::Lookup  
 キーまたは値を検索するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素を識別するキーを指定します。  
  
 *value*  
 検索された値を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 メソッドの最初の形式は、キーが見つかった場合は true を返します。 2 番目と&3; 番目のフォームへのポインターを返す、 [CPair](#cpair_class)する呼び出しのために位置として使用できる[で](#getnext)にします。  
  
### <a name="remarks"></a>コメント  
 `Lookup`ハッシュ アルゴリズムを使用して、指定されたキー パラメーターを正確に一致するキーを含むマップの要素を簡単に検索します。  
  
##  <a name="operator_at"></a>CAtlMap::operator\[\]  
 置換したり、新しい要素を追加したり、`CAtlMap`です。  
  
```
V& operator[](kinargtype key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 追加または置換する要素のキー。  
  
### <a name="return-value"></a>戻り値  
 指定したキーに関連付けられている値への参照を返します。  
  
### <a name="example"></a>例  
 キーが既に存在する場合は、要素が置き換えられます。 キーが存在しない場合は、新しい要素が追加されます。 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="rehash"></a>CAtlMap::Rehash  
 Rehash にこのメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
void Rehash(UINT nBins = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBins`  
 ハッシュ テーブルで使用する新しいビン数します。 参照してください[CAtlMap::CAtlMap](#catlmap)説明します。  
  
### <a name="remarks"></a>コメント  
 場合`nBins`は 0、`CAtlMap`マップおよび最適な読み込み設定内の要素の数に基づいて適切な数を計算します。 Rehashing プロセスは自動に通常場合に、 [CAtlMap::DisableAutoRehash](#disableautorehash)が呼び出されると、このメソッドが実行するために必要なサイズを変更します。  
  
##  <a name="removeall"></a>CAtlMap::RemoveAll  
 すべての要素を削除するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 クリアして、`CAtlMap`オブジェクトの要素を格納するために使用するメモリを解放します。  
  
##  <a name="removeatpos"></a>CAtlMap::RemoveAtPos  
 指定された位置に要素を削除するには、このメソッドを呼び出す、`CAtlMap`オブジェクトです。  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
### <a name="remarks"></a>コメント  
 指定した位置に格納されているキー/値ペアを削除します。 要素の格納に使用されるメモリは解放されます。 によって参照される位置`pos`、無効になり、マップ内の他の要素の位置が有効ですが、必ずしもそれらの間は、同じ順序を保持します。  
  
##  <a name="removekey"></a>CAtlMap::RemoveKey  
 要素を削除するには、このメソッドを呼び出して、`CAtlMap`キーが指定されたオブジェクト。  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 削除する要素のペアに対応するキー。  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**キーが検出され削除されると、 **false**失敗します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlMap::CAtlMap](#catlmap)します。  
  
##  <a name="setat"></a>CAtlMap::SetAt  
 要素のペアをマップに挿入するには、このメソッドを呼び出します。  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 追加するキー値、`CAtlMap`オブジェクトです。  
  
 *value*  
 追加する値、`CAtlMap`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 キー/値要素のペアの位置を返す、`CAtlMap`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `SetAt`一致するキーが見つかった場合は、既存の要素を置換します。 キーが見つからない場合は、新しいキー/値ペアが作成されます。  
  
##  <a name="setoptimalload"></a>CAtlMap::SetOptimalLoad  
 最適なロードを設定するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```  
  
### <a name="parameters"></a>パラメーター  
 `fOptimalLoad`  
 最適な読み込みの比率です。  
  
 `fLoThreshold`  
 負荷率の下限のしきい値。  
  
 `fHiThreshold`  
 負荷率の上限のしきい値。  
  
 `bRehashNow`  
 ハッシュ テーブルを再計算する場合を示すフラグします。  
  
### <a name="remarks"></a>コメント  
 このメソッドの最適な読み込みの値を再定義、`CAtlMap`オブジェクトです。 参照してください[CAtlMap::CAtlMap](#catlmap)については、さまざまなパラメーターです。 場合`bRehashNow`が true の場合、要素の数が最小値と最大値の範囲外、ハッシュ テーブルを再計算します。  
  
##  <a name="setvalueat"></a>CAtlMap::SetValueAt  
 内の指定位置に格納された値を変更するには、このメソッドを呼び出して、`CAtlMap`オブジェクトです。  
  
```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 以前の呼び出しによって返される位置カウンター [CAtlMap::GetNextAssoc](#getnextassoc)または[CAtlMap::GetStartPosition](#getstartposition)します。  
  
 *value*  
 追加する値、`CAtlMap`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 指定された位置に格納されている値を変更、`CAtlMap`オブジェクトです。  
  
##  <a name="vinargtype"></a>CAtlMap::VINARGTYPE  
 値が入力引数として渡されるときに使用される型。  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CAtlMap::VOUTARGTYPE  
 値が出力引数として渡されるときに使用される型。  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="m_key"></a>CAtlMap::CPair::m_key  
 キーの要素を格納するデータ メンバーです。  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>パラメーター  
 `K`  
 キーの要素の型。  
  
##  <a name="m_value"></a>CAtlMap::CPair::m_value  
 値の要素を格納するデータ メンバーです。  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>パラメーター  
 *V*  
 値の要素型。  
  
## <a name="see-also"></a>関連項目  
 [マーキーのサンプル](../../visual-cpp-samples.md)   
 [UpdatePV サンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

