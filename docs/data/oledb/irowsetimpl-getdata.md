---
title: "Irowsetimpl::getdata |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
dev_langs:
- C++
helpviewer_keywords:
- GetData method [OLE DB]
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4c8238fba101efe81219bc332e050d7fd0ed8165
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplgetdata"></a>IRowsetImpl::GetData
行の行セットのコピーからデータを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(GetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[irowset::getdata](https://msdn.microsoft.com/en-us/library/ms716988.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 いくつかのパラメーターに対応*OLE DB プログラマーズ リファレンス*で説明される、別の名前のパラメーター **irowset::getdata**:  
  
|OLE DB テンプレート パラメーター|*OLE DB プログラマーズ リファレンス*パラメーター|  
|--------------------------------|------------------------------------------------|  
|*pDstData*|`pData`|  
  
## <a name="remarks"></a>コメント  
 また、OLE DB データ変換 DLL を使用したデータ変換を処理します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)