---
title: IErrorRecordsImpl::GetErrorHelpFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
dev_langs:
- C++
helpviewer_keywords:
- GetErrorHelpFile method
ms.assetid: ad198f76-5bdf-4b8d-9f1a-3d38f72f31ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3029a9822f16108409f703d2f5431b07fa7fde25
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ierrorrecordsimplgeterrorhelpfile"></a>IErrorRecordsImpl::GetErrorHelpFile
エラー レコードからヘルプ ファイルのパス名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rCurError`  
 `ERRORINFO`レコードで、 **IErrorInfo**インターフェイスです。  
  
## <a name="return-value"></a>戻り値  
 エラーに関するヘルプ ファイルのパス名を表す文字列へのポインター。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IErrorRecordsImpl クラス](../../data/oledb/ierrorrecordsimpl-class.md)