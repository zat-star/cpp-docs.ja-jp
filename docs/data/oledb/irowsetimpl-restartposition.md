---
title: "Irowsetimpl::restartposition |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs: C++
helpviewer_keywords: RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d8ed3217a635f8a0b9af5e2c94fff325e07bff61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
次のフェッチ位置を最初の位置に再配置します。つまり、行セットが最初の位置が作成されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowset::restartposition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 行セットの位置は未定義になるまで**GetNextRow**と呼びます。 後方に移動行セット内を呼び出して`RestartPosition`フェッチするか、逆方向にスクロールします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)