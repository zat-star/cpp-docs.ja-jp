---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- collection classes, string mapping
- CMapStringToOb class
- strings [C++], class for mapping
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
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
ms.openlocfilehash: 2bfd277ebc1f00784d8e3d9686623777cb7fb5a5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmapstringtoob-class"></a>関数のクラス
一意の `CString` オブジェクトを `CObject` へのポインターに割り当てる辞書コレクション クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|このマップ内の要素の数を返します。|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|現在のハッシュ テーブル内の要素数を決定します。|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CMapStringToOb::GetSize](#getsize)|このマップ内の要素の数を返します。|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|最初の要素の位置を返します。|  
|[CMapStringToOb::HashKey](#hashkey)|指定したキーのハッシュ値を計算します。|  
|[CMapStringToOb::InitHashTable](#inithashtable)|ハッシュ テーブルを初期化します。|  
|[CMapStringToOb::IsEmpty](#isempty)|マップが空の状態 (要素がない) をテストします。|  
|[CMapStringToOb::Lookup](#lookup)|Void ポインターのキーに基づく void ポインターを検索します。 エンティティではなく、ポインター値は、キーの比較に使用されます。|  
|[CMapStringToOb::LookupKey](#lookupkey)|指定したキー値に関連付けられているキーへの参照を返します。|  
|[CMapStringToOb::RemoveAll](#removeall)|このマップからすべての要素を削除します。|  
|[CMapStringToOb::RemoveKey](#removekey)|キーによって指定される要素を削除します。|  
|[CMapStringToOb::SetAt](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMapStringToOb::operator](#operator_at)|マップに要素を挿入などの演算子の代替`SetAt`します。|  
  
## <a name="remarks"></a>コメント  
 挿入すると、 `CString` -  `CObject*`ペア (要素) map に効率的に取得したり、文字列を使用してペアを削除または`CString`キーと値。 マップ内のすべての要素を繰り返すこともできます。  
  
 型の変数**位置**のすべての種類のマップに別のエントリのアクセスに使用します。 使用することができます、**位置**「ください」などのエントリと、マップを反復処理します。 このイテレーションがキーの値がシーケンシャルであると思われるかもしれませんそうじゃないです。 取得する要素の順序は予測できません。  
  
 `CMapStringToOb` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 各要素がシリアル化されるさらに、マップが、オーバー ロードされた出力ストリームのアーカイブに格納されている場合 ( ** << **) 演算子、または、`Serialize`メンバー関数。  
  
 マップ内の個々 の要素の診断用のダンプが必要なかどうか (、`CString`値、および`CObject`内容)、ダンプ コンテキストの深さは 1 以上を設定する必要があります。  
  
 ときに、`CMapStringToOb`オブジェクトを削除すると、またはその要素が削除されたとき、`CString`オブジェクトおよび`CObject`ポインターが削除されます。 によって参照されるオブジェクト、`CObject`ポインターは破棄されません。  
  
 マップ クラスの派生は、リストの派生に似ています。 記事を参照して[コレクション](../../mfc/collections.md)図解専用のリストのクラスから派生します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="cmapstringtoob"></a>CMapStringToOb::CMapStringToOb  
 空の構築`CString`対`CObject*`マップします。  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 マップを拡張するためのメモリ割り当ての粒度を指定します。  
  
### <a name="remarks"></a>コメント  
 単位でメモリが割り当てられた、マップするにつれて、`nBlockSize`エントリです。  
  
 次の表はその他のメンバー関数に類似する**関数:: 関数**します。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10)。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10)。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10)。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**メンバー (INT_PTR** `nBlockSize` **= 10)。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10)。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10)。**|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&63;](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
##  <a name="getcount"></a>CMapStringToOb::GetCount  
 マップの要素の数が決まります。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このマップ内の要素の数。  
  
### <a name="remarks"></a>コメント  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::GetCount`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; INT_PTR GetCount)**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; INT_PTR GetCount)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&64;](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize  
 現在のハッシュ テーブル内の要素数を決定します。  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハッシュ テーブル内の要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::GetHashTableSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () の定数です。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () の定数です。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () の定数です。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () の定数です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () の定数です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () の定数です。**|  
  
##  <a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc  
 位置にあるマップ要素を取得*rNextPosition*、し、更新*rNextPosition*に、マップ内の次の要素を参照してください。  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *rNextPosition*  
 参照を指定、**位置**以前から返される値**たどる**または**中**呼び出します。  
  
 *rKey*  
 取得した要素 (文字列) の返されたキーを指定します。  
  
 *右辺値*  
 取得した要素の戻り値を指定します (、 **CObject**ポインター)。 このパラメーターの詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 この関数は、マップ内のすべての要素を反復処理する方が適しています。 位置シーケンスがないとは限りませんと同じキー値のシーケンスに注意してください。  
  
 取得した要素が、マップ内の最後の新しい値の*rNextPosition*に設定されている**NULL**します。  
  
 *右辺値*パラメーターに、オブジェクト型をキャストすることを確認する**CObject\*&**、これは、コンパイラは次の例で示すように。  
  
 [!code-cpp[NVC_MFCCollections #&65;](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 これには当てはまりません**たどる**テンプレートを基にマップします。  
  
 次の表はその他のメンバー関数に類似する**CMapStringToOb::GetNextAssoc**します。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, void\*&** *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\*&** *rKey* **, WORD&** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**たどるを無効にする (位置 >/documents/report1.rdl」の** *rNextPosition* **、CString >/documents/report1.rdl」の** *rKey* **, void\* & ** *右辺値* **) const です。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**たどるを無効にする (位置 >/documents/report1.rdl」の** *rNextPosition* **、CString >/documents/report1.rdl」の** *rKey* **、CString >/documents/report1.rdl」の***右辺値* **) const です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**たどるを無効にする (位置 >/documents/report1.rdl」の** *rNextPosition* **、WORD >/documents/report1.rdl」の** *rKey* **、CObject\* & ** *右辺値* **) const です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, WORD&** *rKey* **, void\*&** *rValue* **) const;**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&66;](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="getsize"></a>CMapStringToOb::GetSize  
 マップ要素の数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マップ内のアイテムの数。  
  
### <a name="remarks"></a>コメント  
 マップ内の要素の数を取得するには、このメソッドを呼び出します。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::GetSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; INT_PTR GetSize)**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; INT_PTR GetSize)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&67;](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="getstartposition"></a>CMapStringToOb::GetStartPosition  
 返すことによって、マップの反復処理を開始、**位置**値を渡すことができる、`GetNextAssoc`呼び出します。  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**マップを反復処理するための開始位置を表す値または**NULL**マップが空の場合。  
  
### <a name="remarks"></a>コメント  
 繰り返しシーケンスは予想外のです。したがって、マップの最初の要素""には、特別な意味はありません。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::GetStartPosition`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; 位置中)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; 位置中)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; 位置中)**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**Const; 位置中)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; 位置中)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; 位置中)**|  
  
### <a name="example"></a>例  
 例を参照してください[CMapStringToOb::GetNextAssoc](#getnextassoc)します。  
  
##  <a name="hashkey"></a>CMapStringToOb::HashKey  
 指定したキーのハッシュ値を計算します。  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 ハッシュ値が計算されるキーです。  
  
### <a name="return-value"></a>戻り値  
 キーのハッシュ値  
  
### <a name="remarks"></a>コメント  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::HashKey`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void\* ** `key` **) const です。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void\* ** `key` **) const です。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const です。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const です。**|  
  
##  <a name="inithashtable"></a>CMapStringToOb::InitHashTable  
 ハッシュ テーブルを初期化します。  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hashSize`  
 ハッシュ テーブル内のエントリの数です。  
  
 `bAllocNow`  
 場合**TRUE**初期化時にハッシュ テーブルを割り当てるために必要なときにそれ以外の場合、テーブルが割り当てられます。  
  
### <a name="remarks"></a>コメント  
 最適なパフォーマンスをハッシュ テーブルのサイズは、素数をする必要があります。 競合を最小限に抑えるため、サイズする必要があります約 20% が予想される最大のデータ セットよりも大きいです。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::InitHashTable`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**InitHashTable を無効にする (UINT** `hashSize` **、BOOL** `bAllocNow` **= TRUE)。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**InitHashTable を無効にする (UINT** `hashSize` **、BOOL** `bAllocNow` **= TRUE)。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**InitHashTable を無効にする (UINT** `hashSize` **、BOOL** `bAllocNow` **= TRUE)。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**InitHashTable を無効にする (UINT** `hashSize` **、BOOL** `bAllocNow` **= TRUE)。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**InitHashTable を無効にする (UINT** `hashSize` **、BOOL** `bAllocNow` **= TRUE)。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**InitHashTable を無効にする (UINT** `hashSize` **、BOOL** `bAllocNow` **= TRUE)。**|  
  
##  <a name="isempty"></a>CMapStringToOb::IsEmpty  
 マップが空かどうかを決定します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このマップに要素が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 例を参照してください[RemoveAll](#removeall)します。  
  
### <a name="remarks"></a>コメント  
 次の表はその他のメンバー関数に類似する**関数:: IsEmpty**します。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; BOOL IsEmpty)**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; BOOL IsEmpty)**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; BOOL IsEmpty)**|  
  
##  <a name="lookup"></a>CMapStringToOb::Lookup  
 返します。、`CObject`ポインターがに基づいて、`CString`値。  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素を識別する文字列キーを指定します。  
  
 `rValue`  
 検索された要素から返された値を指定します。  
  
### <a name="return-value"></a>戻り値  
 要素が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `Lookup`ハッシュ アルゴリズムを使用してすばやく正確に一致するキーを使用してマップの要素を検索 (`CString`値)。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::LookUp`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL Lookup( void\*** `key` **, void\*&** `rValue` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL Lookup( void\*** `key` **, WORD&** `rValue` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL Lookup( LPCTSTR** `key` **, void\*&** `rValue` **) const;**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**BOOL ルックアップ (LPCTSTR** `key` **、CString >/documents/report1.rdl」の** `rValue` **) const です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL Lookup( WORD** `key` **, CObject\*&** `rValue` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL Lookup( WORD** `key` **, void\*&** `rValue` **) const;**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&68;](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="lookupkey"></a>CMapStringToOb::LookupKey  
 指定したキー値に関連付けられているキーへの参照を返します。  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 検索する要素を識別する文字列キーを指定します。  
  
 `rKey`  
 関連付けられているキーへの参照。  
  
### <a name="return-value"></a>戻り値  
 キーが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 または、マップが破棄された後に関連付けられている要素は、マップから削除された後に使用する場合は、キーへの参照を使用しても安全です。  
  
 次の表はその他のメンバー関数に類似する**関数:: LookupKey**します。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **、LPCTSTR >/documents/report1.rdl」の** `rKey` **) const です。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **、LPCTSTR >/documents/report1.rdl」の** `rKey` **) const です。**|  
  
##  <a name="operator_at"></a>CMapStringToOb::operator  
 便利な代用、`SetAt`メンバー関数。  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>戻り値  
 ポインターへの参照を`CObject`オブジェクトまたは**NULL**マップが空の場合、または`key`が範囲外です。  
  
### <a name="remarks"></a>コメント  
 したがって、代入ステートメント (左辺値) の左側にのみ使用できます。 指定したキーにマップ要素が存在しない、新しい要素が作成されます。  
  
 ない「右側」(右辺値) にこの演算子と同じキーがマップに含まれていない可能性があります可能性があるため。 使用して、`Lookup`メンバー関数要素を取得します。  
  
 次の表はその他のメンバー関数に類似する**CMapStringToOb::operator:operator[]**します。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void\*& operator[](void\*** `key` **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD& operator[](void\*** `key` **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& operator[](lpctstr** `key` **\);**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**CString < 演算子 (lpctstr** `key` **\)です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& operator[](word** `key` **\);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& operator[](word** `key` **\);**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&72;](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="removeall"></a>CMapStringToOb::RemoveAll  
 このマップからすべての要素を削除し、破棄、 `CString` key オブジェクトです。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 `CObject`各キーによって参照されるオブジェクトは破棄されません。 `RemoveAll`はないことを確認する、参照されている場合、関数はメモリ リークに可能性`CObject`オブジェクトが破棄されます。  
  
 関数は、マップが既に空の場合、正常に動作します。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::RemoveAll`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**RemoveAll (); を無効にします。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**RemoveAll (); を無効にします。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**RemoveAll (); を無効にします。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**RemoveAll (); を無効にします。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**RemoveAll (); を無効にします。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**RemoveAll (); を無効にします。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&69;](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="removekey"></a>CMapStringToOb::RemoveKey  
 指定されたキーに対応するマップ エントリを検索します。次に、キーが見つかった場合は、エントリを削除します。  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 マップの検索に使用する文字列を指定します。  
  
### <a name="return-value"></a>戻り値  
 エントリが見つかり、正常に削除された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メモリ リークが発生する場合はこれ、`CObject`オブジェクトは別の場所に削除されません。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::RemoveKey`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**ブール値には (void\* ** `key` **) です。**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**ブール値には (void\* ** `key` **) です。**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**ブール値には (LPCTSTR** `key` **) です。**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**ブール値には (LPCTSTR** `key` **) です。**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**ブール値には (WORD** `key` **) です。**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**ブール値には (WORD** `key` **) です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&70;](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="setat"></a>CMapStringToOb::SetAt  
 プライマリは、マップ内の要素を挿入することです。  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `key`  
 新しい要素のキーである文字列を指定します。  
  
 `newValue`  
 指定、`CObject`新しい要素の値であるポインターです。  
  
### <a name="remarks"></a>コメント  
 最初に、キーが検索されます。 キーが見つかった場合、対応する値を変更します。それ以外の場合、新しいキーと値の要素が作成されます。  
  
 次の表はその他のメンバー関数に類似する`CMapStringToOb::SetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt( void\*** `key` **, void\*** `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt( void\*** `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt( LPCTSTR** `key` **, void\*** `newValue` **);**|  
|[メンバー](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt( WORD** `key` **, CObject\*** `newValue` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt( WORD** `key` **, void\*** `newValue` **);**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&71;](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr クラス](../../mfc/reference/cmapstringtoptr-class.md)   
 [メンバー クラス](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb クラス](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)

