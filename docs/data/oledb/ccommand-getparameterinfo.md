---
title: "Ccommand::getparameterinfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
dev_langs: C++
helpviewer_keywords: GetParameterInfo method
ms.assetid: 9cd9277f-0161-4bd8-ad24-58e5e90b92a7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c89b91ccd5dd7b0c9f6ed9235024cd446370c897
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandgetparameterinfo"></a>CCommand::GetParameterInfo
コマンドのパラメーター、その名前、およびそれらの種類の一覧を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CCommandBase::GetParameterInfo(  
   DB_UPARAMS* pParams,  
   DBPARAMINFO** ppParamInfo,  
   OLECHAR** ppNamesBuffer   
) throw ( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[icommandwithparameters::getparameterinfo](https://msdn.microsoft.com/en-us/library/ms714917.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)