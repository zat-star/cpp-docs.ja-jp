---
title: "Idbcreatecommandimpl::createcommand |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- CreateCommand method
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 83566713a42de25fb2c0e515daa94ee61eed53ed
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="idbcreatecommandimplcreatecommand"></a>IDBCreateCommandImpl::CreateCommand
新しいコマンドを作成し、要求されたインターフェイスを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand);  
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