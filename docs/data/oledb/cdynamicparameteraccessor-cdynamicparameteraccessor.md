---
title: CDynamicParameterAccessor::CDynamicParameterAccessor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::CDynamicParameterAccessor
- CDynamicParameterAccessor.CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class, constructor
- CDynamicParameterAccessor method
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9befa8128aa54f300e5e7c8ff4b225f517e2fc0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorcdynamicparameteraccessor"></a>CDynamicParameterAccessor::CDynamicParameterAccessor
コンストラクターです。  
  
## <a name="syntax"></a>構文  
  
```cpp
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor(eBlobHandling, nBlobSize )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `eBlobHandling`  
 BLOB データを処理する方法を指定します。 既定値は**DBBLOBHANDLING_DEFAULT**です。 参照してください[cdynamicaccessor::setblobhandling](../../data/oledb/cdynamicaccessor-setblobhandling.md)の詳細については、 **DBBLOBHANDLINGENUM**値。  
  
 `nBlobSize`  
 BLOB の最大サイズ (バイト単位)この値を列データは、BLOB として扱われます。 既定値は、8,000 です。 参照してください[cdynamicaccessor::setblobsizelimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md)詳細についてはします。  
  
## <a name="remarks"></a>コメント  
 参照してください、 [cdynamicaccessor::cdynamicaccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) BLOB の処理の詳細については、コンス トラクターです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)