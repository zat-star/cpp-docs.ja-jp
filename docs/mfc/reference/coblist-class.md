---
title: "CObList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObList
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], lists of
- CObList class
- lists, object
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: dc95f76be56f00f4779724facaf668a72b3d5ed6
ms.lasthandoff: 02/24/2017

---
# <a name="coblist-class"></a>CObList クラス
一意でない場合の順序付きリスト fSupports`CObject`ポインターにアクセス可能な順番にも、ポインター値です。  
  
## <a name="syntax"></a>構文  
  
```  
class CObList : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[使われて](#coblist)|空のリストを構築`CObject`ポインター。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObList::AddHead](#addhead)|(新しいヘッドによって作成) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::AddTail](#addtail)|(新しい末尾によって作成) リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::Find](#find)|ポインター値によって指定される要素の位置を取得します。|  
|[CObList::FindIndex](#findindex)|0 から始まるインデックスで指定された要素の位置を取得します。|  
|[CObList::GetAt](#getat)|指定された位置に要素を取得します。|  
|[CObList::GetCount](#getcount)|この一覧には、要素の数を返します。|  
|[CObList::GetHead](#gethead)|(空にすることはできません) の一覧の先頭の要素を返します。|  
|[CObList::GetHeadPosition](#getheadposition)|リストの先頭の要素の位置を返します。|  
|[CObList::GetNext](#getnext)|反復処理するためには、次の要素を取得します。|  
|[CObList::GetPrev](#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CObList::GetSize](#getsize)|この一覧には、要素の数を返します。|  
|[CObList::GetTail](#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CObList::GetTailPosition](#gettailposition)|リストの末尾の要素の位置を返します。|  
|[CObList::InsertAfter](#insertafter)|指定した位置の後に新しい要素を挿入します。|  
|[CObList::InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|  
|[CObList::IsEmpty](#isempty)|空のリストの状態 (要素がない) をテストします。|  
|[CObList::RemoveAll](#removeall)|この一覧からすべての要素を削除します。|  
|[CObList::RemoveAt](#removeat)|位置によって指定されたこのリストから要素を削除します。|  
|[CObList::RemoveHead](#removehead)|リストの先頭から要素を削除します。|  
|[CObList::RemoveTail](#removetail)|リストの末尾から要素を削除します。|  
|[CObList::SetAt](#setat)|指定された位置に要素を設定します。|  
  
## <a name="remarks"></a>コメント  
 `CObList`リストは、二重リンク リストのように動作します。  
  
 型の変数**位置**リストのキーです。 使用することができます、**位置**順番に、リストを走査する反復子、および位置を保持するためのブックマークとして変数です。 位置は、インデックスと同じしかしです。  
  
 要素の挿入は非常に高速リストの先頭、末尾、および既知**位置**します。 順次検索は、値またはインデックスで要素を検索する必要があります。 この検索は、リストが長い場合は低速にすることはできます。  
  
 `CObList` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 リストの場合`CObject`ポインターがオーバー ロードされた挿入演算子またはでアーカイブに格納されている、`Serialize`のメンバー関数の各`CObject`要素が順にシリアル化します。  
  
 個別にダンプする必要がある場合`CObject`リスト内の要素を 1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ときに、`CObList`オブジェクトを削除すると、またはその要素が削除されたとき、のみ、`CObject`ポインターを削除すると、オブジェクトではなくを参照します。  
  
 独自のクラスを派生する`CObList`です。 派生したオブジェクトへのポインターを保持するために設計された新しいリスト クラス`CObject`、新しいデータ メンバーと新しいメンバー関数を追加します。 いずれかの挿入を許容するために、結果のリストは厳密にタイプ セーフである、注意してください`CObject`ポインター。  
  
> [!NOTE]
>  使用する必要があります、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)一覧をシリアル化する場合は、派生クラスの実装ではマクロです。  
  
 使用する方法について`CObList`、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="a-nameaddheada--coblistaddhead"></a><a name="addhead"></a>CObList::AddHead  
 このリストの先頭に新しい要素または要素のリストを追加します。  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `newElement`  
 `CObject`この一覧に追加するへのポインター。  
  
 `pNewList`  
 別のポインター `CObList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンの取得、**位置**新しく挿入される要素の値。  
  
 次の表はその他のメンバー関数に類似する`CObList::AddHead`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 AddHead (void\* ** `newElement` **) です。**<br /><br /> **AddHead を無効にする (CPtrList\* ** `pNewList` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 AddHead (const CString >/documents/report1.rdl」の** `newElement` **) です。**<br /><br /> **位置 AddHead (LPCTSTR** `newElement` **) です。**<br /><br /> **AddHead を無効にする (CStringList\* ** `pNewList` **) です。**|  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&89;](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="a-nameaddtaila--coblistaddtail"></a><a name="addtail"></a>CObList::AddTail  
 このリストの末尾に新しい要素または要素のリストを追加します。  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `newElement`  
 `CObject`この一覧に追加するへのポインター。  
  
 `pNewList`  
 別のポインター `CObList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンの取得、**位置**新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
 次の表はその他のメンバー関数に類似する`CObList::AddTail`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 AddTail (void\* ** `newElement` **) です。**<br /><br /> **AddTail を無効にする (CPtrList\* ** `pNewList` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 AddTail (const CString >/documents/report1.rdl」の** `newElement` **) です。**<br /><br /> **位置 AddTail (LPCTSTR** `newElement` **) です。**<br /><br /> **AddTail を無効にする (CStringList\* ** `pNewList` **) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&90;](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="a-namecoblista--coblistcoblist"></a><a name="coblist"></a>使われて  
 空の構築`CObject`ポインターのリスト。  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 リストを拡張するメモリ割り当ての粒度。  
  
### <a name="remarks"></a>コメント  
 単位でメモリが割り当てられている一覧するにつれて、`nBlockSize`エントリです。 メモリの割り当てに失敗した場合、`CMemoryException`がスローされます。  
  
 次の表はその他のメンバー関数に類似する`CObList::CObList`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10)。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10)。**|  
  
### <a name="example"></a>例  
  以下の一覧を示します、 `CObject`-派生クラス`CAge`コレクションのすべての例で使用します。  
  
 [!code-cpp[NVC_MFCCollections #&91;](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 以下の例は、`CObList`コンス トラクターの使用状況。  
  
 [!code-cpp[NVC_MFCCollections #&92;](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="a-namefinda--coblistfind"></a><a name="find"></a>CObList::Find  
 最初に順番にリストを検索`CObject`ポインター、指定した照合`CObject`ポインター。  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `searchValue`  
 この一覧で検索するオブジェクトのポインター。  
  
 `startAfter`  
 検索の開始位置。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**オブジェクトが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 ポインター値を比較することに注意してください、オブジェクトの内容ではありません。  
  
 次の表はその他のメンバー関数に類似する`CObList::Find`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置検索 (void\* ** `searchValue` **、位置** `startAfter` **= NULL) const です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置検索 (LPCTSTR** `searchValue` **、位置** `startAfter` **= NULL) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&93;](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="a-namefindindexa--coblistfindindex"></a><a name="findindex"></a>CObList::FindIndex  
 値を使用して`nIndex`としてリストのインデックス。  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 検索するリストの要素の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**場合`nIndex`が大きすぎます。 (フレームワーク場合にアサーションを生成する`nIndex`が負の値です)。  
  
### <a name="remarks"></a>コメント  
 上の停止して、リストの先頭からのシーケンシャルなスキャンを開始、 *n*番目の要素。  
  
 次の表はその他のメンバー関数に類似する`CObList::FindIndex`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 FindIndex (INT_PTR** `nIndex` **) const です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 FindIndex (INT_PTR** `nIndex` **) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&94;](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="a-namegetata--coblistgetat"></a><a name="getat"></a>CObList::GetAt  
 型の変数**位置**リストのキーです。  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 A**位置**以前から返される値`GetHeadPosition`または**検索**メンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照して[gethead 関数](#gethead)します。  
  
### <a name="remarks"></a>コメント  
 操作できません。 したり、インデックスと同じには、**位置**自分の値。 `GetAt`取得、`CObject`指定した位置に関連付けられたポインター。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*>/documents/report1.rdl」の GetAt (位置***位置* **) const です。**<br /><br /> **void\*>/documents/report1.rdl」の GetAt (位置***位置* **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const の CString >/documents/report1.rdl」の GetAt (位置***位置* **) const です。**<br /><br /> **CString >/documents/report1.rdl」の GetAt (位置***位置* **) です。**|  
  
### <a name="example"></a>例  
  例を参照してください[FindIndex](#findindex)します。  
  
##  <a name="a-namegetcounta--coblistgetcount"></a><a name="getcount"></a>CObList::GetCount  
 この一覧内の要素の数を取得します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要素の数を含む整数値。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetCount`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; INT_PTR GetCount)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&95;](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="a-namegetheada--coblistgethead"></a><a name="gethead"></a>CObList::GetHead  
 取得、`CObject`ポインターがこの一覧の先頭の要素を表します。  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>戻り値  
 一覧にはへのポインターを介してアクセスする場合、 **const CObList**、し、`GetHead`返します、`CObject`ポインター。 これは、関数は、代入ステートメントの右側にあるでのみ使用し、したがって、ボックスの一覧を変更から保護します。  
  
 一覧には直接、またはポインターにアクセスする場合、 `CObList`、し、`GetHead`への参照を返す、`CObject`ポインター。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetHead`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetHead`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*>/documents/report1.rdl」の gethead 関数 () const; void\*>/documents/report1.rdl」の gethead 関数 ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const; const の CString >/documents/report1.rdl」の gethead 関数)CString >/documents/report1.rdl」の gethead 関数 ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 次の例では、使用する`GetHead`代入ステートメントの左側にあります。  
  
 [!code-cpp[NVC_MFCCollections #&96;](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="a-namegetheadpositiona--coblistgetheadposition"></a><a name="getheadposition"></a>CObList::GetHeadPosition  
 この一覧の先頭の要素の位置を取得します。  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**リストが空の場合。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetHeadPosition`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; 位置順)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; 位置順)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&97;](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="a-namegetnexta--coblistgetnext"></a><a name="getnext"></a>CObList::GetNext  
 識別される要素を取得`rPosition`、設定し、`rPosition`に、`POSITION`一覧の次のエントリの値。  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、`POSITION`以前から返される値`GetNext`、 `GetHeadPosition`、またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照して[gethead 関数](#gethead)します。  
  
### <a name="remarks"></a>コメント  
 使用する`GetNext`への呼び出しでは、最初の位置を確立する場合は、順方向の反復ループで`GetHeadPosition`または`Find`です。  
  
 確認する必要があります、`POSITION`値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得した要素が値の場合、リスト内の最後の新しいの`rPosition`に設定されている`NULL`します。  
  
 反復処理中に要素を削除することができます。 例を参照してください[RemoveAt](#removeat)します。  
  
> [!NOTE]
>  返すこのメソッドの const バージョンが変更された MFC 8.0 の時点で`const CObject*`の代わりに`const CObject*&`します。  標準の C++ への適合性をコンパイラをさせるために変更されました。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetNext`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&98;](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="a-namegetpreva--coblistgetprev"></a><a name="getprev"></a>CObList::GetPrev  
 識別される要素を取得`rPosition`を設定し、`rPosition`に、`POSITION`一覧の前のエントリの値。  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照、`POSITION`以前から返される値`GetPrev`またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照して[gethead 関数](#gethead)します。  
  
### <a name="remarks"></a>コメント  
 使用する`GetPrev`への呼び出しでは、最初の位置を確立する場合に、逆順イテレーション ループで`GetTailPosition`または`Find`です。  
  
 確認する必要があります、`POSITION`値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 要素を取得した一覧で、最初からの新しい値場合`rPosition`に設定されている`NULL`します。  
  
> [!NOTE]
>  返すこのメソッドの const バージョンが変更された MFC 8.0 の時点で`const CObject*`の代わりに`const CObject*&`します。  標準の C++ への適合性をコンパイラをさせるために変更されました。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetPrev`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections&#99;](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="a-namegetsizea--coblistgetsize"></a><a name="getsize"></a>CObList::GetSize  
 リストの要素数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リストの項目数。  
  
### <a name="remarks"></a>コメント  
 リスト内の要素の数を取得するには、このメソッドを呼び出します。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; INT_PTR GetSize)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections&#100;](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="a-namegettaila--coblistgettail"></a><a name="gettail"></a>CObList::GetTail  
 取得、`CObject`ポインターがこのリストの末尾の要素を表します。  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照して[gethead 関数](#gethead)します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetTail`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetTail`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*>/documents/report1.rdl」の GetTail () const; void\*>/documents/report1.rdl」の GetTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const; const の CString >/documents/report1.rdl」の GetTail)CString >/documents/report1.rdl」の GetTail ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&101;](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="a-namegettailpositiona--coblistgettailposition"></a><a name="gettailposition"></a>CObList::GetTailPosition  
 このリストの末尾の要素の位置を取得します。**NULL**リストが空の場合。  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**リストが空の場合。  
  
 次の表はその他のメンバー関数に類似する`CObList::GetTailPosition`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; 位置 GetTailPosition)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; 位置 GetTailPosition)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&102;](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="a-nameinsertaftera--coblistinsertafter"></a><a name="insertafter"></a>CObList::InsertAfter  
 指定位置にある要素の後にこのリストに要素を追加します。  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。  
  
 次の表はその他のメンバー関数に類似する`CObList::InsertAfter`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 InsertAfter (位置***位置* **, void\* ** `newElement` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 InsertAfter (位置***位置* **、const CString >/documents/report1.rdl」の** `newElement` **) です。**<br /><br /> **位置 InsertAfter (位置***位置* **、LPCTSTR** `newElement` **) です。**|  
  
### <a name="return-value"></a>戻り値  
 A**位置**は同じ値として、*位置*パラメーター。  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&103;](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="a-nameinsertbeforea--coblistinsertbefore"></a><a name="insertbefore"></a>CObList::InsertBefore  
 一覧の指定した位置にある要素の前に要素を追加します。  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**リストが空の場合。  
  
 次の表はその他のメンバー関数に類似する`CObList::InsertBefore`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**位置 InsertBefore (位置***位置* **, void\* ** `newElement` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**位置 InsertBefore (位置***位置* **、const CString >/documents/report1.rdl」の** `newElement` **) です。**<br /><br /> **位置 InsertBefore (位置***位置* **、LPCTSTR** `newElement` **) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&104;](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="a-nameisemptya--coblistisempty"></a><a name="isempty"></a>CObList::IsEmpty  
 このリストに要素が含まれないかどうかを示します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のリストは空です。それ以外の場合 0 を返します。  
  
 次の表はその他のメンバー関数に類似する`CObList::IsEmpty`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Const; BOOL IsEmpty)**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Const; BOOL IsEmpty)**|  
  
### <a name="example"></a>例  
  例を参照してください[RemoveAll](#removeall)します。  
  
##  <a name="a-nameremovealla--coblistremoveall"></a><a name="removeall"></a>CObList::RemoveAll  
 このリストからすべての要素を削除し、関連付けられた解放`CObList`メモリです。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 リストが既に空の場合、エラーは発生しません。  
  
 要素を削除するときに、 `CObList`、一覧からオブジェクトのポインターを削除します。 ユーザーの責任において、オブジェクト自体を削除することをお勧めします。  
  
 次の表はその他のメンバー関数に類似する`CObList::RemoveAll`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**RemoveAll (); を無効にします。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**RemoveAll (); を無効にします。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&105;](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="a-nameremoveata--coblistremoveat"></a><a name="removeat"></a>CObList::RemoveAt  
 この一覧から、指定した要素を削除します。  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 一覧から削除する要素の位置。  
  
### <a name="remarks"></a>コメント  
 要素を削除すると、 `CObList`、一覧からオブジェクトへのポインターを削除します。 ユーザーの責任において、オブジェクト自体を削除することをお勧めします。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に類似する`CObList::RemoveAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**RemoveAt を無効にする (位置***位置* **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**RemoveAt を無効にする (位置***位置* **) です。**|  
  
### <a name="example"></a>例  
  リストの反復処理中に要素を削除する際に注意してください。 次の例では、有効なことを保証する削除手法**位置**の場合は値[GetNext](#getnext)します。  
  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&106;](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="a-nameremoveheada--coblistremovehead"></a><a name="removehead"></a>CObList::RemoveHead  
 リストの先頭から要素を削除し、ポインターを返します。  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>戻り値  
 `CObject`リストの先頭にあったポインター。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveHead`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に類似する`CObList::RemoveHead`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&107;](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="a-nameremovetaila--coblistremovetail"></a><a name="removetail"></a>CObList::RemoveTail  
 リストの末尾から要素を削除し、ポインターを返します。  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>戻り値  
 リストの後部にあったオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveTail`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
 次の表はその他のメンバー関数に類似する`CObList::RemoveTail`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&108;](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="a-namesetata--coblistsetat"></a><a name="setat"></a>CObList::SetAt  
 指定された位置に要素を設定します。  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 **位置**を設定する要素のです。  
  
 `newElement`  
 `CObject`リストに書き込まれるへのポインター。  
  
### <a name="remarks"></a>コメント  
 型の変数**位置**リストのキーです。 操作できません。 したり、インデックスと同じには、**位置**自分の値。 `SetAt`書き込み、`CObject`リストの指定位置へのポインター。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に類似する`CObList::SetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**SetAt を無効にする (位置** `pos` **、const CString >/documents/report1.rdl」の** `newElement` **) です。**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt( POSITION** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>例  
  参照してください[使われて](#coblist)の一覧については、`CAge`クラスです。  
  
 [!code-cpp[NVC_MFCCollections #&109;](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStringList クラス](../../mfc/reference/cstringlist-class.md)   
 [CPtrList クラス](../../mfc/reference/cptrlist-class.md)

