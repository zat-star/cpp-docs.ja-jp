---
title: "CDefaultCharTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 12991cfcf1ac96808a0315899d01ce3012324dc6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits クラス
このクラスは、大文字と小文字を変換するための&2; つの静的関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(静的)この関数では、文字を大文字に変換します。|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(静的)文字を小文字に変換するには、この関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには、クラスによって使用されている関数[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="chartolower"></a>CDefaultCharTraits::CharToLower  
 文字を小文字に変換するには、この関数を呼び出します。  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 小文字に変換する文字。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities #&132;](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="chartoupper"></a>CDefaultCharTraits::CharToUpper  
 この関数では、文字を大文字に変換します。  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 大文字に変換する文字。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

