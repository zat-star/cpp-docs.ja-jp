---
title: "CTypedPtrList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrList
dev_langs:
- C++
helpviewer_keywords:
- CTypedPtrList class
- type-safe collections
- lists [C++]
- template classes, CTypedPtrList class
- linked lists [C++]
- pointer lists
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
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
ms.openlocfilehash: ca8d868333aa977710e387fc1bb13271dc8f99fa
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrlist-class"></a>CTypedPtrList クラス
`CPtrList`クラスのオブジェクトに対してタイプ セーフな "ラップ" が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 クラスの基本クラス、型指定されたポインター ボックスの一覧です。ポインター リスト クラスである必要があります (`CObList`または`CPtrList`)。  
  
 `TYPE`  
 基底クラス リストに格納された要素の型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|(新しいヘッドによって作成) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CTypedPtrList::AddTail](#addtail)|(新しい末尾によって作成) リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CTypedPtrList::GetAt](#getat)|指定された位置に要素を取得します。|  
|[CTypedPtrList::GetHead](#gethead)|(空にすることはできません) の一覧の先頭の要素を返します。|  
|[CTypedPtrList::GetNext](#getnext)|反復処理するためには、次の要素を取得します。|  
|[CTypedPtrList::GetPrev](#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CTypedPtrList::GetTail](#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CTypedPtrList::RemoveHead](#removehead)|リストの先頭から要素を削除します。|  
|[CTypedPtrList::RemoveTail](#removetail)|リストの末尾から要素を削除します。|  
|[CTypedPtrList::SetAt](#setat)|指定された位置に要素を設定します。|  
  
## <a name="remarks"></a>コメント  
 使用すると`CTypedPtrList`なく`CObList`または`CPtrList`C++ の型チェック機能により、一致しないポインター型によって発生したエラーを排除します。  
  
 さらに、`CTypedPtrList`を使用した場合に必要がありますキャストの多くを実行するラッパー`CObList`または`CPtrList`です。  
  
 すべて`CTypedPtrList`関数はインラインで、このテンプレートを使用しない変わらないサイズや、コードの処理速度。  
  
 派生したリスト`CObList`から派生したのですが、シリアル化できる`CPtrList`ことはできません。  
  
 `CTypedPtrList` オブジェクトが削除されたとき、またはその要素が削除されたときは、ポインターだけが削除されます。ポインターが参照するエンティティは削除されません。  
  
 使用する方法について`CTypedPtrList`、記事を参照して[コレクション](../../mfc/collections.md)と[クラスのテンプレートに基づく](../../mfc/template-based-classes.md)します。  
  
## <a name="example"></a>例  
 この例のインスタンスを作成する`CTypedPtrList`、1 つのオブジェクトを追加、リストをディスクにシリアル化およびから、オブジェクトを削除します。  
  
 [!code-cpp[NVC_MFCCollections #&110;](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections #&111;](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="a-nameaddheada--ctypedptrlistaddhead"></a><a name="addhead"></a>CTypedPtrList::AddHead  
 このメンバー関数を呼び出す`BASE_CLASS` **:: AddHead**します。  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 基底クラス リストに格納された要素の型。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。 A **NULL**値を指定します。  
  
 `BASE_CLASS`  
 クラスの基本クラス、型指定されたポインター ボックスの一覧です。ポインター リスト クラスである必要があります ( [CObList](../../mfc/reference/coblist-class.md)または[CPtrList](../../mfc/reference/cptrlist-class.md))。  
  
 `pNewList`  
 別のポインター [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md)オブジェクトです。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンの取得、**位置**新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンでは、リストの先頭の前に新しい要素を追加します。 2 番目のバージョンでは、別のリストの先頭の前に要素を追加します。  
  
##  <a name="a-nameaddtaila--ctypedptrlistaddtail"></a><a name="addtail"></a>CTypedPtrList::AddTail  
 このメンバー関数を呼び出す`BASE_CLASS` **:: AddTail**します。  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 基底クラス リストに格納された要素の型。  
  
 `newElement`  
 この一覧に追加するオブジェクトのポインター。 A **NULL**値を指定します。  
  
 `BASE_CLASS`  
 クラスの基本クラス、型指定されたポインター ボックスの一覧です。ポインター リスト クラスである必要があります ( [CObList](../../mfc/reference/coblist-class.md)または[CPtrList](../../mfc/reference/cptrlist-class.md))。  
  
 `pNewList`  
 別のポインター [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md)オブジェクトです。 内の要素`pNewList`この一覧に追加されます。  
  
### <a name="return-value"></a>戻り値  
 最初のバージョンの取得、**位置**新しく挿入される要素の値。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンでは、リストの末尾に新しい要素を追加します。 2 番目のバージョンでは、リストの後部後の要素の別のリストを追加します。  
  
##  <a name="a-namegetata--ctypedptrlistgetat"></a><a name="getat"></a>CTypedPtrList::GetAt  
 型の変数**位置**リストのキーです。  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リストに格納されている要素の型を指定するテンプレート パラメーター。  
  
 *位置*  
 A**位置**以前から返される値`GetHeadPosition`または**検索**メンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 一覧にはへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetAt`テンプレート パラメーターで指定された型のポインターを返します*型*します。 これは、関数は、代入ステートメントの右側にあるでのみ使用し、したがって、ボックスの一覧を変更から保護します。  
  
 一覧には直接、またはポインターにアクセスする場合、 `CTypedPtrList`、し`GetAt`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 操作できません。 したり、インデックスと同じには、**位置**自分の値。 `GetAt`取得、`CObject`指定した位置に関連付けられたポインター。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 このインライン関数が呼び出す`BASE_CLASS` **:: GetAt**します。  
  
##  <a name="a-namegetheada--ctypedptrlistgethead"></a><a name="gethead"></a>CTypedPtrList::GetHead  
 この一覧の先頭の要素を表すポインターを取得します。  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リストに格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 一覧にはへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetHead`テンプレート パラメーターで指定された型のポインターを返します*型*します。 これは、関数は、代入ステートメントの右側にあるでのみ使用し、したがって、ボックスの一覧を変更から保護します。  
  
 一覧には直接、またはポインターにアクセスする場合、 `CTypedPtrList`、し`GetHead`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetHead`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="a-namegetnexta--ctypedptrlistgetnext"></a><a name="getnext"></a>CTypedPtrList::GetNext  
 識別される要素を取得`rPosition`、設定し、`rPosition`に、**位置**一覧の次のエントリの値。  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 この一覧に含まれる要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**以前から返される値`GetNext`、 `GetHeadPosition`、またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 一覧にはへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetNext`テンプレート パラメーターで指定された型のポインターを返します*型*します。 これは、関数は、代入ステートメントの右側にあるでのみ使用し、したがって、ボックスの一覧を変更から保護します。  
  
 一覧には直接、またはポインターにアクセスする場合、 `CTypedPtrList`、し`GetNext`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 使用する`GetNext`への呼び出しでは、最初の位置を確立する場合は、順方向の反復ループで`GetHeadPosition`または[CPtrList::Find](../../mfc/reference/coblist-class.md#find)します。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得した要素が値の場合、リスト内の最後の新しいの`rPosition`に設定されている**NULL**します。  
  
 反復処理中に要素を削除することができます。 例を参照してください[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)します。  
  
##  <a name="a-namegetpreva--ctypedptrlistgetprev"></a><a name="getprev"></a>CTypedPtrList::GetPrev  
 識別される要素を取得`rPosition`、設定し、`rPosition`に、**位置**一覧の前のエントリの値。  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 この一覧に含まれる要素の型を指定するテンプレート パラメーター。  
  
 `rPosition`  
 参照、**位置**以前から返される値`GetPrev`またはその他のメンバー関数の呼び出しです。  
  
### <a name="return-value"></a>戻り値  
 一覧にはへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetPrev`テンプレート パラメーターで指定された型のポインターを返します*型*します。 これは、関数は、代入ステートメントの右側にあるでのみ使用し、したがって、ボックスの一覧を変更から保護します。  
  
 一覧には直接、またはポインターにアクセスする場合、 `CTypedPtrList`、し`GetPrev`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 使用する`GetPrev`への呼び出しでは、最初の位置を確立する場合に、逆順イテレーション ループで`GetTailPosition`または**検索**します。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 要素を取得した一覧で、最初からの新しい値場合`rPosition`に設定されている**NULL**します。  
  
##  <a name="a-namegettaila--ctypedptrlistgettail"></a><a name="gettail"></a>CTypedPtrList::GetTail  
 この一覧の先頭の要素を表すポインターを取得します。  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リストに格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 一覧にはへのポインターを介してアクセスする場合、 **const CTypedPtrList**、し`GetTail`テンプレート パラメーターで指定された型のポインターを返します*型*します。 これは、関数は、代入ステートメントの右側にあるでのみ使用し、したがって、ボックスの一覧を変更から保護します。  
  
 一覧には直接、またはポインターにアクセスする場合、 `CTypedPtrList`、し`GetTail`テンプレート パラメーターで指定された型のポインターへの参照を返します*型*します。 代入ステートメントのどちらにも使用される関数は、このできるので、リスト エントリを変更できます。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`GetTail`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="a-nameremoveheada--ctypedptrlistremovehead"></a><a name="removehead"></a>CTypedPtrList::RemoveHead  
 リストの先頭から要素を削除し、それを返します。  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リストに格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの先頭にあったのポインター。 このポインターは、テンプレート パラメーターで指定された型*型*します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveHead`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="a-nameremovetaila--ctypedptrlistremovetail"></a><a name="removetail"></a>CTypedPtrList::RemoveTail  
 リストの末尾から要素を削除し、それを返します。  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 リストに格納されている要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 リストの後部にあったのポインター。 このポインターは、テンプレート パラメーターで指定された型*型*します。  
  
### <a name="remarks"></a>コメント  
 リストが呼び出す前に空でないことを確認する必要があります`RemoveTail`します。 リストが空の場合、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。 使用[IsEmpty](../../mfc/reference/coblist-class.md#isempty)リストに要素が含まれていることを確認します。  
  
##  <a name="a-namesetata--ctypedptrlistsetat"></a><a name="setat"></a>CTypedPtrList::SetAt  
 このメンバー関数を呼び出す`BASE_CLASS` **:: SetAt**します。  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 **位置**を設定する要素のです。  
  
 *型*  
 基底クラス リストに格納された要素の型。  
  
 `newElement`  
 一覧に書き込まれるオブジェクトのポインター。  
  
### <a name="remarks"></a>コメント  
 型の変数**位置**リストのキーです。 操作できません。 したり、インデックスと同じには、**位置**自分の値。 `SetAt`オブジェクトへのポインターを一覧内の指定位置に書き込みます。  
  
 確認する必要があります、**位置**値がリスト内の有効な位置を表します。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 詳細についてを参照してください。 [CObList::SetAt](../../mfc/reference/coblist-class.md#setat)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPtrList クラス](../../mfc/reference/cptrlist-class.md)   
 [CObList クラス](../../mfc/reference/coblist-class.md)

