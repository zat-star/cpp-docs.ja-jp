---
title: "error_code クラス | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- error_code
- system_error/std::error_code
- system_error/std::error_code::value_type
- system_error/std::error_code::assign
- system_error/std::error_code::category
- system_error/std::error_code::clear
- system_error/std::error_code::default_error_condition
- system_error/std::error_code::message
- system_error/std::error_code::operator bool
dev_langs:
- C++
helpviewer_keywords:
- error_code class
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 82c70317383fe096c56b0d5b79bab24175d2872a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="errorcode-class"></a>error_code クラス
実装固有の低レベルなシステム エラーを表します。  
  
## <a name="syntax"></a>構文  
  
```
class error_code;
```  
  
## <a name="remarks"></a>コメント  
 `error_code` クラス型のオブジェクトは、エラー コード値を格納するほか、レポートされた低レベルのシステム エラーを説明するエラー コードの[カテゴリ](../standard-library/error-category-class.md)を表すオブジェクトを指すポインターも格納します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[error_code](#error_code)|`error_code` 型のオブジェクトを構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#value_type)|格納されたエラー コード値を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[assign](#assign)|エラー コードにエラー コード値とカテゴリを割り当てます。|  
|[category](#category)|エラー カテゴリを返します。|  
|[clear](#clear)|エラー コード値とカテゴリをクリアします。|  
|[default_error_condition](#default_error_condition)|既定のエラー条件を返します。|  
|[message](#message)|エラー コードの名前を返します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|`error_code` オブジェクト間の同等性をテストします。|  
|[operator!=](#op_neq)|`error_code` オブジェクト間の不等性をテストします。|  
|[operator<](#op_lt)|`error_code` オブジェクトが比較のために渡される `error_code` オブジェクトより小さいかどうかをテストします。|  
|[operator=](#op_eq)|`error_code` オブジェクトに新しい列挙値を代入します。|  
|[operator bool](#op_bool)|`error_code` 型の変数をキャストします。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<system_error>  
  
 **名前空間:** std  
  
##  <a name="assign"></a>  error_code::assign  
 エラー コードにエラー コード値とカテゴリを割り当てます。  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`val`|`error_code` に格納するエラー コード値。|  
|`_Cat`|`error_code` に格納するエラー カテゴリ。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、エラー コード値としての `val` と `_Cat` を指すポインターを格納します。  
  
##  <a name="category"></a>  error_code::category  
 エラー カテゴリを返します。  
  
```
const error_category& category() const;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="clear"></a>  error_code::clear  
 エラー コード値とカテゴリをクリアします。  
  
```
clear();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数はゼロ エラー コード値と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。  
  
##  <a name="default_error_condition"></a>  error_code::default_error_condition  
 既定のエラー条件を返します。  
  
```
error_condition default_error_condition() const;
```  
  
### <a name="return-value"></a>戻り値  
 [default_error_condition](../standard-library/error-category-class.md#default_error_condition) で指定された [error_condition](../standard-library/error-condition-class.md)。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `category().default_error_condition(value())` を返します。  
  
##  <a name="error_code"></a>  error_code::error_code  
 `error_code` 型のオブジェクトを構築します。  
  
```
error_code();

error_code(value_type val, const error_category& _Cat);

template <class _Enum>
error_code(_Enum _Errcode,
    typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`val`|`error_code` に格納するエラー コード値。|  
|`_Cat`|`error_code` に格納するエラー カテゴリ。|  
|`_Errcode`|`error_code` に格納する列挙値。|  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターはゼロ エラー コード値と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。  
  
 2 番目のコンストラクターは、エラー コード値としての `val` と [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8) を指すポインターを格納します。  
  
 3 番目のコンストラクターは、エラー コード値としての `(value_type)_Errcode` と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。  
  
##  <a name="message"></a>  error_code::message  
 エラー コードの名前を返します。  
  
```
string message() const;
```  
  
### <a name="return-value"></a>戻り値  
 エラー コードの名前を表す `string`。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `category().message(value())` を返します。  
  
##  <a name="op_eq_eq"></a>  error_code::operator==  
 `error_code` オブジェクト間の同等性をテストします。  
  
```
bool operator==(const error_code& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|等しいかどうかをテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`category() == right.category() && value == right.value()` を返します。  
  
##  <a name="op_neq"></a>  error_code::operator!=  
 `error_code` オブジェクト間の不等性をテストします。  
  
```
bool operator!=(const error_code& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|不等性をテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `error_code` オブジェクトが、`right` に渡される `error_code` オブジェクトに等しくない場合は **true**。それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`!(*this == right)` を返します。  
  
##  <a name="op_lt"></a>  error_code::operator&lt;  
 [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31) オブジェクトが比較のために渡された `error_code` オブジェクトより小さいかどうかをテストします。  
  
```
bool operator<(const error_code& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`right`|比較する error_code オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `error_code` オブジェクトが、比較対象として渡された `error_code` より小さい場合は **true**。それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、`category() < right.category() || category() == right.category() && value < right.value()` を返します。  
  
##  <a name="op_eq"></a>  error_code::operator=  
 [error_code](http://msdn.microsoft.com/en-us/09c6ef90-b6f8-430a-b584-e168716c7e31) オブジェクトに新しい列挙値を代入します。  
  
```
template <class _Enum>
typename enable_if<is_error_code_enum<_Enum>::value,
    error_code>::type&
 operator=(_Enum _Errcode);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Errcode`|`error_code` オブジェクトに代入する列挙値。|  
  
### <a name="return-value"></a>戻り値  
 メンバー関数によって新しい列挙値が代入される `error_code` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、エラー コード値としての `(value_type)_Errcode` と [generic_category](../standard-library/system-error-functions.md#generic_category) を指すポインターを格納します。 `*this` を返します。  
  
##  <a name="op_bool"></a>  error_code::operator bool  
 `error_code` 型の変数をキャストします。  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>戻り値  
 `error_code` オブジェクトのブール値。  
  
### <a name="remarks"></a>コメント  
 この演算子は、[値](#value)が 0 と等しくない場合に限り、`true` に変換できる値が返されます。 戻り値の型は、`void *` またはその他の既知のスカラー型ではなく、`bool` 型にのみ変換可能です。  
  
##  <a name="value"></a>  error_code::value  
 格納されたエラー コード値を返します。  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>戻り値  
 [value_type](#value_type) 型の格納されたエラー コード値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="value_type"></a>  error_code::value_type  
 格納されたエラー コード値を表す型。  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>コメント  
 この型定義は `int` のシノニムです。  
  
## <a name="see-also"></a>関連項目  
 [error_category クラス](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)




