---
title: "CAtlArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
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
ms.openlocfilehash: 5fe987e428fc0dcf3e40bfb16aa26bcb90339aff
ms.lasthandoff: 02/24/2017

---
# <a name="catlarray-class"></a>CAtlArray クラス
このクラスは、配列オブジェクトを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```  
  
#### <a name="parameters"></a>パラメーター  
 *E*  
 配列に格納されるデータの型。  
  
 *ETraits*  
 コピーまたは要素を移動するために使用するコードです。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[[追加]](#add)|配列オブジェクトに要素を追加するには、このメソッドを呼び出します。|  
|[追加](#append)|別の end に&1; つの配列の内容を追加するには、このメソッドを呼び出します。|  
|[AssertValid](#assertvalid)|Array オブジェクトが有効であることを確認するには、このメソッドを呼び出します。|  
|[CAtlArray](#catlarray)|コンストラクターです。|  
|[~ CAtlArray](#dtor)|デストラクターです。|  
|[コピー](#copy)|別の&1; つの配列の要素をコピーするには、このメソッドを呼び出します。|  
|[FreeExtra](#freeextra)|配列から空の要素を削除するには、このメソッドを呼び出します。|  
|[GetAt](#getat)|配列オブジェクトから&1; つの要素を取得するには、このメソッドを呼び出します。|  
|[GetCount](#getcount)|このメソッドでは、配列に格納されている要素の数を取得します。|  
|[GetData](#getdata)|このメソッドを呼び出して配列の最初の要素へのポインターを返します。|  
|[InsertArrayAt](#insertarrayat)|1 つの配列を挿入するには、このメソッドを呼び出します。|  
|[InsertAt](#insertat)|配列オブジェクトに新しい要素 (または要素の複数のコピー) を挿入するには、このメソッドを呼び出します。|  
|[IsEmpty](#isempty)|配列が空の場合は、テストするには、このメソッドを呼び出します。|  
|[RemoveAll](#removeall)|配列オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。|  
|[RemoveAt](#removeat)|配列から&1; つまたは複数の要素を削除するには、このメソッドを呼び出します。|  
|[SetAt](#setat)|配列オブジェクト内に要素の値を設定するには、このメソッドを呼び出します。|  
|[SetAtGrow](#setatgrow)|必要に応じて、配列を展開する、配列オブジェクト内の要素の値を設定するには、このメソッドを呼び出します。|  
|[SetCount](#setcount)|配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子](#operator_at)|配列の要素への参照を返すには、この演算子を呼び出します。|  

  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[INARGTYPE](#inargtype)|データは、配列に要素を追加するために使用する型します。|  
|[OUTARGTYPE](#outargtype)|配列から要素を取得するために使用するデータ型。|  
  
## <a name="remarks"></a>コメント  
 **CAtlArray**を作成して、ユーザー定義型の要素の配列を管理するメソッドを提供します。 標準 C 配列に似ていますが、 **CAtlArray**オブジェクトを動的に縮小および必要に応じて大きくなります。 配列のインデックスは常に 0 から開始し、上限の境界を修正、または新しい要素が追加される順に展開を許可します。  
  
 配列の要素、ATL クラスの数が少ない[CSimpleArray](../../atl/reference/csimplearray-class.md)使用できます。  
  
 **CAtlArray** MFC のと密接な関係**CArray**クラスし、はシリアル化をサポートしていないが、MFC プロジェクトでは機能します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="add"></a>CAtlArray::Add  
 配列オブジェクトに要素を追加するには、このメソッドを呼び出します。  
  
```
size_t Add(INARGTYPE element);
size_t Add();
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 追加した要素のインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 新しい要素は、配列の末尾に追加されます。 要素が提供されない場合、空の要素を追加します。つまり、実際の要素が追加されたものとしてのサイズ、配列が増加します。 操作が失敗した場合、[ため](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)E_OUTOFMEMORY 引数で呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#1;](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]  
  
##  <a name="append"></a>CAtlArray::Append  
 別の end に&1; つの配列の内容を追加するには、このメソッドを呼び出します。  
  
```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `aSrc`  
 追加する配列。  
  
### <a name="return-value"></a>戻り値  
 追加された最初の要素のインデックスを返します。  
  
### <a name="remarks"></a>コメント  
 指定した配列内の要素は、既存の配列の末尾に追加されます。 必要に応じて、メモリが新しい要素のために割り当てられます。  
  
 配列自体に追加することはできませんし、同じ型の配列があります。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`引数が有効な配列ではない場合、または`aSrc`は同じオブジェクトを参照します。 リリース ビルドで、予期しない動作を無効な引数があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#2;](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]  
  
##  <a name="assertvalid"></a>CAtlArray::AssertValid  
 Array オブジェクトが有効であることを確認するには、このメソッドを呼び出します。  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>コメント  
 Array オブジェクトが有効でない場合`ATLASSERT`はアサーションをスローします。 このメソッドは _DEBUG が定義されている場合にのみ使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#3;](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]  
  
##  <a name="catlarray"></a>CAtlArray::CAtlArray  
 コンストラクターです。  
  
```
CAtlArray() throw();
```  
  
### <a name="remarks"></a>コメント  
 配列オブジェクトを初期化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&4;](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]  
  
##  <a name="dtor"></a>CAtlArray:: ~ CAtlArray  
 デストラクターです。  
  
```
~CAtlArray() throw();
```  
  
### <a name="remarks"></a>コメント  
 配列オブジェクトによって使用されているリソースを解放します。  
  
##  <a name="copy"></a>CAtlArray::Copy  
 別の&1; つの配列の要素をコピーするには、このメソッドを呼び出します。  
  
```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `aSrc`  
 配列にコピーする要素のソースです。  
  
### <a name="remarks"></a>コメント  
 別の配列の要素を持つ&1; つの配列の要素を上書きするには、このメソッドを呼び出します。 必要に応じて、メモリが新しい要素のために割り当てられます。 それ自体に、配列の要素をコピーすることはできません。  
  
 配列の既存の内容を保持する場合を使用して[CAtlArray::Append](#append)代わりにします。  
  
 デバッグ ビルドで、ATLASSERT が発生既存`CAtlArray`オブジェクトが有効でない場合、または`aSrc`は同じオブジェクトを参照します。 リリース ビルドで、予期しない動作を無効な引数があります。  
  
> [!NOTE]
> `CAtlArray::Copy`作成した要素から成る配列をサポートしていない、 [CAutoPtr](../../atl/reference/cautoptr-class.md)クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#5;](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]  
  
##  <a name="freeextra"></a>CAtlArray::FreeExtra  
 配列から空の要素を削除するには、このメソッドを呼び出します。  
  
```
void FreeExtra() throw();
```  
  
### <a name="remarks"></a>コメント  
 空の要素が削除されますが、サイズと配列の上限は変更されません。  
  
 デバッグ ビルドでは CAtlArray オブジェクトが有効でない場合、または配列の最大サイズを超えてしまう場合、atlassert されます。  
  
##  <a name="getat"></a>CAtlArray::GetAt  
 呼び出しには、このメソッドは、配列オブジェクトから&1; つの要素を取得します。  
  
```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 返される配列要素のインデックス値。  
  
### <a name="return-value"></a>戻り値  
 要求された配列の要素への参照を返します。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドは atlassert 場合`iElement`配列内の要素数を超えています。 リリース ビルドで、予期しない動作を無効な引数があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&6;](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]  
  
##  <a name="getcount"></a>CAtlArray::GetCount  
 このメソッドでは、配列に格納されている要素の数を取得します。  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 配列に格納されている要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 によって、値が返される配列の最初の要素が 0 の位置に格納される、`GetCount`が常に 1 より大きいインデックスの最大値。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlArray::GetAt](#getat)します。  
  
##  <a name="getdata"></a>CAtlArray::GetData  
 このメソッドを呼び出して配列の最初の要素へのポインターを返します。  
  
```
E* GetData() throw();
const E* GetData() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 配列内の最初の要素を格納するメモリ位置へのポインターを返します。 使用可能な要素が存在しない場合は、NULL が返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#7;](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]  
  
##  <a name="inargtype"></a>CAtlArray::INARGTYPE  
 データは、配列に要素を追加するために使用する型します。  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertarrayat"></a>CAtlArray::InsertArrayAt  
 1 つの配列を挿入するには、このメソッドを呼び出します。  
  
```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `iStart`  
 配列が挿入されるインデックスです。  
  
 `paNew`  
 挿入先の配列。  
  
### <a name="remarks"></a>コメント  
 配列から要素`paNew`要素で始まる配列にコピーされます`iStart`します。 既存の配列要素は、上書きされないようにに移動されます。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが有効でない場合は、`paNew`ポインターが NULL または無効です。  
  
> [!NOTE]
> `CAtlArray::InsertArrayAt`作成した要素から成る配列をサポートしていない、 [CAutoPtr](../../atl/reference/cautoptr-class.md)クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#8;](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]  
  
##  <a name="insertat"></a>CAtlArray::InsertAt  
 配列オブジェクトに新しい要素 (または要素の複数のコピー) を挿入するには、このメソッドを呼び出します。  
  
```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 要素または要素が挿入されるインデックス。  
  
 `element`  
 要素または挿入する要素の値。  
  
 `nCount`  
 追加する要素の数。  
  
### <a name="remarks"></a>コメント  
 インデックスで開始する配列に&1; つまたは複数の要素を挿入`iElement`します。 既存の要素は、上書きされないようにに移動されます。  
  
 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが無効、追加する要素の数が&0;、またはを格納する配列の要素の合計数が大きすぎます。 製品版ビルドで無効なパラメーターを渡すことと、予期しない結果が発生する可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#9;](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]  
  
##  <a name="isempty"></a>CAtlArray::IsEmpty  
 配列が空の場合は、テストするには、このメソッドを呼び出します。  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 配列が false の場合それ以外の場合、空の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 配列は、要素が含まれていない場合は、空であると言われます。 したがって、配列に空の要素が含まれている場合でも空ではないです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#10;](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]  
  
##  <a name="operator_at"></a>CAtlArray::operator  
 配列の要素への参照を返すには、この演算子を呼び出します。  
  
```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 返される配列要素のインデックス値。  
  
### <a name="return-value"></a>戻り値  
 要求された配列の要素への参照を返します。  
  
### <a name="remarks"></a>コメント  
 同様の機能を実行[CAtlArray::GetAt](#getat)します。 MFC クラスとは異なり[CArray](../../mfc/reference/carray-class.md)の代わりに、この演算子を使用できません[CAtlArray::SetAt](#setat)します。  
  
 デバッグ ビルドは atlassert 場合`iElement`配列内の要素の合計数を超えています。 製品版ビルドでは、予期しない結果が無効なパラメーターにあります。  
  
##  <a name="outargtype"></a>CAtlArray::OUTARGTYPE  
 配列から要素を取得するために使用するデータ型。  
  
```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```  
  
##  <a name="removeall"></a>CAtlArray::RemoveAll  
 配列オブジェクトからすべての要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>コメント  
 配列オブジェクトからすべての要素を削除します。  
  
 このメソッドを呼び出す[CAtlArray::SetCount](#setcount)配列のサイズを変更して、後で、割り当てられたメモリを解放します。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlArray::IsEmpty](#isempty)します。  
  
##  <a name="removeat"></a>CAtlArray::RemoveAt  
 配列から&1; つまたは複数の要素を削除するには、このメソッドを呼び出します。  
  
```
void RemoveAt(size_t iElement, size_t nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 削除する最初の要素のインデックス。  
  
 `nCount`  
 削除する要素の数を指定します。  
  
### <a name="remarks"></a>コメント  
 配列から&1; つまたは複数の要素を削除します。 残りの要素は下に移動します。 上限の境界がデクリメントが、メモリは、呼び出されるまで解放されない[CAtlArray::FreeExtra](#freeextra)されます。  
  
 デバッグ ビルドで、ATLASSERT が発生、`CAtlArray`オブジェクトが有効でない場合の合計`iElement`と`nCount`配列内の要素の合計数を超えています。 製品版ビルドでは、予期しない結果が無効なパラメーターにあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#11;](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]  
  
##  <a name="setat"></a>CAtlArray::SetAt  
 配列オブジェクト内に要素の値を設定するには、このメソッドを呼び出します。  
  
```
void SetAt(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 設定する配列要素を指すインデックス。  
  
 `element`  
 指定した要素の新しい値。  
  
### <a name="remarks"></a>コメント  
 デバッグ ビルドは atlassert 場合`iElement`配列内の要素数を超えています。 製品版ビルドで、無効なパラメーターが予期しない結果があります。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlArray::GetAt](#getat)します。  
  
##  <a name="setcount"></a>CAtlArray::SetCount  
 配列オブジェクトのサイズを設定するには、このメソッドを呼び出します。  
  
```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewSize`  
 配列の必要なサイズです。  
  
 `nGrowBy`  
 値を決定するため、バッファーの大きさ。 値-1 の場合、使用する内部で計算される値。  
  
### <a name="return-value"></a>戻り値  
 配列の場合、false を正常にサイズを変更したそれ以外の場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 配列を増加またはサイズが減少します。 増やされた場合は、空の要素が配列に追加されます。 低下している場合は、最大のインデックスを持つ要素が削除され、メモリが解放されます。  
  
 このメソッドを使用すると、使用する前に、配列のサイズを設定できます。 場合`SetCount`は使用されません要素を追加するプロセス: され、その後のメモリ割り当ての実行-パフォーマンスが低下して、メモリが断片化されます。  
  
### <a name="example"></a>例  
 例を参照してください[CAtlArray::GetData](#getdata)します。  
  
##  <a name="setatgrow"></a>CAtlArray::SetAtGrow  
 必要に応じて、配列を展開する、配列オブジェクト内の要素の値を設定するには、このメソッドを呼び出します。  
  
```
void SetAtGrow(size_t iElement, INARGTYPE element);
```  
  
### <a name="parameters"></a>パラメーター  
 `iElement`  
 設定する配列要素を指すインデックス。  
  
 `element`  
 指定した要素の新しい値。  
  
### <a name="remarks"></a>コメント  
 インデックスが指す要素の値に置き換えます。 場合`iElement`が現在のサイズより大きい、配列の配列は自動的に増加する呼び出しを使用して[CAtlArray::SetCount](#setcount)します。 デバッグ ビルドは atlassert 場合、`CAtlArray`オブジェクトが無効です。 製品版ビルドでは、予期しない結果が無効なパラメーターにあります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities&#12;](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MMXSwarm サンプル](../../visual-cpp-samples.md)   
 [DynamicConsumer サンプル](../../visual-cpp-samples.md)   
 [UpdatePV サンプル](../../visual-cpp-samples.md)   
 [マーキーのサンプル](../../visual-cpp-samples.md)   
 [CArray クラス](../../mfc/reference/carray-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

