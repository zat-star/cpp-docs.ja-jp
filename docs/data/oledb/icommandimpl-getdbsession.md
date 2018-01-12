---
title: "Icommandimpl::getdbsession |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
dev_langs: C++
helpviewer_keywords: GetDBSession method
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d848b9bc541c74d6820932335542707c12263e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="icommandimplgetdbsession"></a>ICommandImpl::GetDBSession
コマンドを作成したセッションにインターフェイス ポインターを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD (GetDBSession) (  
   REFIID riid,  
   IUnknown** ppSession   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 セッションからのプロパティを取得するために便利です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [ICommandImpl クラス](../../data/oledb/icommandimpl-class.md)