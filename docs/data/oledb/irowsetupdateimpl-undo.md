---
title: "Irowsetupdateimpl::undo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
dev_langs: C++
helpviewer_keywords: Undo method
ms.assetid: f3dc7764-050c-4322-9b2f-9ca772a0fb88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 329a6141ca01678c341ef3890fb0e563a7299915
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplundo"></a>IRowsetUpdateImpl::Undo
最後のフェッチまたは更新以降、行への変更を元に戻します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( Undo )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[ ],  
   DBCOUNTITEM* pcRowsUndone,  
   HROW** prgRowsUndone,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hReserved`  
 [in]対応する、`hChapter`パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)です。  
  
 *pcRowsUndone*  
 [out]対応する、`pcRows`パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)です。  
  
 *prgRowsUndone*  
 [in]対応する、 *prgRows*パラメーター [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)です。  
  
 その他のパラメーターを参照してください。 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [IRowsetUpdateImpl クラス](../../data/oledb/irowsetupdateimpl-class.md)