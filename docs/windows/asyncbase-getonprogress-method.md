---
title: "Asyncbase::getonprogress メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs: C++
helpviewer_keywords: GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8d83099b6842f9e758755e64aa8d7828a656aafb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasegetonprogress-method"></a>AsyncBase::GetOnProgress メソッド
指定された変数に現在の進行状況イベント ハンドラーのアドレスをコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `progressHandler`  
 現在の進行状況イベント ハンドラーのアドレスが格納されている場所です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、E_ILLEGAL_METHOD_CALL です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>参照  
 [AsyncBase クラス](../windows/asyncbase-class.md)