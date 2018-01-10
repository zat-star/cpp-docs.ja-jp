---
title: "CDefaultHashTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs: C++
helpviewer_keywords: CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2407ffdd5d8ea327cd4669f2c33ccda5e0246d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits クラス
このクラスは、ハッシュ値を計算するための静的関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(静的)この関数では、指定された要素のハッシュ値を計算します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには、指定された要素のハッシュ値を返す 1 つの静的関数が含まれています。 このクラスは、によって使用されて、 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 この関数では、指定された要素のハッシュ値を計算します。  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 要素。  
  
### <a name="return-value"></a>戻り値  
 ハッシュ値を返します。  
  
### <a name="remarks"></a>コメント  
 既定のハッシュ アルゴリズムは非常に単純: 戻り値は、要素数。 複雑なアルゴリズムが必要な場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
