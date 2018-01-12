---
title: "_AtlCreateWndData 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs: C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99fc06e44f24b176482a6ff0b08ceed45b0f4f17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atlcreatewnddata-structure"></a>_AtlCreateWndData 構造体
この構造体には、ATL の windowing コードのクラス インスタンス データが含まれています。  
  
## <a name="syntax"></a>構文  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>メンバー  
 **m_pThis**  
 **この**ポインターをウィンドウ プロシージャに、クラスのインスタンスへのアクセスを取得するために使用します。  
  
 `m_dwThreadID`  
 現在のクラス インスタンスのスレッド ID。  
  
 **m_pNext**  
 次へのポインター`_AtlCreateWndData`オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>参照  
 [構造体](../../atl/reference/atl-structures.md)





