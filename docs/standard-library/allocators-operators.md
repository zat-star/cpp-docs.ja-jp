---
title: "&lt;allocators&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0a2da6c72e8900c0cea86c30c6b8511e6b256ff9
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 演算子
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 指定したクラスのアロケーター オブジェクト間の非等値をテストします。  
  
```
template <class Type, class Sync>  
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|不等性をテストする一方のアロケーター オブジェクト。|  
|`right`|不等性をテストする一方のアロケーター オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 アロケーター オブジェクトが等しくない場合は **true**、アロケーター オブジェクトが等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 テンプレート演算子は `!(left == right)` を返します。  
  
##  <a name="op_eq_eq"></a>  operator==  
 指定したクラスのアロケーター オブジェクト間の等値をテストします。  
  
```
template <class Type, class Sync>  
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|等しいかどうかをテストする一方のアロケーター オブジェクト。|  
|`right`|等しいかどうかをテストする一方のアロケーター オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 アロケーター オブジェクトが等しい場合は **true**、アロケーター オブジェクトが等しくない場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このテンプレート演算子は `left.equals(right)` を返します。  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




