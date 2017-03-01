---
title: "CArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArray
dev_langs:
- C++
helpviewer_keywords:
- CArray class
- arrays [C++], classes
- templates, collection classes
- collection classes, template-based
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
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
ms.openlocfilehash: bac8e08540ffead565d1097c6ef1efcae5e606c2
ms.lasthandoff: 02/24/2017

---
# <a name="carray-class"></a>CArray クラス
C 言語の配列に似ていますが、動的に削減でき、必要に応じて大きくなる配列をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
template <class TYPE, class ARG_TYPE = const TYPE&>  
class CArray : public CObject  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TYPE`  
 配列に格納されているオブジェクトの種類を指定するテンプレート パラメーター。 `TYPE`によって返されるパラメーターは、`CArray`です。  
  
 `ARG` *_* `TYPE`  
 配列に格納されているオブジェクトへのアクセスに使用される引数の型を指定するテンプレート パラメーター。 参照を多くの場合、`TYPE`です。 `ARG_TYPE`渡されるパラメーターは、`CArray`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CArray::CArray](#carray)|空の配列を生成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CArray::Add](#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CArray::Append](#append)|別の配列を追加します。必要に応じて、配列を大きく|  
|[CArray::Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CArray::ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CArray::FreeExtra](#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CArray::GetAt](#getat)|指定されたインデックス位置にある値を返します。|  
|[呼び出す](#getcount)|この配列内の要素の数を取得します。|  
|[CArray::GetData](#getdata)|配列内の要素へのアクセスを許可します。 できる**NULL**します。|  
|[呼び出す](#getsize)|この配列内の要素の数を取得します。|  
|[CArray::GetUpperBound](#getupperbound)|有効な最大のインデックスを返します。|  
|[CArray::InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CArray::IsEmpty](#isempty)|配列が空かどうかを決定します。|  
|[CArray::RemoveAll](#removeall)|この配列からすべての要素を削除します。|  
|[CArray::RemoveAt](#removeat)|特定のインデックス位置にある要素を削除します。|  
|[CArray::SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CArray::SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CArray::SetSize](#setsize)|この配列に含まれる要素の数を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator&#91;&#93;](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 配列のインデックスは、常に 0 の位置から開始します。 上限の境界を修正するか、過去の現在のバインド要素を追加するとき、展開先の配列を有効にするかどうかを決定できます。 メモリでは、いくつかの要素が null の場合でも上限の境界が連続的に割り当てられます。  
  
> [!NOTE]
>  サイズが変更されるほとんどのメソッド、`CArray`要素を使用して追加またはオブジェクト[memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)要素を移動します。 問題のためにこれは`memcpy_s`呼び出されるコンス トラクターを必要とする任意のオブジェクトと互換性がありません。 場合内の項目、`CArray`と互換性がない`memcpy_s`、新規に作成する必要があります`CArray`の適切なサイズです。 使用して[CArray::Copy](#copy)と[CArray::SetAt](#setat)これらのメソッドの代わりに、代入演算子を使用するために、新しい配列を作成する`memcpy_s`です。  
  
 C 言語の配列では、アクセスする時間と同様、`CArray`インデックス付けされた要素は定数であり、配列のサイズに依存しません。  
  
> [!TIP]
>  配列を使用する前に使用して[SetSize](#setsize)そのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列の個々 の要素をダンプする場合は、深さを設定する必要があります、 [CDumpContext](../../mfc/reference/cdumpcontext-class.md)を 1 以上のオブジェクト。  
  
 ほとんどの用途のグローバル ヘルパー関数をこのクラスの呼び出しの一部のメンバー関数をカスタマイズする必要があります、`CArray`クラスです。 トピックを参照して[コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md) MFC マクロとグローバルに記載します。  
  
 配列クラスの派生は、リストの派生に似ています。  
  
 使用する方法の詳細についての`CArray`、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## <a name="requirements"></a>要件  
 `Header:`afxtempl.h  
  
##  <a name="a-nameadda--carrayadd"></a><a name="add"></a>CArray::Add  
 新しい要素を 1 ずつ配列の拡張は、配列の末尾に追加します。  
  
```  
INT_PTR Add(ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `ARG_TYPE`  
 この配列の要素を参照する引数の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 追加した要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 場合[SetSize](#setsize)と共に使用した、 `nGrowBy` 1、余分なメモリよりも大きい値を割り当てることができます。 ただし、上限の境界が唯一 1 ずつ増加します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&22;](../../mfc/codesnippet/cpp/carray-class_1.cpp)]  
  
##  <a name="a-nameappenda--carrayappend"></a><a name="append"></a>CArray::Append  
 別の end に&1; つの配列の内容を追加するには、このメンバー関数を呼び出します。  
  
```  
INT_PTR Append(const CArray& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 配列に追加する要素のソースです。  
  
### <a name="return-value"></a>戻り値  
 追加された最初の要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 配列は、同じ型でなければなりません。  
  
 必要に応じて、 **Append**配列に追加された要素を格納する余分なメモリを割り当てることがあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections 第&23;](../../mfc/codesnippet/cpp/carray-class_2.cpp)]  
  
##  <a name="a-namecarraya--carraycarray"></a><a name="carray"></a>CArray::CArray  
 空の配列を生成します。  
  
```  
CArray();
```  
  
### <a name="remarks"></a>コメント  
 配列は、一度に&1; つの要素を拡張します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&24;](../../mfc/codesnippet/cpp/carray-class_3.cpp)]  
  
##  <a name="a-namecopya--carraycopy"></a><a name="copy"></a>CArray::Copy  
 このメンバー関数を使用すると、別の&1; つの配列の要素をコピーできます。  
  
```  
void Copy(const CArray& src);
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 配列にコピーする要素のソースです。  
  
### <a name="remarks"></a>コメント  
 別の配列の要素を持つ&1; つの配列の要素を上書きするには、このメンバー関数を呼び出します。  
  
 **コピー**メモリは解放されません。 ただし、必要に応じて、**コピー**配列にコピーされた要素を格納する余分なメモリを割り当てることがあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&#25;](../../mfc/codesnippet/cpp/carray-class_4.cpp)]  
  
##  <a name="a-nameelementata--carrayelementat"></a><a name="elementat"></a>CArray::ElementAt  
 配列内の指定された要素に一時的な参照を返します。  
  
```  
TYPE& ElementAt(INT_PTR nIndex);  
const TYPE& ElementAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下[です](#getupperbound)します。  
  
### <a name="return-value"></a>戻り値  
 配列の要素への参照。  
  
### <a name="remarks"></a>コメント  
 配列の左側にある代入演算子の実装に使用されます。  
  
### <a name="example"></a>例  
  例を参照してください[GetSize](#getsize)します。  
  
##  <a name="a-namefreeextraa--carrayfreeextra"></a><a name="freeextra"></a>CArray::FreeExtra  
 配列が拡張されたときに割り当てられたすべての余分なメモリを解放します。  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>コメント  
 この関数には、サイズや配列の上限値には影響はありません。  
  
### <a name="example"></a>例  
  例を参照してください[GetData](#getdata)します。  
  
##  <a name="a-namegetata--carraygetat"></a><a name="getat"></a>CArray::GetAt  
 指定したインデックスにある配列要素を返します。  
  
```  
TYPE& GetAt(INT_PTR nIndex);  
const TYPE& GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 配列の要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下[です](#getupperbound)します。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置の配列の要素。  
  
### <a name="remarks"></a>コメント  
 によって返される値より大きい負の値または値を渡す`GetUpperBound`アサーションは失敗になります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&26;](../../mfc/codesnippet/cpp/carray-class_5.cpp)]  
  
##  <a name="a-namegetcounta--carraygetcount"></a><a name="getcount"></a>呼び出す  
 配列要素の数を返します。  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列内の項目の数。  
  
### <a name="remarks"></a>コメント  
 配列内の要素の数を取得するには、このメソッドを呼び出します。 インデックスが 0 から始まるので、サイズは、インデックスの最大値より大きい 1 になります。 このメソッドを呼び出すのと同じ結果が生成されます、[呼び出す](#getsize)メソッドです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&27;](../../mfc/codesnippet/cpp/carray-class_6.cpp)]  
  
##  <a name="a-namegetdataa--carraygetdata"></a><a name="getdata"></a>CArray::GetData  
 このメンバー関数を使用して、配列内の要素に直接アクセスします。  
  
```  
const TYPE* GetData() const; 
TYPE* GetData();
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 配列の要素の型を指定するテンプレート パラメーター。  
  
### <a name="return-value"></a>戻り値  
 配列の要素へのポインター。  
  
### <a name="remarks"></a>コメント  
 要素がない場合、 `GetData` null 値を返します。  
  
 呼び出すときに警告を使用して、配列の要素への直接アクセスより早く作業する際に役立つ、 `GetData`; 直接、エラーがあれば、配列の要素に影響します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&28;](../../mfc/codesnippet/cpp/carray-class_7.cpp)]  
  
##  <a name="a-namegetsizea--carraygetsize"></a><a name="getsize"></a>呼び出す  
 配列のサイズを返します。  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>コメント  
 インデックスが 0 から始まるので、サイズは、インデックスの最大値より大きい 1 になります。 このメソッドを呼び出すのと同じ結果が生成されます、[呼び出す](#getcount)メソッドです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&29;](../../mfc/codesnippet/cpp/carray-class_8.cpp)]  
  
##  <a name="a-namegetupperbounda--carraygetupperbound"></a><a name="getupperbound"></a>CArray::GetUpperBound  
 この配列の現在の上限値を返します。  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="remarks"></a>コメント  
 この関数が値 1 を返す配列のインデックスが 0 から始まるためより小さい`GetSize`します。  
  
 条件**です ()** = –&1; は、配列に要素が含まれないことを示します。  
  
### <a name="example"></a>例  
  例を参照してください[CArray::GetAt](#getat)します。  
  
##  <a name="a-nameinsertata--carrayinsertat"></a><a name="insertat"></a>CArray::InsertAt  
 最初のバージョン`InsertAt`配列内の指定したインデックス位置に&1; つの要素 (または要素の複数のコピー) を挿入します。  
  
```  
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,  
    INT_PTR nCount = 1);
 
void InsertAt(
    INT_PTR nStartIndex,  
    CArray* pNewArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 整数インデックス`GetUpperBound`します。  
  
 `ARG_TYPE`  
 この配列の要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に格納される要素。  
  
 `nCount`  
 この要素にする必要があります回数 (既定値は 1) が挿入されます。  
  
 `nStartIndex`  
 整数インデックス[です](#getupperbound)します。  
  
 `pNewArray`  
 この配列に追加する要素を含む別の配列。  
  
### <a name="remarks"></a>コメント  
 プロセスでは、その上がり、(インデックスをインクリメントする) をこのインデックスでは、既存の要素が上のすべての要素を移動します。  
  
 2 番目のバージョンから別のすべての要素の挿入`CArray`コレクションの開始位置として、`nStartIndex`位置。  
  
 `SetAt`関数の場合、これに対し、1 つの指定した配列の要素を置換し、任意の要素を移動しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&30;](../../mfc/codesnippet/cpp/carray-class_9.cpp)]  
  
##  <a name="a-nameisemptya--carrayisempty"></a><a name="isempty"></a>CArray::IsEmpty  
 配列が空かどうかを決定します。  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列に要素が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="a-nameoperatorata--carrayoperator-"></a><a name="operator_at"></a>CArray::operator\[\]  
 これらの添字演算子の便利な代替手段は、 [SetAt](#setat)と[GetAt](#getat)関数です。  
  
```  
TYPE& operator[](int_ptr nindex);  
const TYPE& operator[](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 この配列の要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 アクセスして、要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 れていない配列の最初の演算子と呼ばれる**const**右 (右辺値) と、代入ステートメントの左側 (左辺値) のいずれかで使用することがあります。 2 番目の場合と呼ばれる**const**右上のみ、配列で使用できます。  
  
 ライブラリのデバッグ バージョンでは、添字 (またはいずれかで、左、代入ステートメントの右側にある) が範囲外かどうかをアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&34;](../../mfc/codesnippet/cpp/carray-class_10.cpp)]  
  
##  <a name="a-namerelocateelementsa--carrayrelocateelements"></a><a name="relocateelements"></a>CArray::RelocateElements  
 配列の拡張または縮小時に新しいバッファーにデータを再配置します。  
  
```  
template<class TYPE, class ARG_TYPE>  
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,  
    const TYPE* pData,  
    INT_PTR nCount);
```  
  
### <a name="parameters"></a>パラメーター  
 `pNewData`  
 要素の配列を新しいバッファー。  
  
 `pData`  
 要素の古い配列。  
  
 `nCount`  
 元の配列要素の数。  
  
### <a name="remarks"></a>コメント  
 `pNewData`すべてを保持するのに十分では常に、`pData`要素。  
  
 [CArray](../../mfc/reference/carray-class.md)実装では、このメソッドを使用して、古いデータをコピー、新しいバッファー配列は、拡大または縮小する必要があります (と[SetSize](#setsize)または[FreeExtra](#freeextra)と呼ばれます)。 既定の実装は、データだけをコピーします。  
  
 配列の要素には、独自のメンバーのいずれかへのポインターが含まれています。 または、別の構造体、配列要素のいずれかへのポインターを格納する場合、ポインターは、既定のコピーでは更新されません。 この場合は、特殊化を実装することでポインターを修正できます`RelocateElements`に関連する型。 データのコピーを行う必要があります。  
  
##  <a name="a-nameremovealla--carrayremoveall"></a><a name="removeall"></a>CArray::RemoveAll  
 この配列からすべての要素を削除します。  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>コメント  
 配列が既に空の場合、関数も使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&31;](../../mfc/codesnippet/cpp/carray-class_11.cpp)]  
  
##  <a name="a-nameremoveata--carrayremoveat"></a><a name="removeat"></a>CArray::RemoveAt  
 配列内の指定したインデックスから始まる&1; つまたは複数の要素を削除します。  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下[です](#getupperbound)します。  
  
 `nCount`  
 削除する要素の数を指定します。  
  
### <a name="remarks"></a>コメント  
 プロセスでは、削除された要素の上のすべての要素をだけシフトします。 これをデクリメント上は、配列のバインドが、メモリは解放されません。  
  
 削除位置以降の配列に含まれる以上の要素を削除しようとする場合、ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections&#32;](../../mfc/codesnippet/cpp/carray-class_12.cpp)]  
  
##  <a name="a-namesetata--carraysetat"></a><a name="setat"></a>CArray::SetAt  
 指定したインデックス位置にある配列要素を設定します。  
  
```  
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下[です](#getupperbound)します。  
  
 `ARG_TYPE`  
 配列の要素を参照するために使用する引数の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 指定した位置に格納する新しい要素の値。  
  
### <a name="remarks"></a>コメント  
 `SetAt`拡張先の配列は発生しません。 使用[SetAtGrow](#setatgrow)する場合は自動的に拡張する配列。  
  
 インデックス値が配列内の有効な位置を表すことを確認する必要があります。 範囲外の場合は、ライブラリのデバッグ バージョンはアサートします。  
  
### <a name="example"></a>例  
  例を参照してください[GetAt](#getat)します。  
  
##  <a name="a-namesetatgrowa--carraysetatgrow"></a><a name="setatgrow"></a>CArray::SetAtGrow  
 指定したインデックス位置にある配列要素を設定します。  
  
```  
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数のインデックス。  
  
 `ARG_TYPE`  
 配列内の要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に追加する要素。 A **NULL**値を指定します。  
  
### <a name="remarks"></a>コメント  
 必要に応じて、配列を自動的に大きく (定義した上限の境界は新しい要素のために調整されます)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCCollections #&33;](../../mfc/codesnippet/cpp/carray-class_13.cpp)]  
  
##  <a name="a-namesetsizea--carraysetsize"></a><a name="setsize"></a>CArray::SetSize  
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
 新しいサイズが元のサイズより小さい場合は、配列が切り捨てられるし、すべての未使用メモリを解放します。  
  
 この関数を使用すると、配列を使用して開始する前に、配列のサイズを設定できます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 `nGrowBy`パラメーターは、配列は増え続けている中に内部メモリの割り当てに影響します。 使用は配列のサイズをによって報告されたに影響しない[GetSize](#getsize)と[です](#getupperbound)します。 既定値が使用されている場合、MFC はメモリの断片化を防ぐため、ほとんどの場合の効率を最適化するように計算にメモリを割り当てます。  
  
### <a name="example"></a>例  
  例を参照してください[GetData](#getdata)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)   
 [コレクション クラスのヘルパー](../../mfc/reference/collection-class-helpers.md)

