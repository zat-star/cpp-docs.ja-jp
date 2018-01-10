---
title: "Cmanualaccessor::createaccessor |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
dev_langs: C++
helpviewer_keywords: CreateAccessor method
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f313e6d2b13a03a91295c75d52e4e77d5dfda22b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmanualaccessorcreateaccessor"></a>CManualAccessor::CreateAccessor
列バインド構造体のメモリを割り当て、列のデータ メンバーを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nBindEntries`  
 [in]列の数。 この数はへの呼び出しの数に一致する必要があります、 [cmanualaccessor::addbindentry](../../data/oledb/cmanualaccessor-addbindentry.md)関数。  
  
 `pBuffer`  
 [in]出力列の格納バッファーへのポインター。  
  
 `nBufferSize`  
 [in]バッファーのバイト単位のサイズ。  
  
## <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
## <a name="remarks"></a>コメント  
 呼び出す前に、この関数を呼び出して、`CManualAccessor::AddBindEntry`関数。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer サンプル](../../visual-cpp-samples.md)