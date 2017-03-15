---
title: "error_category クラス | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::error_category
- system_error/std::error_category
- error_category
- std.error_category
dev_langs:
- C++
helpviewer_keywords:
- error_category class
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 7700ffce8b04f9caad33c08f03f0585c29a43efd
ms.lasthandoff: 02/24/2017

---
# <a name="errorcategory-class"></a>error_category クラス
エラー コードのカテゴリを表すオブジェクトの抽象的な共通基底を表します。  
  
## <a name="syntax"></a>構文  
  
```
class error_category;
```  
  
## <a name="remarks"></a>コメント  
 定義済みの&2; つのオブジェクト [generic_category](../standard-library/system-error-functions.md#generic_category) および [system_category](../standard-library/system-error-functions.md#system_category) によって `error_category` が実装されます。  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[value_type](#error_category__value_type)|格納されたエラー コード値を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[default_error_condition](#error_category__default_error_condition)|エラー条件オブジェクトのエラー コード値を格納します。|  
|[equivalent](#error_category__equivalent)|エラー オブジェクトが同等であるかどうかを示す値を返します。|  
|[message](#error_category__message)|指定したエラー コードの名前を返します。|  
|[name](#error_category__name)|カテゴリの名前を返します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator==](#error_category__operator_eq_eq)|`error_category` オブジェクト間の同等性をテストします。|  
|[operator!=](#error_category__operator_neq)|`error_category` オブジェクト間の不等性をテストします。|  
|[operator<](#error_category__operator_lt_)|[error_category](../standard-library/error-category-class.md) オブジェクトが比較のために渡される `error_category` オブジェクトより小さいかどうかをテストします。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
##  <a name="a-nameerrorcategorydefaulterrorconditiona--errorcategorydefaulterrorcondition"></a><a name="error_category__default_error_condition"></a>  error_category::default_error_condition  
 エラー条件オブジェクトのエラー コード値を格納します。  
  
```
virtual error_condition default_error_condition(int _Errval) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Errval`|[error_condition](../standard-library/error-condition-class.md) オブジェクトに格納するエラー コード値。|  
  
### <a name="return-value"></a>戻り値  
 `error_condition(_Errval, *this)` を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameerrorcategoryequivalenta--errorcategoryequivalent"></a><a name="error_category__equivalent"></a>  error_category::equivalent  
 エラー オブジェクトが同等であるかどうかを示す値を返します。  
  
```
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Errval`|比較するエラー コード値。|  
|`_Cond`|比較する [error_condition](../standard-library/error-condition-class.md) オブジェクト。|  
|`_Code`|比較する [error_code](../standard-library/error-code-class.md) オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 カテゴリと値が等しい場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は `*this == _Cond.category() && _Cond.value() == _Errval` を返します。  
  
 2 番目のメンバー関数は `*this == _Code.category() && _Code.value() == _Errval` を返します。  
  
##  <a name="a-nameerrorcategorymessagea--errorcategorymessage"></a><a name="error_category__message"></a>  error_category::message  
 指定したエラー コードの名前を返します。  
  
```
virtual string message(error_code::value_type val) const = 0;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`val`|記述するエラー コード値。|  
  
### <a name="return-value"></a>戻り値  
 カテゴリのエラー コード`val` のわかりやすい名前を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameerrorcategorynamea--errorcategoryname"></a><a name="error_category__name"></a>  error_category::name  
 カテゴリの名前を返します。  
  
```
virtual const char *name() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 カテゴリの名前を、null 終端バイト文字列として返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameerrorcategoryoperatoreqeqa--errorcategoryoperator"></a><a name="error_category__operator_eq_eq"></a>  error_category::operator==  
 `error_category` オブジェクト間の同等性をテストします。  
  
```
bool operator==(const error_category& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|等しいかどうかをテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`this == &right` を返します。  
  
##  <a name="a-nameerrorcategoryoperatorneqa--errorcategoryoperator"></a><a name="error_category__operator_neq"></a>  error_category::operator!=  
 `error_category` オブジェクト間の不等性をテストします。  
  
```
bool operator!=(const error_category& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|不等性をテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `error_category` オブジェクトが、`right` に渡される `error_category` オブジェクトに等しくない場合は **true**。それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`(!*this == right)` を返します。  
  
##  <a name="a-nameerrorcategoryoperatorlta--errorcategoryoperatorlt"></a><a name="error_category__operator_lt_"></a>  error_category::operator&lt;  
 [error_category](../standard-library/error-category-class.md) オブジェクトが比較のために渡される `error_category` オブジェクトより小さいかどうかをテストします。  
  
```
bool operator<(const error_category& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|比較される `error_category` オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `error_category` オブジェクトが、比較対象として渡された `error_category` より小さい場合は **true**。それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`this < &right` を返します。  
  
##  <a name="a-nameerrorcategoryvaluetypea--errorcategoryvaluetype"></a><a name="error_category__value_type"></a>  error_category::value_type  
 格納されたエラー コード値を表す型。  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>コメント  
 この型定義は `int` のシノニムです。  
  
## <a name="see-also"></a>関連項目  
 [<system_error>](../standard-library/system-error.md)




