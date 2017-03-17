---
title: "CObArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- arrays [C++], pointers
- CObArray class
- arrays [C++], Object type
- object arrays, CObArray class
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
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
ms.openlocfilehash: ed822c7e23510144d09ee268c1430aea354144cb
ms.lasthandoff: 02/24/2017

---
# <a name="cobarray-class"></a>CObArray クラス
`CObject` ポインターの配列をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CObArray : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::CObArray](#cobarray)|空の配列を構築`CObject`ポインター。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::Add](#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Append](#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CObArray::ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CObArray::FreeExtra](#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CObArray::GetAt](#getat)|指定されたインデックス位置にある値を返します。|  
|[CObArray::GetCount](#getcount)|この配列内の要素の数を取得します。|  
|[CObArray::GetData](#getdata)|配列内の要素へのアクセスを許可します。 できる**NULL**します。|  
|[CObArray::GetSize](#getsize)|この配列内の要素の数を取得します。|  
|[CObArray::GetUpperBound](#getupperbound)|有効な最大のインデックスを返します。|  
|[CObArray::InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CObArray::IsEmpty](#isempty)|配列が空かどうかを判別します。|  
|[CObArray::RemoveAll](#removeall)|この配列からすべての要素を削除します。|  
|[CObArray::RemoveAt](#removeat)|特定のインデックス位置にある要素を削除します。|  
|[CObArray::SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CObArray::SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CObArray::SetSize](#setsize)|この配列に含まれる要素の数を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::operator](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 これらのオブジェクトの配列は c 言語の配列に似ていますが、縮小や、必要に応じて拡張することができますが動的にします。  
  
 配列のインデックスは、常に 0 の位置から開始します。 上限の境界を修正するか、現在の境界を越えて要素を追加するとき、展開先の配列を許可するかどうかを決定できます。 メモリでは、いくつかの要素が null の場合でも上限の境界が連続的に割り当てられます。  
  
 Win32 でのサイズ、`CObArray`オブジェクトは使用可能なメモリに限定します。  
  
 C 言語の配列では、アクセスする時間と同様、`CObArray`インデックス付けされた要素は定数であり、配列のサイズに依存しません。  
  
 `CObArray` には、`IMPLEMENT_SERIAL` マクロが組み込まれており、その要素のシリアル化とダンプがサポートされます。 配列の場合`CObject`ポインターがオーバー ロードされた挿入演算子またはでアーカイブに格納されている、`Serialize`のメンバー関数の各`CObject`要素は、その配列のインデックスと共に、シリアル化します。  
  
 個別にダンプする必要がある場合`CObject`配列内の要素の深さを設定する必要があります、`CDumpContext`を 1 以上のオブジェクト。  
  
 ときに、`CObArray`オブジェクトを削除すると、またはその要素が削除されたとき、のみ、`CObject`ポインターを削除すると、オブジェクトではなくを参照します。  
  
> [!NOTE]
>  配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列クラスの派生は、リストの派生に似ています。 詳細については、特殊なリスト クラスの派生は、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
> [!NOTE]
>  使用する必要があります、`IMPLEMENT_SERIAL`配列をシリアル化する場合は、派生クラスの実装ではマクロです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="add"></a>CObArray::Add  
 新しい要素を 1 ずつ配列の拡張は、配列の末尾に追加します。  
  
```  
INT_PTR Add(CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `newElement`  
 `CObject`この配列に追加するへのポインター。  
  
### <a name="return-value"></a>戻り値  
 追加した要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 場合[SetSize](#setsize)と共に使用した、 `nGrowBy` 1、余分なメモリよりも大きい値を割り当てることができます。 ただし、上限の境界が唯一 1 ずつ増加します。  
  
 次の表はその他のメンバー関数に類似する`CObArray::Add`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR の追加 (バイト** `newElement` **) です。**<br /><br /> **スロー (関数\*) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR の追加 (DWORD** `newElement` **) です。**<br /><br /> **スロー (関数\*) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Add( void\*** `newElement` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR の追加 (LPCTSTR** `newElement` **); スロー (関数\*) です。**<br /><br /> **INT_PTR Add(const CString&** `newElement` **) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR の追加 (UINT** `newElement` **) です。**<br /><br /> **スロー (関数\*) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR の追加 (WORD** `newElement` **) です。**<br /><br /> **スロー (関数\*) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&75;](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `Add example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $442A 21`  
  
 `[1] = a CAge at $4468 40`  
  
##  <a name="append"></a>CObArray::Append  
 指定された配列の末尾に別の配列の内容を追加するには、このメンバー関数を呼び出します。  
  
```  
INT_PTR Append(const CObArray& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 配列に追加する要素のソースです。  
  
### <a name="return-value"></a>戻り値  
 追加された最初の要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 配列は、同じ型でなければなりません。  
  
 必要に応じて、 **Append**配列に追加された要素を格納する余分なメモリを割り当てることがあります。  
  
 次の表はその他のメンバー関数に類似する`CObArray::Append`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR の追加 (const CByteArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR の追加 (const CDWordArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR の追加 (const CPtrArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR の追加 (const CStringArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR の追加 (const CUIntArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR の追加 (const CWordArray >/documents/report1.rdl」の** *src* **) です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&76;](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]  
  
##  <a name="copy"></a>CObArray::Copy  
 同じ型の別の配列の要素で指定された配列の要素を上書きするには、このメンバー関数を呼び出します。  
  
```  
void Copy(const CObArray& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 配列にコピーする要素のソースです。  
  
### <a name="remarks"></a>コメント  
 **コピー**メモリは解放されません。 ただし、必要に応じて、**コピー**配列にコピーされた要素を格納する余分なメモリを割り当てることがあります。  
  
 次の表はその他のメンバー関数に類似する`CObArray::Copy`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**コピーを無効にする (const CByteArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**コピーを無効にする (const CDWordArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**コピーを無効にする (const CPtrArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**コピーを無効にする (const CStringArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**コピーを無効にする (const CUIntArray >/documents/report1.rdl」の** *src* **) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**コピーを無効にする (const CWordArray >/documents/report1.rdl」の** *src* **) です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&77;](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]  
  
##  <a name="cobarray"></a>CObArray::CObArray  
 空の構築`CObject`ポインターの配列。  
  
```  
CObArray();
```  
  
### <a name="remarks"></a>コメント  
 配列は、一度に&1; つの要素を拡張します。  
  
 次の表に、他のコンス トラクターに類似する`CObArray::CObArray`です。  
  
|クラス|コンストラクター|  
|-----------|-----------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&78;](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]  
  
##  <a name="elementat"></a>CObArray::ElementAt  
 配列内の要素ポインターへの一時的な参照を返します。  
  
```  
CObject*& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`GetUpperBound`します。  
  
### <a name="return-value"></a>戻り値  
 参照、`CObject`ポインター。  
  
### <a name="remarks"></a>コメント  
 配列の左側にある代入演算子の実装に使用されます。 これは、特殊な配列演算子の実装にのみ使用される高度な関数であることに注意してください。  
  
 次の表はその他のメンバー関数に類似する`CObArray::ElementAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**バイト >/reportbuilder/reportbuilder_3_0_0_0.application ElementAt (INT_PTR** `nIndex` **) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD >/reportbuilder/reportbuilder_3_0_0_0.application ElementAt (INT_PTR** `nIndex` **) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*ElementAt >/documents/report1.rdl」(INT_PTR** `nIndex` **) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString >/reportbuilder/reportbuilder_3_0_0_0.application ElementAt (INT_PTR** `nIndex` **) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT >/reportbuilder/reportbuilder_3_0_0_0.application ElementAt (INT_PTR** `nIndex` **) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD >/reportbuilder/reportbuilder_3_0_0_0.application ElementAt (INT_PTR** `nIndex` **) です。**|  
  
### <a name="example"></a>例  
  例を参照してください[CObArray::GetSize](#getsize)します。  
  
##  <a name="freeextra"></a>CObArray::FreeExtra  
 配列が拡張されたときに割り当てられたすべての余分なメモリを解放します。  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>コメント  
 この関数には、サイズや配列の上限値には影響はありません。  
  
 次の表はその他のメンバー関数に類似する`CObArray::FreeExtra`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void FreeExtra ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void FreeExtra ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra ();**|  
  
### <a name="example"></a>例  
  例を参照してください[CObArray::GetData](#getdata)します。  
  
##  <a name="getat"></a>CObArray::GetAt  
 指定したインデックスにある配列要素を返します。  
  
```  
CObject* GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`GetUpperBound`します。  
  
### <a name="return-value"></a>戻り値  
 `CObject`ポインター要素を指定したインデックス位置。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  によって返される値より大きい負の値または値を渡す`GetUpperBound`アサーションは失敗になります。  
  
 次の表はその他のメンバー関数に類似する`CObArray::GetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**バイト GetAt (INT_PTR** `nIndex` **) const です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\* GetAt (INT_PTR** `nIndex` **) const です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&79;](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]  
  
##  <a name="getcount"></a>CObArray::GetCount  
 配列要素の数を返します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列内の項目の数。  
  
### <a name="remarks"></a>コメント  
 配列内の要素の数を取得するには、このメソッドを呼び出します。 インデックスが 0 から始まるので、サイズは、インデックスの最大値より大きい 1 になります。  
  
 次の表はその他のメンバー関数に類似する`CObArray::GetCount`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Const; INT_PTR GetCount)**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Const; INT_PTR GetCount)**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Const; INT_PTR GetCount)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&80;](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]  
  
##  <a name="getdata"></a>CObArray::GetData  
 このメンバー関数を使用して、配列内の要素に直接アクセスします。  
  
```  
const CObject** GetData() const;  
  
CObject** GetData();
```  
  
### <a name="return-value"></a>戻り値  
 配列へのポインター`CObject`ポインター。  
  
### <a name="remarks"></a>コメント  
 要素がない場合、 `GetData` null 値を返します。  
  
 呼び出すときに警告を使用して、配列の要素への直接アクセスより早く作業する際に役立つ、 `GetData`; 直接、エラーがあれば、配列の要素に影響します。  
  
 次の表はその他のメンバー関数に類似する`CObArray::GetData`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const バイト\*const; GetData)バイト\*GetData ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData const (); DWORD\* GetData ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const void\* \* GetData () const; void\* \* GetData ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* const; GetData)CString\* GetData ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* const; GetData)UINT\* GetData ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD\* const; GetData)WORD\* GetData ();**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&81;](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]  
  
##  <a name="getsize"></a>CObArray::GetSize  
 配列のサイズを返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>コメント  
 インデックスが 0 から始まるため、サイズは、インデックスの最大値より大きい 1 です。  
  
 次の表はその他のメンバー関数に類似する`CObArray::GetSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Const; INT_PTR GetSize)**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Const; INT_PTR GetSize)**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Const; INT_PTR GetSize)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&82;](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>CObArray::GetUpperBound  
 この配列の現在の上限値を返します。  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="return-value"></a>戻り値  
 上限値 (0 から始まる) のインデックス。  
  
### <a name="remarks"></a>コメント  
 この関数が値 1 を返す配列のインデックスが 0 から始まるためより小さい`GetSize`します。  
  
 条件**です ()** = –&1; は、配列に要素が含まれないことを示します。  
  
 次の表はその他のメンバー関数に類似する`CObArray::GetUpperBound`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Const; INT_PTR です)**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Const; INT_PTR です)**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Const; INT_PTR です)**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Const; INT_PTR です)**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Const; INT_PTR です)**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Const; INT_PTR です)**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections&#83;](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]  
  
##  <a name="insertat"></a>CObArray::InsertAt  
 指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    CObject* newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CObArray* pNewArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 整数インデックス`GetUpperBound`します。  
  
 `newElement`  
 `CObject`この配列に配置するへのポインター。 A`newElement`値の**NULL**は許可されています。  
  
 `nCount`  
 この要素にする必要があります回数 (既定値は 1) が挿入されます。  
  
 `nStartIndex`  
 整数インデックス`GetUpperBound`します。  
  
 `pNewArray`  
 この配列に追加する要素を含む別の配列。  
  
### <a name="remarks"></a>コメント  
 最初のバージョン`InsertAt`配列内の指定したインデックス位置に&1; つの要素 (または要素の複数のコピー) を挿入します。 プロセスでは、その上がり、(インデックスをインクリメントする) をこのインデックスでは、既存の要素が上のすべての要素を移動します。  
  
 2 番目のバージョンから別のすべての要素の挿入`CObArray`コレクションの開始位置として、`nStartIndex`位置。  
  
 `SetAt`関数の場合、これに対し、1 つの指定した配列の要素を置換し、任意の要素を移動しません。  
  
 次の表はその他のメンバー関数に類似する`CObArray::InsertAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, BYTE** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **スロー (関数\*) です。**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CByteArray\*** `pNewArray` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **スロー (関数\*) です。**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CDWordArray\*** `pNewArray` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, void\*** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **スロー (関数\*) です。**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CPtrArray\*** `pNewArray` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **スロー (関数\*) です。**<br /><br /> **InsertAt を無効にする (INT_PTR** `nStartIndex` **、CStringArray\* ** `pNewArray` **) です。**<br /><br /> **スロー (関数\*) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, UINT** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **スロー (関数\*) です。**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CUIntArray\*** `pNewArray` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **スロー (関数\*) です。**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CWordArray\*** `pNewArray` **);**<br /><br /> **スロー (関数\*) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&84;](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `InsertAt example: A CObArray with 3 elements`  
  
 `[0] = a CAge at $45C8 21`  
  
 `[1] = a CAge at $4646 30`  
  
 `[2] = a CAge at $4606 40`  
  
##  <a name="isempty"></a>CObArray::IsEmpty  
 配列が空かどうかを判別します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列が空である場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="operator_at"></a>CObArray::operator  
 これらの添字演算子の便利な代替手段は、`SetAt`と`GetAt`関数です。  
  
```  
CObject*& operator[](int_ptr nindex);  
CObject* operator[](int_ptr nindex) const;  
```  
  
### <a name="remarks"></a>コメント  
 れていない配列の最初の演算子と呼ばれる**const**右 (右辺値) と、代入ステートメントの左側 (左辺値) のいずれかで使用することがあります。 2 番目の場合と呼ばれる**const**右上のみ、配列で使用できます。  
  
 ライブラリのデバッグ バージョンでは、添字 (またはいずれかで、左、代入ステートメントの右側にある) が範囲外かどうかをアサートします。  
  
 次の表に、その他の演算子に類似する**CObArray::operator:operator[]**します。  
  
|クラス|演算子|  
|-----------|--------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**バイト >/reportbuilder/reportbuilder_3_0_0_0.application 演算子 (int_ptr** `nindex` **\)です。**<br /><br /> **Byte[] 演算子 (int_ptr** `nindex` ** \) const です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD >/reportbuilder/reportbuilder_3_0_0_0.application 演算子 (int_ptr** `nindex` **\)です。**<br /><br /> **DWORD 演算子 (int_ptr** `nindex` ** \) const です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& operator [](int_ptr** `nindex` **\);**<br /><br /> **void\*演算子 (int_ptr** `nindex` ** \) const です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString < 演算子 (int_ptr** `nindex` **\)です。**<br /><br /> **CString operator[] (int_ptr** `nindex` ** \) const です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT < 演算子 (int_ptr** `nindex` **\)です。**<br /><br /> **UINT operator[] (int_ptr** `nindex` ** \) const です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD < 演算子 (int_ptr** `nindex` **\)です。**<br /><br /> **WORD operator[] (int_ptr** `nindex` ** \) const です。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&88;](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]  
  
##  <a name="removeall"></a>CObArray::RemoveAll  
 この配列からすべてのポインターを削除しますが、実際には削除されません、`CObject`オブジェクトです。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 配列が既に空の場合、関数も使用できます。  
  
 `RemoveAll`関数ポインターを格納するため、すべてのメモリを解放します。  
  
 次の表はその他のメンバー関数に類似する`CObArray::RemoveAll`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**RemoveAll (); を無効にします。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**RemoveAll (); を無効にします。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**RemoveAll (); を無効にします。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**RemoveAll (); を無効にします。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**RemoveAll (); を無効にします。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**RemoveAll (); を無効にします。**|  
  
### <a name="example"></a>例  
 参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&85;](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]  
  
##  <a name="removeat"></a>CObArray::RemoveAt  
 配列内の指定したインデックスから始まる&1; つまたは複数の要素を削除します。  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`GetUpperBound`します。  
  
 `nCount`  
 削除する要素の数を指定します。  
  
### <a name="remarks"></a>コメント  
 プロセスでは、削除された要素の上のすべての要素をだけシフトします。 これをデクリメント上は、配列のバインドが、メモリは解放されません。  
  
 削除位置以降の配列に含まれる以上の要素を削除しようとする場合、ライブラリのデバッグ バージョンはアサートします。  
  
 `RemoveAt`削除の機能、 `CObject` 、配列からのポインターでは、オブジェクト自体は削除されません。  
  
 次の表はその他のメンバー関数に類似する`CObArray::RemoveAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**RemoveAt を無効にする (INT_PTR** `nIndex` **、INT_PTR** *nCount* **= 1) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&112;](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `RemoveAt example: A CObArray with 1 elements`  
  
 `[0] = a CAge at $4606 40`  
  
##  <a name="setat"></a>CObArray::SetAt  
 指定したインデックス位置にある配列要素を設定します。  
  
```  
void SetAt(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`GetUpperBound`します。  
  
 `newElement`  
 この配列に挿入するオブジェクトのポインター。 A **NULL**値を指定します。  
  
### <a name="remarks"></a>コメント  
 `SetAt`拡張先の配列は発生しません。 使用`SetAtGrow`する場合は自動的に拡張する配列。  
  
 インデックス値が配列内の有効な位置を表すことを確認する必要があります。 範囲外の場合は、ライブラリのデバッグ バージョンはアサートします。  
  
 次の表はその他のメンバー関数に類似する`CObArray::SetAt`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAt( INT_PTR** `nIndex` **, BYTE** `newElement` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, DWORD** `newElement` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, void\*** `newElement` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, UINT** `newElement` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, WORD** `newElement` **);**|  
  
### <a name="example"></a>例  
  参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&86;](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `SetAt example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $47E0 30`  
  
 `[1] = a CAge at $47A0 40`  
  
##  <a name="setatgrow"></a>CObArray::SetAtGrow  
 指定したインデックス位置にある配列要素を設定します。  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数のインデックス。  
  
 `newElement`  
 この配列に追加するオブジェクトのポインター。 A **NULL**値を指定します。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、配列を自動的に大きく (定義した上限の境界は新しい要素のために調整されます)。  
  
 次の表はその他のメンバー関数に類似する`CObArray::SetAtGrow`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, BYTE** `newElement` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, void\*** `newElement` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**SetAtGrow を無効にする (INT_PTR** `nIndex` **、LPCTSTR** `newElement` **) です。**<br /><br /> **スロー (関数\*) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **スロー (関数\*) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **スロー (関数\*) です。**|  
  
### <a name="example"></a>例  
  参照してください[使われて](../../mfc/reference/coblist-class.md#coblist)の一覧については、`CAge`コレクションのすべての例で使用されるクラスです。  
  
 [!code-cpp[NVC_MFCCollections #&87;](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]  
  
 このプログラムからの結果は次のとおりです。  
  
 `SetAtGrow example: A CObArray with 4 elements`  
  
 `[0] = a CAge at $47C0 21`  
  
 `[1] = a CAge at $4800 40`  
  
 `[2] = NULL`  
  
 `[3] = a CAge at $4840 65`  
  
##  <a name="setsize"></a>CObArray::SetSize  
 空または既存の配列のサイズを設定します必要な場合は、メモリを割り当てます。  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewSize`  
 新しい配列のサイズ (要素の数)。 0 以上にする必要があります。  
  
 `nGrowBy`  
 サイズの増加が必要な場合を確保する要素のスロットの最小数。  
  
### <a name="remarks"></a>コメント  
 新しいサイズが元のサイズより小さい場合は、配列が切り捨てられるし、すべての未使用メモリを解放します。 効率を高めるため、呼び出す`SetSize`を使用する前に、配列のサイズを設定します。 これにより、再割り当てし、項目が追加されるたびに、配列をコピーする必要があります。  
  
 `nGrowBy`パラメーターは、配列は増え続けている中に内部メモリの割り当てに影響します。 使用は配列のサイズをによって報告されたに影響しない`GetSize`と`GetUpperBound`です。  
  
 配列のサイズが大きくなった場合、新しく割り当てられた**CObject \* **ポインターが NULL に設定されます。  
  
 次の表はその他のメンバー関数に類似する`CObArray::SetSize`です。  
  
|クラス|メンバー関数|  
|-----------|---------------------|  
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **スロー (関数\*) です。**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **スロー (関数\*) です。**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **スロー (関数\*) です。**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **スロー (関数\*) です。**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **スロー (関数\*) です。**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1 );**<br /><br /> **スロー (関数\*) です。**|  
  
### <a name="example"></a>例  
  例を参照してください[CObArray::GetData](#getdata)します。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStringArray クラス](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray クラス](../../mfc/reference/cptrarray-class.md)   
 [CByteArray クラス](../../mfc/reference/cbytearray-class.md)   
 [CWordArray クラス](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray クラス](../../mfc/reference/cdwordarray-class.md)

