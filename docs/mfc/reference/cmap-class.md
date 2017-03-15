---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMap
dev_langs:
- C++
helpviewer_keywords:
- dictionary mapping class
- collection classes, dictionary mapping
- CMap class
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
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
ms.openlocfilehash: 680d44fe6154861d2c638697cfc9d3fbeab36cc4
ms.lasthandoff: 02/24/2017

---
# <a name="cmap-class"></a>メンバー クラス
一意なキーを値に割り当てる辞書コレクション クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>パラメーター  
 `KEY`  
 マップのキーとして使用されるオブジェクトのクラスです。  
  
 `ARG` *_* `KEY`  
 データ型`KEY`引数; 通常への参照を`KEY`します。  
  
 `VALUE`  
 マップに格納されているオブジェクトのクラスです。  
  
 `ARG` *_* `VALUE`  
 データ型`VALUE`引数; 通常への参照を`VALUE`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-structures"></a>パブリック構造体  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|キーの値と関連付けられたオブジェクトの値を含む入れ子になった構造体。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|キーの値を割り当てるコレクションを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|このマップ内の要素の数を返します。|  
|[CMap::GetHashTableSize](#gethashtablesize)|ハッシュ テーブル内の要素の数を返します。|  
|[CMap::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CMap::GetSize](#getsize)|このマップ内の要素の数を返します。|  
|[CMap::GetStartPosition](#getstartposition)|最初の要素の位置を返します。|  
|[CMap::InitHashTable](#inithashtable)|ハッシュ テーブルを初期化し、そのサイズを指定します。|  
|[CMap::IsEmpty](#isempty)|マップが空の状態 (要素がない) をテストします。|  
|[CMap::Lookup](#lookup)|指定されたキーにマップされている値を検索します。|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|最初の要素へのポインターを返します。|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|反復処理するための次の要素へのポインターを取得します。|  
|[例](#plookup)|値が指定の値に一致するキーへのポインターを返します。|  
|[CMap::RemoveAll](#removeall)|このマップからすべての要素を削除します。|  
|[CMap::RemoveKey](#removekey)|キーによって指定される要素を削除します。|  
|[CMap::SetAt](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMap::operator](#operator_at)|マップ â € に要素を挿入"を`SetAt`します。|  
  
## <a name="remarks"></a>コメント  
 マップにキー/値ペア (要素) を挿入すると効率的に取得かへのアクセス キーを使用してペアを削除することができます。 マップ内のすべての要素を繰り返すこともできます。  
  
 型の変数**位置**エントリに代替のアクセスに使用します。 使用することができます、**位置**「ください」などのエントリと、マップを反復処理します。 このイテレーションがキーの値がシーケンシャルであると思われるかもしれませんそうじゃないです。 取得する要素の順序は予測できません。  
  
 ほとんどの用途のグローバル ヘルパー関数をこのクラスの呼び出しの一部のメンバー関数をカスタマイズする必要があります、`CMap`クラスです。 参照してください[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)のマクロとグローバルのセクションで、`MFC``Reference`です。  
  
 `CMap`上書き[指定](../../mfc/reference/cobject-class.md#serialize)シリアル化とその要素のダンプがサポートされます。 マップを使用して、アーカイブに格納されている場合`Serialize`、各マップ要素が順にシリアル化します。 既定の実装、`SerializeElements`ヘルパー関数ではビットごとの書き込みです。 派生したポインター コレクション項目のシリアル化に関する情報の`CObject`またはその他のユーザー定義型を参照してください[方法: タイプ セーフなコレクションを作成する](../../mfc/how-to-make-a-type-safe-collection.md)です。  
  
 (キーと値) のマップ内の個々 の要素の診断用のダンプを実行する場合に、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ときに、`CMap`オブジェクトが削除されると、またはその要素が削除された場合、キーと値の両方が削除されます。  
  
 マップ クラスの派生は、リストの派生に似ています。 記事を参照して[コレクション](../../mfc/collections.md)図解専用のリストのクラスから派生します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="a-namecmapa--cmapcmap"></a><a name="cmap"></a>CMap::CMap  
 空のマップを構築します。  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 マップを拡張するためのメモリ割り当ての粒度を指定します。  
  
### <a name="remarks"></a>コメント  
 単位でメモリが割り当てられた、マップするにつれて、`nBlockSize`エントリです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&56;](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="a-namecpaira--cmapcpair"></a><a name="cpair"></a>CMap::CPair  
 キーの値と関連付けられているオブジェクトの値が含まれています。  
  
### <a name="remarks"></a>コメント  
 次に、クラス内で入れ子になった構造[メンバー](../../mfc/reference/cmap-class.md)します。  
  
 構造体は、2 つのフィールドで構成されます。  
  
- **--keyÂ**キーの種類の実際の値。  
  
- **--valueÂ**関連するオブジェクトの値。  
  
 戻り値の格納に使用される、[例](#plookup)、 [CMap::PGetFirstAssoc](#pgetfirstassoc)、および[CMap::PGetNextAssoc](#pgetnextassoc)します。  
  
### <a name="example"></a>例  
 使用状況の例は、の使用例を参照してください。[例](#plookup)します。  
  
##  <a name="a-namegetcounta--cmapgetcount"></a><a name="getcount"></a>CMap::GetCount  
 マップ内の要素の数を取得します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要素の数。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::Lookup](#lookup)します。  
  
##  <a name="a-namegethashtablesizea--cmapgethashtablesize"></a><a name="gethashtablesize"></a>CMap::GetHashTableSize  
 マップのハッシュ テーブル内の要素の数が決まります。  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハッシュ テーブル内の要素の数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&57;](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="a-namegetnextassoca--cmapgetnextassoc"></a><a name="getnextassoc"></a>CMap::GetNextAssoc  
 位置にあるマップ要素を取得`rNextPosition`、し、更新`rNextPosition`に、マップ内の次の要素を参照してください。  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rNextPosition`  
 参照を指定、**位置**以前から返される値`GetNextAssoc`または`GetStartPosition`呼び出します。  
  
 *キー*  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 `rKey`  
 取得した要素の返されたキーを指定します。  
  
 *値*  
 マップの値の型を指定するテンプレート パラメーター。  
  
 `rValue`  
 取得した要素の戻り値を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、マップ内のすべての要素を反復処理する方が適しています。 位置シーケンスがないとは限りませんと同じキー値のシーケンスに注意してください。  
  
 取得した要素が、マップ内の最後の新しい値の`rNextPosition`に設定されている**NULL**します。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::SetAt](#setat)します。  
  
##  <a name="a-namegetsizea--cmapgetsize"></a><a name="getsize"></a>CMap::GetSize  
 マップ要素の数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内のアイテムの数。  
  
### <a name="remarks"></a>コメント  
 マップ内の要素の数を取得するには、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="a-namegetstartpositiona--cmapgetstartposition"></a><a name="getstartposition"></a>CMap::GetStartPosition  
 返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、`GetNextAssoc`呼び出します。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**マップを反復処理するための開始位置を表す値または**NULL**マップが空の場合。  
  
### <a name="remarks"></a>コメント  
 繰り返しシーケンスは予想外のです。したがって、マップの最初の要素""には、特別な意味はありません。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::SetAt](#setat)します。  
  
##  <a name="a-nameinithashtablea--cmapinithashtable"></a><a name="inithashtable"></a>CMap::InitHashTable  
 ハッシュ テーブルを初期化します。  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUEÂ);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hashSize`  
 ハッシュ テーブル内のエントリの数です。  
  
 `bAllocNow`  
 場合**TRUE**初期化時にハッシュ テーブルを割り当てるために必要なときにそれ以外の場合、テーブルが割り当てられます。  
  
### <a name="remarks"></a>コメント  
 最適なパフォーマンスをハッシュ テーブルのサイズは、素数をする必要があります。 競合を最小限に抑えるため、サイズする必要があります約 20% が予想される最大のデータ セットよりも大きいです。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::Lookup](#lookup)します。  
  
##  <a name="a-nameisemptya--cmapisempty"></a><a name="isempty"></a>CMap::IsEmpty  
 マップが空かどうかを決定します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このマップに要素が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::RemoveAll](#removeall)します。  
  
##  <a name="a-namelookupa--cmaplookup"></a><a name="lookup"></a>CMap::Lookup  
 指定されたキーにマップされている値を検索します。  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_KEY`  
 テンプレート パラメーターの型を指定する、`key`値。  
  
 `key`  
 検索する要素を識別するキーを指定します。  
  
 *値*  
 検索する値の型を指定します。  
  
 `rValue`  
 検索された値を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 要素が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `Lookup`ハッシュ アルゴリズムを使用して、指定したキーを完全に一致するキーを使用してマップの要素をすばやく検索します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&58;](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="a-nameoperatorata--cmapoperator--"></a><a name="operator_at"></a>CMap::operator  
 便利な代用、`SetAt`メンバー関数。  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>パラメーター  
 *値*  
 マップ値の型を指定するテンプレート パラメーター。  
  
 `ARG_KEY`  
 キーの値の型を指定するテンプレート パラメーター。  
  
 `key`  
 マップの値を取得するために使用するキー。  
  
### <a name="remarks"></a>コメント  
 したがって、代入ステートメント (左辺値) の左側にのみ使用できます。 指定したキーにマップ要素が存在しない、新しい要素が作成されます。  
  
 ない「右側」(右辺値) にこの演算子と同じキーがマップに含まれていない可能性があります可能性があるため。 使用して、`Lookup`メンバー関数要素を取得します。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::Lookup](#lookup)します。  
  
##  <a name="a-namepgetfirstassoca--cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 マップ オブジェクトの最初のエントリを返します。  
  
```  
const CPair* PGetFirstAssoc() const;Â CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内の最初のエントリへのポインター参照してください[CMap::CPair](#cpair)します。 マップにエントリが含まれていない場合、値は**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この関数では、マップ オブジェクト内の最初の要素のポインターを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&59;](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="a-namepgetnextassoca--cmappgetnextassoc"></a><a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 指すに基づいてマップ要素を取得`pAssocRec`します。  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>パラメーター  
 *pAssocRet*  
 直前のマップ エントリが指す[PGetNextAssoc](#pgetnextassoc)または[CMap::PGetFirstAssoc](#pgetfirstassoc)呼び出します。  
  
### <a name="return-value"></a>戻り値  
 マップ内の次のエントリへのポインター参照してください[CMap::CPair](#cpair)します。 値は、要素がマップ内の最後の場合は、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 マップ内のすべての要素を反復処理するには、このメソッドを呼び出します。 呼び出しの最初の要素を取得`PGetFirstAssoc`を連続する呼び出すと、マップを反復処理し、`PGetNextAssoc`です。  
  
### <a name="example"></a>例  
 例を参照してください[CMap::PGetFirstAssoc](#pgetfirstassoc)します。  
  
##  <a name="a-nameplookupa--cmapplookup"></a><a name="plookup"></a>例  
 指定されたキーにマップされている値を検索します。  
  
```  
const CPair* PLookup(ARG_KEY  key) const;
CPair* PLookup(Â    ARG_KEY  keyÂ);  ```  
  
### Parameters  
 `key`  
 Key for the element to be searched for.  
  
### Return Value  
 A pointer to a key structure; see [CMap::CPair](#cpair). If no match is found, `CMap::PLookup` returns `NULL`.  
  
### Remarks  
 Call this method to search for a map element with a key that exactly matches the given key.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>  CMap::RemoveAll  
 Removes all the values from this map by calling the global helper function **DestructElements**.  
  
```  
RemoveAll(); を無効にします。
```  
  
### Remarks  
 The function works correctly if the map is already empty.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>  CMap::RemoveKey  
 Looks up the map entry corresponding to the supplied key; then, if the key is found, removes the entry.  
  
```  
BOOL RemoveKey(ARG_KEY key) です。
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the key.  
  
 `key`  
 Key for the element to be removed.  
  
### Return Value  
 Nonzero if the entry was found and successfully removed; otherwise 0.  
  
### Remarks  
 The **DestructElements** helper function is used to remove the entry.  
  
### Example  
 See the example for [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>  CMap::SetAt  
 The primary means to insert an element in a map.  
  
```  
SetAt (ARG_KEY キー、ARG_VALUE newValue); を無効にします。
```  
  
### Parameters  
 `ARG_KEY`  
 Template parameter specifying the type of the `key` parameter.  
  
 `key`  
 Specifies the key of the new element.  
  
 `ARG_VALUE`  
 Template parameter specifying the type of the `newValue` parameter.  
  
 `newValue`  
 Specifies the value of the new element.  
  
### Remarks  
 First, the key is looked up. If the key is found, then the corresponding value is changed; otherwise a new key-value pair is created.  
  
### Example  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## See Also  
 [MFC Sample COLLECT](../../visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)  

