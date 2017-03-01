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
- CMapStringToString
dev_langs:
- C++
helpviewer_keywords:
- collection classes, string mapping
- strings [C++], mapping
- strings [C++], class for mapping
- CMapStringToString class
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
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
ms.openlocfilehash: 58ca2023d57c2865dadc8dfab304aab2fa39a96b
ms.lasthandoff: 02/24/2017

---
# <a name="cmapstringtostring-class"></a>メンバー クラス
`CString` オブジェクトをキーとした `CString` オブジェクトのマップをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CMapStringToString`クラスのメンバー関数に似ています[関数](../../mfc/reference/cmapstringtoob-class.md)します。 メンバー関数については `CMapStringToOb` クラスの説明を参照してください。 表示されたら、`CObject`ポインターと戻り値または「出力」関数のパラメーターを置き換えるへのポインター`char`します。 表示されたら、 `CObject` 、"input"の関数のパラメーターとしてのポインターへのポインターに置き換える`char`します。  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 たとえば、次のように変換します。  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>パブリック構造体  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|キーの値と関連付けられている文字列オブジェクトの値を含む入れ子になった構造体。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|このマップ内の要素の数を返します。|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|現在のハッシュ テーブル内の要素数を決定します。|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|このマップ内の要素の数を返します。|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|最初の要素の位置を返します。|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|指定したキーのハッシュ値を計算します。|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|ハッシュ テーブルを初期化します。|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|マップが空の状態 (要素がない) をテストします。|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void ポインターのキーに基づく void ポインターを検索します。 エンティティではなく、ポインター値は、キーの比較に使用されます。|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|指定したキー値に関連付けられているキーへの参照を返します。|  
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|最初のポインターを取得`CString`にマップします。|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|ポインターを取得`CString`の反復処理します。|  
|[CMapStringToString::PLookup](#plookup)|ポインターを返す、`CString`値が指定の値に一致します。|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|このマップからすべての要素を削除します。|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|キーによって指定される要素を削除します。|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::operator](../../mfc/reference/cmapstringtoob-class.md#operator_at)|マップに要素を挿入などの演算子の代替`SetAt`します。|  
  
## <a name="remarks"></a>コメント  
 `CMapStringToString` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 各要素がシリアル化されるさらに、マップが、オーバー ロードされた出力ストリームのアーカイブに格納されている場合 ( ** << **) 演算子、または、`Serialize`メンバー関数。  
  
 個別にダンプする必要がある場合`CString` -  `CString`要素を 1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ときに、`CMapStringToString`オブジェクトを削除すると、またはその要素が削除されたとき、`CString`オブジェクトは、必要に応じて削除されます。  
  
 詳細については`CMapStringToString`、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="a-namecpaira--cmapstringtostringcpair"></a><a name="cpair"></a>CMapStringToString::CPair  
 キーの値と関連付けられている文字列オブジェクトの値が含まれています。  
  
### <a name="remarks"></a>コメント  
 次に、クラス内で入れ子になった構造[メンバー](../../mfc/reference/cmapstringtostring-class.md)します。  
  
 構造体は、2 つのフィールドで構成されます。  
  
- **キー**キーの種類の実際の値。  
  
- **値**関連付けられているオブジェクトの値。  
  
 戻り値の格納に使用される、 [CMapStringToString::PLookup](#plookup)、 [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)、および[CMapStringToString::PGetNextAssoc](#pgetnextassoc)します。  
  
### <a name="example"></a>例  
  使用状況の例は、の使用例を参照してください。 [CMapStringToString::PLookup](#plookup)します。  
  
##  <a name="a-namepgetfirstassoca--cmapstringtostringpgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMapStringToString::PGetFirstAssoc  
 マップ オブジェクトの最初のエントリを返します。  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>戻り値  
 マップ内の最初のエントリへのポインター参照してください[CMapStringToString::CPair](#cpair)します。 マップが空の場合、値は、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 この関数では、マップ オブジェクト内の最初の要素のポインターを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&73;](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="a-namepgetnextassoca--cmapstringtostringpgetnextassoc"></a><a name="pgetnextassoc"></a>CMapStringToString::PGetNextAssoc  
 指すに基づいてマップ要素を取得`pAssocRec`します。  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pAssoc*  
 直前のマップ エントリが指す[PGetNextAssoc](#pgetnextassoc)または[PGetFirstAssoc](#pgetfirstassoc)呼び出します。  
  
### <a name="return-value"></a>戻り値  
 マップ内の次のエントリへのポインター参照してください[CMapStringToString::CPair](#cpair)します。 値は、要素がマップ内の最後の場合は、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 マップ内のすべての要素を反復処理するには、このメソッドを呼び出します。 呼び出しの最初の要素を取得`PGetFirstAssoc`を連続する呼び出すと、マップを反復処理し、`PGetNextAssoc`です。  
  
### <a name="example"></a>例  
  例を参照してください[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)します。  
  
##  <a name="a-nameplookupa--cmapstringtostringplookup"></a><a name="plookup"></a>CMapStringToString::PLookup  
 指定されたキーにマップされている値を検索します。  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素のキーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたキーへのポインター。  
  
### <a name="remarks"></a>コメント  
 マップ要素の指定したキーを完全に一致するキーを検索するには、このメソッドを呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&74;](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




