---
title: "Asyncbase::close メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dbdc52eec476b973c3d3549cfb0ff9413a46f6f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbaseclose-method"></a>AsyncBase::Close メソッド
非同期操作を閉じます。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>戻り値  
 操作が終了またはである場合は S_OK が閉じられました。それ以外の場合、E_ILLEGAL_STATE_CHANGE です。  
  
## <a name="remarks"></a>コメント  
 Close() は、IAsyncInfo::Close の既定の実装は、実際の作業は行われません。 実際には、非同期操作を閉じます OnClose() 純粋仮想メソッドをオーバーライドします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [AsyncBase クラス](../windows/asyncbase-class.md)