---
title: "CTypedPtrArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrArray
dev_langs:
- C++
helpviewer_keywords:
- pointer arrays
- CTypedPtrArray class
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
caps.latest.revision: 22
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
ms.openlocfilehash: 24b21d017d46cc88d7e243aff75ccf6383d2c870
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray クラス
`CPtrArray` クラスまたは `CObArray`クラスのオブジェクトに対してタイプセーフな "ラッパー" を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrArray : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 型指定されたポインター、配列クラスの基本クラスarray クラスにする必要があります (`CObArray`または`CPtrArray`)。  
  
 `TYPE`  
 基本クラスの配列に格納されている要素の型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrArray::Add](#add)|新しい要素を配列の末尾に追加します。 必要に応じて、配列を大きく|  
|[CTypedPtrArray::Append](#append)|1 つの配列の内容を別の末尾に追加します。 必要に応じて、配列を大きく|  
|[CTypedPtrArray::Copy](#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CTypedPtrArray::ElementAt](#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CTypedPtrArray::GetAt](#getat)|指定されたインデックス位置にある値を返します。|  
|[CTypedPtrArray::InsertAt](#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CTypedPtrArray::SetAt](#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CTypedPtrArray::SetAtGrow](#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrArray::operator](#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 使用すると`CTypedPtrArray`なく`CPtrArray`または`CObArray`C++ の型チェック機能により、一致しないポインター型によって発生したエラーを排除します。  
  
 さらに、`CTypedPtrArray`を使用した場合に必要がありますキャストの多くを実行するラッパー`CObArray`または`CPtrArray`です。  
  
 すべて`CTypedPtrArray`関数はインラインで、このテンプレートを使用しない変わらないサイズや、コードの処理速度。  
  
 使用する方法について`CTypedPtrArray`、記事を参照して[コレクション](../../mfc/collections.md)と[クラスのテンプレートに基づく](../../mfc/template-based-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BASE_CLASS`  
  
 `CTypedPtrArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="a-nameadda--ctypedptrarrayadd"></a><a name="add"></a>CTypedPtrArray::Add  
 このメンバー関数を呼び出す`BASE_CLASS` **:: 追加**します。  
  
```  
INT_PTR Add(TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 配列に追加する要素の型を指定するテンプレート パラメーター。  
  
 `newElement`  
 この配列に追加する要素。  
  
### <a name="return-value"></a>戻り値  
 追加した要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::Add](../../mfc/reference/cobarray-class.md#add)します。  
  
##  <a name="a-nameappenda--ctypedptrarrayappend"></a><a name="append"></a>CTypedPtrArray::Append  
 このメンバー関数を呼び出す`BASE_CLASS` **:: 追加**します。  
  
```  
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 型指定されたポインター、配列クラスの基本クラスarray クラスにする必要があります ( [CObArray](../../mfc/reference/cobarray-class.md)または[CPtrArray](../../mfc/reference/cptrarray-class.md))。  
  
 *型*  
 基本クラスの配列に格納されている要素の型。  
  
 *src*  
 配列に追加する要素のソースです。  
  
### <a name="return-value"></a>戻り値  
 追加された最初の要素のインデックス。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::Append](../../mfc/reference/cobarray-class.md#append)します。  
  
##  <a name="a-namecopya--ctypedptrarraycopy"></a><a name="copy"></a>CTypedPtrArray::Copy  
 このメンバー関数を呼び出す`BASE_CLASS` **:: コピー**します。  
  
```  
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```  
  
### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 型指定されたポインター、配列クラスの基本クラスarray クラスにする必要があります ( [CObArray](../../mfc/reference/cobarray-class.md)または[CPtrArray](../../mfc/reference/cptrarray-class.md))。  
  
 *型*  
 基本クラスの配列に格納されている要素の型。  
  
 *src*  
 配列にコピーする要素のソースです。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)します。  
  
##  <a name="a-nameelementata--ctypedptrarrayelementat"></a><a name="elementat"></a>CTypedPtrArray::ElementAt  
 このインライン関数が呼び出す`BASE_CLASS` **:: ElementAt**します。  
  
```  
TYPE& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 この配列に格納されている要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`BASE_CLASS` **:: です**します。  
  
### <a name="return-value"></a>戻り値  
 指定された位置にある要素への一時的な参照`nIndex`します。 この要素は、テンプレート パラメーターで指定された型*型*します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)します。  
  
##  <a name="a-namegetata--ctypedptrarraygetat"></a><a name="getat"></a>CTypedPtrArray::GetAt  
 このインライン関数が呼び出す`BASE_CLASS` **:: GetAt**します。  
  
```  
TYPE GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 配列に格納されている要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`BASE_CLASS` **:: です**します。  
  
### <a name="return-value"></a>戻り値  
 指定された位置にある要素のコピー`nIndex`します。 この要素は、テンプレート パラメーターで指定された型*型*します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください[CObArray::GetAt。](../../mfc/reference/cobarray-class.md#getat)  
  
##  <a name="a-nameinsertata--ctypedptrarrayinsertat"></a><a name="insertat"></a>CTypedPtrArray::InsertAt  
 このメンバー関数を呼び出す`BASE_CLASS` **:: InsertAt**します。  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    TYPE newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 整数インデックス[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)します。  
  
 *型*  
 基本クラスの配列に格納されている要素の型。  
  
 `newElement`  
 この配列に格納されるオブジェクトのポインター。 A`newElement`値の**NULL**は許可されています。  
  
 `nCount`  
 この要素にする必要があります回数 (既定値は 1) が挿入されます。  
  
 `nStartIndex`  
 整数インデックス`CObArray::GetUpperBound`します。  
  
 `BASE_CLASS`  
 型指定されたポインター、配列クラスの基本クラスarray クラスにする必要があります ( [CObArray](../../mfc/reference/cobarray-class.md)または[CPtrArray](../../mfc/reference/cptrarray-class.md))。  
  
 `pNewArray`  
 この配列に追加する要素を含む別の配列。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)します。  
  
##  <a name="a-nameoperatorata--ctypedptrarrayoperator--"></a><a name="operator_at"></a>CTypedPtrArray::operator  
 これらのインライン演算子を呼び出す`BASE_CLASS` **:: 演算子**します。  
  
```  
TYPE& operator[ ](int_ptr nindex);  
TYPE operator[ ](int_ptr nindex) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *型*  
 配列に格納されている要素の型を指定するテンプレート パラメーター。  
  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下`BASE_CLASS` **:: です**します。  
  
### <a name="remarks"></a>コメント  
 れていない配列の最初の演算子と呼ばれる**const**右側の (右辺値) と、代入ステートメントの左側 (左辺値) のいずれかで使用できます。 2 番目が呼び出されます。 **const**配列、は、右辺でのみ使用できます。  
  
 ライブラリのデバッグ バージョンでは、添字 (またはいずれかで、左、代入ステートメントの右側にある) が範囲外かどうかをアサートします。  
  
##  <a name="a-namesetata--ctypedptrarraysetat"></a><a name="setat"></a>CTypedPtrArray::SetAt  
 このメンバー関数を呼び出す`BASE_CLASS` **:: SetAt**します。  
  
```  
void SetAt(
    INT_PTR nIndex,  
    TYPE ptr);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数インデックスによって返される値以下[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)します。  
  
 *型*  
 基本クラスの配列に格納されている要素の型。  
  
 *ptr*  
 配列、nIndex 位置に挿入される要素へのポインター。 NULL 値が許可されるとします。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)します。  
  
##  <a name="a-namesetatgrowa--ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>CTypedPtrArray::SetAtGrow  
 このメンバー関数を呼び出す`BASE_CLASS` **:: SetAtGrow**します。  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    TYPE newElement);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 以上である整数のインデックス。  
  
 *型*  
 基本クラスの配列に格納されている要素の型。  
  
 `newElement`  
 この配列に追加するオブジェクトのポインター。 A **NULL**値を指定します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPtrArray クラス](../../mfc/reference/cptrarray-class.md)   
 [CObArray クラス](../../mfc/reference/cobarray-class.md)

