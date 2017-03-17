---
title: "CComAutoDeleteCriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: eb53a0966d29759bbe7513f6042f72a280801707
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection クラス
このクラスは、取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>コメント  
 `CComAutoDeleteCriticalSection`クラスから派生[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)します。 ただし、`CComAutoDeleteCriticalSection`オーバーライド、[用語](ccomsafedeletecriticalsection-class.md#term)メソッドを`private`アクセスで、強制的にのみこのクラスのインスタンスのスコープ外に出るまたは明示的に削除されたときメモリから発生する内部メモリ クリーンアップします。  

  
 このクラスには、基本クラスに対して追加のメソッドはありません。 参照してください[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)と[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)詳細については、クリティカル セクションのヘルパー クラスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
## <a name="see-also"></a>関連項目  
 [CComSafeDeleteCriticalSection クラス](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

