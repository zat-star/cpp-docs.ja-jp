---
title: "CTypedPtrMap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections
- template classes, CTypedPtrMap class
- maps
- CTypedPtrMap class
- pointer maps
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
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
ms.openlocfilehash: 919d751c6ffe4b10ffad047f1b6be832bf49a1af
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap クラス
ポインター マップ クラス `CMapPtrToPtr`、 `CMapPtrToWord`、 `CMapWordToPtr`、および `CMapStringToPtr`のオブジェクトに対してタイプ セーフな "ラップ" が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 型指定されたポインター マップ クラスの基本クラスポインター マップ クラスである必要があります ( `CMapPtrToPtr`、 `CMapPtrToWord`、 `CMapWordToPtr`、または`CMapStringToPtr`)。  
  
 `KEY`  
 マップのキーとして使用されるオブジェクトのクラスです。  
  
 `VALUE`  
 マップに格納されているオブジェクトのクラスです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|反復処理するためには、次の要素を取得します。|  
|[CTypedPtrMap::Lookup](#lookup)|返します。、`KEY`に基づいて、`VALUE`です。|  
|[CTypedPtrMap::RemoveKey](#removekey)|キーによって指定される要素を削除します。|  
|[CTypedPtrMap::SetAt](#setat)|マップに要素を挿入します。一致するキーが見つかった場合は、既存の要素を置換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CTypedPtrMap::operator](#operator_at)|マップに要素を挿入します。|  
  
## <a name="remarks"></a>コメント  
 使用すると`CTypedPtrMap`C++ の型チェック機能により、一致しないポインター型によって発生したエラーを排除します。  
  
 すべて`CTypedPtrMap`関数はインラインで、このテンプレートを使用しない変わらないサイズや、コードの処理速度。  
  
 使用する方法について`CTypedPtrMap`、記事を参照して[コレクション](../../mfc/collections.md)と[クラスのテンプレートに基づく](../../mfc/template-based-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtempl.h  
  
##  <a name="a-namegetnextassoca--ctypedptrmapgetnextassoc"></a><a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 位置にあるマップ要素を取得`rNextPosition`、し、更新`rNextPosition`に、マップ内の次の要素を参照してください。  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rPosition`  
 参照を指定、**位置**以前から返される値`GetNextAssoc`または`BASE_CLASS` **:: 中**呼び出します。  
  
 *キー*  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 `rKey`  
 取得した要素の返されたキーを指定します。  
  
 *値*  
 マップの値の型を指定するテンプレート パラメーター。  
  
 `rValue`  
 取得した要素の戻り値を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、マップ内のすべての要素を反復処理する方が適しています。 位置シーケンスがないとは限りませんと同じキー値のシーケンスに注意してください。  
  
 取得した要素が、マップ内の最後の新しい値の`rNextPosition`に設定されている**NULL**します。  
  
 このインライン関数が呼び出す`BASE_CLASS` **:: たどる**します。  
  
##  <a name="a-namelookupa--ctypedptrmaplookup"></a><a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`ハッシュ アルゴリズムを使用して、すばやく正確に一致するキーを使用してマップの要素を検索します。  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `BASE_CLASS`  
 このマップのクラスの基本クラスを指定するテンプレート パラメーター。  
  
 `key`  
 検索する要素のキー。  
  
 *値*  
 このマップに格納された値の型を指定するテンプレート パラメーター。  
  
 `rValue`  
 取得した要素の戻り値を指定します。  
  
### <a name="return-value"></a>戻り値  
 要素が見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このインライン関数が呼び出す`BASE_CLASS` **:: ルックアップ**します。  
  
##  <a name="a-nameoperatorata--ctypedptrmapoperator--"></a><a name="operator_at"></a>CTypedPtrMap::operator  
 この演算子は、代入ステートメント (左辺値) の左側にのみ使用できます。  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>パラメーター  
 *値*  
 このマップに格納された値の型を指定するテンプレート パラメーター。  
  
 `BASE_CLASS`  
 このマップのクラスの基本クラスを指定するテンプレート パラメーター。  
  
 `key`  
 検索したり、マップで作成する要素のキー。  
  
### <a name="remarks"></a>コメント  
 指定したキーにマップ要素が存在しない、新しい要素が作成されます。 ない「右側」(右辺値) にこの演算子と同じキーがマップに含まれていない可能性があります可能性があるため。 使用して、`Lookup`メンバー関数要素を取得します。  
  
##  <a name="a-nameremovekeya--ctypedptrmapremovekey"></a><a name="removekey"></a>CTypedPtrMap::RemoveKey  
 このメンバー関数を呼び出す`BASE_CLASS` **:: は**です。  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>パラメーター  
 *キー*  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 `key`  
 削除する要素をキーします。  
  
### <a name="return-value"></a>戻り値  
 エントリが見つかり、正常に削除された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)します。  
  
##  <a name="a-namesetata--ctypedptrmapsetat"></a><a name="setat"></a>CTypedPtrMap::SetAt  
 このメンバー関数を呼び出す`BASE_CLASS` **:: SetAt**します。  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *キー*  
 マップのキーの種類を指定するテンプレート パラメーター。  
  
 `key`  
 新しい値のキーの値を指定します。  
  
 `newValue`  
 新しい要素の値であるオブジェクトのポインターを指定します。  
  
### <a name="remarks"></a>コメント  
 詳細についてを参照してください。 [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr クラス](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord クラス](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapWordToPtr クラス](../../mfc/reference/cmapwordtoptr-class.md)   
 [CMapStringToPtr クラス](../../mfc/reference/cmapstringtoptr-class.md)

