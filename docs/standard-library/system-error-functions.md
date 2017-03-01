---
title: "&lt;system_error&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 43098f6f9276c9a66aaa7a30c95a6696e33f8429
ms.lasthandoff: 02/24/2017

---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; 関数
||||  
|-|-|-|  
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|  
|[system_category](#system_category)|  
  
##  <a name="a-namegenericcategorya--genericcategory"></a><a name="generic_category"></a>  generic_category  
 一般的なエラーのカテゴリを表します。  
  
```
extern const error_category& generic_category();
```  
  
### <a name="remarks"></a>コメント  
 `generic_categor`y オブジェクトは、[error_category](../standard-library/error-category-class.md) を実装したものです。  
  
##  <a name="a-namemakeerrorcodea--makeerrorcode"></a><a name="make_error_code"></a>  make_error_code  
 エラー コード オブジェクトを作成します。  
  
```
error_code make_error_code(generic_errno _Errno);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Errno`|エラー コード オブジェクトに格納する列挙値。|  
  
### <a name="return-value"></a>戻り値  
 エラー コード オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemakeerrorconditiona--makeerrorcondition"></a><a name="make_error_condition"></a>  make_error_condition  
 エラー条件オブジェクトを作成します。  
  
```
error_condition make_error_condition(generic_errno _Errno);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Errno`|エラー条件オブジェクトに格納する列挙値。|  
  
### <a name="return-value"></a>戻り値  
 エラー条件オブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesystemcategorya--systemcategory"></a><a name="system_category"></a>  system_category  
 低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。  
  
```
extern const error_category& system_category();
```  
  
### <a name="remarks"></a>コメント  
 `system_categor`y オブジェクトは、[error_category](../standard-library/error-category-class.md) を実装したものです。  
  
## <a name="see-also"></a>関連項目  
 [<system_error>](../standard-library/system-error.md)




