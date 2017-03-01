---
title: "CList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CList
dev_langs:
- C++
helpviewer_keywords:
- lists
- lists, base class for
- CList class
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
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
ms.openlocfilehash: 05d35419f70ab039e6981938c516201b252878d4
ms.lasthandoff: 02/24/2017

---
# <a name="clist-class"></a>CList クラス
オブジェクト (重複あり) を順に並べたリストをサポートします。このリストには、シーケンシャル アクセスまたは値指定によるアクセスを行うことができます。  
  
## <a name="syntax"></a>構文  
  
```  
template<class TYPE, class ARG_TYPE = const TYPE&>  
class CList : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CList::CList](#clist)|空の順序付きリストを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CList::AddHead](#addhead)|(新しいヘッドによって作成) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CList::AddTail](#addtail)|(新しい末尾によって作成) リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CList::Find](#find)|ポインター値によって指定される要素の位置を取得します。|  
|[CList::FindIndex](#findindex)|0 から始まるインデックスで指定された要素の位置を取得します。|  
|[CList::GetAt](#getat)|指定された位置に要素を取得します。|  
|[呼び出す](#getcount)|この一覧には、要素の数を返します。|  
|[CList::GetHead](#gethead)|(空にすることはできません) の一覧の先頭の要素を返します。|  
|[CList::GetHeadPosition](#getheadposition)|リストの先頭の要素の位置を返します。|  
|[CList::GetNext](#getnext)|反復処理するためには、次の要素を取得します。|  
|[CList::GetPrev](#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CList::GetSize](#getsize)|この一覧には、要素の数を返します。|  
|[CList::GetTail](#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CList::GetTailPosition](#gettailposition)|リストの末尾の要素の位置を返します。|  
|[CList::InsertAfter](#insertafter)|指定した位置の後に新しい要素を挿入します。|  
|[CList::InsertBefore](#insertbefore)|指定した位置の前に新しい要素を挿入します。|  
|[CList::IsEmpty](#isempty)|空のリストの状態 (要素がない) をテストします。|  
|[CList::RemoveAll](#removeall)|この一覧からすべての要素を削除します。|  
|[CList::RemoveAt](#removeat)|位置によって指定されたこのリストから要素を削除します。|  
|[CList::RemoveHead](#removehead)|リストの先頭から要素を削除します。|  
|[CList::RemoveTail](#removetail)|リストの末尾から要素を削除します。|  
|[CList::SetAt](#setat)|指定された位置に要素を設定します。|  
  
#### <a name="parameters"></a>パラメーター  
 `TYPE`  
 リストに格納されているオブジェクトの型。  
  
 `ARG` *_* `TYPE`  
 型は、リストに格納されたオブジェクトを参照するために使用します。 参照であることができます。  
  
## <a name="remarks"></a>コメント  
 `CList`リストは、二重リンク リストのように動作します。  
  
 型の変数**位置**リストのキーです。 使用することができます、**位置**および位置を保持するためのブックマークとして、リストを順番に走査する反復子変数です。 位置は、インデックスと同じしかしです。  
  
 要素の挿入は非常に高速リストの先頭、末尾、および既知**位置**します。 順次検索は、値またはインデックスで要素を検索する必要があります。 この検索は、リストが長い場合は低速にすることはできます。  
  
 一覧に個々 の要素をダンプする場合は、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 ほとんどの用途のグローバル ヘルパー関数をこのクラスの呼び出しの一部のメンバー関数をカスタマイズする必要があります、`CList`クラスです。 参照してください[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md) 「マクロとグローバル変数」に記載します。  
  
 使用する方法について`CList`、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&#35;](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="a-nameaddheada--clistaddhead"></a><a name="addhead"></a>CList::AddHead  
 このリストの先頭に新しい要素または要素のリストを追加します。  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 新しい要素。  
  
 `pNewList`  
 別のポインター `CList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンの取得、**位置**新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&#36;](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="a-nameaddtaila--clistaddtail"></a><a name="addtail"></a>CList::AddTail  
 このリストの末尾に新しい要素または要素のリストを追加します。  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 この一覧に追加する要素。  
  
 `pNewList`  
 別のポインター `CList`  ボックスの一覧です。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンの取得、**位置**新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 一覧は、操作の前に空にすることができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&37;](../../mfc/codesnippet/cpp/clist-class_3.cpp)]  
  
##  <a name="a-nameclista--clistclist"></a><a name="clist"></a>CList::CList  
 空の順序付きリストを構築します。  
  
```  
CList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 リストを拡張するメモリ割り当ての粒度。  
  
### <a name="remarks"></a>コメント  
 単位でメモリが割り当てられている一覧するにつれて、`nBlockSize`エントリです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&38;](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="a-namefinda--clistfind"></a><a name="find"></a>CList::Find  
 指定された一致する最初の要素を検索するには、順番にリストを検索`searchValue`します。  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `searchValue`  
 一覧で検索する値。  
  
 `startAfter`  
 検索の開始位置。 値が指定されていない場合は、その head 要素と、検索が開始されます。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**オブジェクトが見つからない場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&#39;](../../mfc/codesnippet/cpp/clist-class_5.cpp)]  
  
##  <a name="a-namefindindexa--clistfindindex"></a><a name="findindex"></a>CList::FindIndex  
 値を使用して`nIndex`としてリストのインデックス。  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 検索するリストの要素の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**場合`nIndex`が負の値または大きすぎます。  
  
### <a name="remarks"></a>コメント  
 上の停止して、リストの先頭からのシーケンシャルなスキャンを開始、 *n*番目の要素。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&40;](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="a-namegetata--clistgetat"></a><a name="getat"></a>CList::GetAt  
 指定した位置にあるリスト要素を取得します。  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 一覧でオブジェクトの種類を指定するテンプレート パラメーター。  
  
 *位置*  
 取得する要素の一覧における位置。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照して`GetHead`します。  
  
### <a name="remarks"></a>コメント  
 `GetAt`指定した位置に関連付けられている要素 (または、要素への参照) を返します。 操作できません。 したり、インデックスと同じには、**位置**自分の値。 型の変数**位置**リストのキーです。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
  例を参照してください[CList::GetHeadPosition](#getheadposition)します。  
  
##  <a name="a-namegetcounta--clistgetcount"></a><a name="getcount"></a>呼び出す  
 この一覧内の要素の数を取得します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 要素の数を含む整数値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すのと同じ結果が生成されます、 [CList::GetSize](#getsize)メソッドです。  
  
### <a name="example"></a>例  
  例を参照してください[CList::RemoveHead](#removehead)します。  
  
##  <a name="a-namegetheada--clistgethead"></a><a name="gethead"></a>CList::GetHead  
 この一覧の先頭の要素 (または head 要素への参照) を取得します。  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 一覧でオブジェクトの種類を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの場合**const**、`GetHead`リストの先頭にある要素のコピーを返します。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護します。  
  
 一覧にある場合**const**、`GetHead`リストの先頭にある要素への参照を返します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetHead`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&41;](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="a-namegetheadpositiona--clistgetheadposition"></a><a name="getheadposition"></a>CList::GetHeadPosition  
 この一覧の先頭の要素の位置を取得します。  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**リストが空の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&42;](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="a-namegetnexta--clistgetnext"></a><a name="getnext"></a>CList::GetNext  
 識別される要素を取得`rPosition`、設定し、`rPosition`に、**位置**一覧の次のエントリの値。  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**以前から返される値`GetNext`、[順](#getheadposition)、またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストの場合**const**、`GetNext`リストの要素のコピーを返します。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護します。  
  
 一覧にある場合**const**、`GetNext`リストの要素への参照を返します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 使用する`GetNext`への呼び出しでは、最初の位置を確立する場合は、順方向の反復ループで`GetHeadPosition`または**検索**します。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得した要素が値の場合、リスト内の最後の新しいの`rPosition`に設定されている**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&43;](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="a-namegetpreva--clistgetprev"></a><a name="getprev"></a>CList::GetPrev  
 識別される要素を取得`rPosition`、設定し、`rPosition`に、**位置**一覧の前のエントリの値。  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**以前から返される値`GetPrev`またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 リストの場合**const**、`GetPrev`リストの先頭にある要素のコピーを返します。 これにより、関数は、代入ステートメントの右側にあるでのみ使用し、変更から一覧を保護します。  
  
 一覧にある場合**const**、`GetPrev`リストの要素への参照を返します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 使用する`GetPrev`への呼び出しでは、最初の位置を確立する場合に、逆順イテレーション ループで`GetTailPosition`または**検索**します。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 要素を取得した一覧で、最初からの新しい値場合`rPosition`に設定されている**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&44;](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="a-namegetsizea--clistgetsize"></a><a name="getsize"></a>CList::GetSize  
 リストの要素数を返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リストの項目数。  
  
### <a name="remarks"></a>コメント  
 リスト内の要素の数を取得するには、このメソッドを呼び出します。  このメソッドを呼び出すのと同じ結果が生成されます、[呼び出す](#getcount)メソッドです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&45;](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="a-namegettaila--clistgettail"></a><a name="gettail"></a>CList::GetTail  
 取得、`CObject`ポインターがこのリストの末尾の要素を表します。  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 戻り値の説明を参照して[gethead 関数](../../mfc/reference/coblist-class.md#gethead)します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetTail`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&#46;](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="a-namegettailpositiona--clistgettailposition"></a><a name="gettailposition"></a>CList::GetTailPosition  
 このリストの末尾の要素の位置を取得します。**NULL**リストが空の場合。  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A**位置**イテレーションまたはオブジェクト ポインターの取得のために使用する値**NULL**リストが空の場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&47;](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="a-nameinsertaftera--clistinsertafter"></a><a name="insertafter"></a>CList::InsertAfter  
 指定位置にある要素の後にこのリストに要素を追加します。  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `ARG_TYPE`  
 リストの要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この一覧に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 イテレーションまたは一覧の要素の取得に使用できる **POSITION** 値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&48;](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="a-nameinsertbeforea--clistinsertbefore"></a><a name="insertbefore"></a>CList::InsertBefore  
 一覧の指定した位置にある要素の前に要素を追加します。  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 前の **、** 、または `GetNext`Find `GetPrev`メンバー関数呼び出しにより返される **POSITION** 値。  
  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 この一覧に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 イテレーションまたは一覧の要素の取得に使用できる **POSITION** 値。  
  
### <a name="remarks"></a>コメント  
 *position* が **NULL**である場合、一覧の先頭に要素が挿入されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections 番号&49;](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="a-nameisemptya--clistisempty"></a><a name="isempty"></a>CList::IsEmpty  
 このリストに要素が含まれないかどうかを示します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 この場合は 0 以外のリストは空です。それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&50;](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="a-nameremovealla--clistremoveall"></a><a name="removeall"></a>CList::RemoveAll  
 このリストからすべての要素を削除し、関連付けられているメモリを解放します。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 リストが既に空の場合、エラーは発生しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&51;](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="a-nameremoveata--clistremoveat"></a><a name="removeat"></a>CList::RemoveAt  
 この一覧から、指定した要素を削除します。  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>パラメーター  
 *位置*  
 一覧から削除する要素の位置。  
  
### <a name="remarks"></a>コメント  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&52;](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="a-nameremoveheada--clistremovehead"></a><a name="removehead"></a>CList::RemoveHead  
 リストの先頭から要素を削除し、ポインターを返します。  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 以前、リストの先頭にある要素。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveHead`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&53;](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="a-nameremovetaila--clistremovetail"></a><a name="removetail"></a>CList::RemoveTail  
 リストの末尾から要素を削除し、ポインターを返します。  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リスト内の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの後部にあった要素です。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveTail`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](#isempty)リストに要素が含まれていることを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&54;](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="a-namesetata--clistsetat"></a><a name="setat"></a>CList::SetAt  
 型の変数**位置**リストのキーです。  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 **位置**を設定する要素のです。  
  
 `ARG_TYPE`  
 一覧の要素の型を指定するテンプレート パラメーター (参照を使用できます)。  
  
 `newElement`  
 一覧に追加する要素。  
  
### <a name="remarks"></a>コメント  
 操作できません。 したり、インデックスと同じには、**位置**自分の値。 `SetAt`リスト内の指定した位置に要素を書き込みます。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&55;](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [メンバー クラス](../../mfc/reference/cmap-class.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)

