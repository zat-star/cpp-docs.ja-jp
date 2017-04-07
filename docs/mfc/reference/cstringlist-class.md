---
title: "CStringList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], lists
- lists, string
- CStringList class
- strings [C++], collections
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
caps.latest.revision: 25
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0b67104e330890ffe8f67bac0dd3b129c7742a29
ms.lasthandoff: 02/24/2017

---
# <a name="cstringlist-class"></a>CStringList クラス
`CString` オブジェクトのリストをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CStringList`クラスのメンバー関数に似ています[CObList](../../mfc/reference/coblist-class.md)します。 メンバー関数については `CObList` クラスの説明を参照してください。 表示されたら、`CObject`ポインター、戻り値として次のように置き換えてください。、 `CString` (いない、`CString`ポインター)。 表示されたら、`CObject`ポインター、関数パラメーターとして次のように置き換えてください。、`LPCTSTR`です。  
  
 `CObject*& CObList::GetHead() const;`  
  
 たとえば、次のように変換します。  
  
 `CString& CStringList::GetHead() const;`  
  
 および  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 次のように変換します。  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[使われて](../../mfc/reference/coblist-class.md#coblist)|空のリストを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|(新しいヘッドによって作成) リストの先頭に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|(新しい末尾によって作成) リストの末尾に要素 (または別のリスト内のすべての要素) を追加します。|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|ポインター値によって指定される要素の位置を取得します。|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|0 から始まるインデックスで指定された要素の位置を取得します。|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|指定された位置に要素を取得します。|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|この一覧には、要素の数を返します。|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|(空にすることはできません) の一覧の先頭の要素を返します。|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|リストの先頭の要素の位置を返します。|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|反復処理するためには、次の要素を取得します。|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|反復処理するためには、直前の要素を取得します。|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|この一覧には、要素の数を返します。|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|(空にすることはできません)、リストの末尾の要素を返します。|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|リストの末尾の要素の位置を返します。|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|指定した位置の後に新しい要素を挿入します。|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|指定した位置の前に新しい要素を挿入します。|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|空のリストの状態 (要素がない) をテストします。|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|この一覧からすべての要素を削除します。|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|位置によって指定されたこのリストから要素を削除します。|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|リストの先頭から要素を削除します。|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|リストの末尾から要素を削除します。|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|指定された位置に要素を設定します。|  
  
## <a name="remarks"></a>コメント  
 すべての比較は、値、つまり、文字列のアドレスではなく、文字列内の文字を比較することによって実行されます。  
  
 `CStringList` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 リストの場合`CString`オブジェクトがオーバー ロードされた挿入演算子またはでアーカイブに格納されている、`Serialize`のメンバー関数の各`CString`要素が順にシリアル化します。  
  
 個別にダンプする必要がある場合`CString`要素を 1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 使用する方法について`CStringList`、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




