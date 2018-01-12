---
title: "Idbcreatecommandimpl::createcommand |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs: C++
helpviewer_keywords: CreateCommand method
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ff1f7e9815ae5cea9a96c95f7faad30340bf548d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="idbcreatecommandimplcreatecommand"></a>IDBCreateCommandImpl::CreateCommand
新しいコマンドを作成し、要求されたインターフェイスを返します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD(CreateCommand)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand    
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[idbcreatecommand::createcommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 いくつかのパラメーターに対応*OLE DB プログラマーズ リファレンス*で説明される、別の名前のパラメーター **idbcreatecommand::createcommand**:  
  
|OLE DB テンプレート パラメーター|*OLE DB プログラマーズ リファレンス*パラメーター|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IDBCreateCommandImpl クラス](../../data/oledb/idbcreatecommandimpl-class.md)