---
title: "_AtlCreateWndData 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: a5b0811e88188bb29ef3153f739804cbdac66083
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)






