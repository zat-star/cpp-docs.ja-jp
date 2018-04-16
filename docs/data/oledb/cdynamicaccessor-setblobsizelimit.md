---
title: CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2fac05c1380e2b612cb39994716387d99bef237
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
BLOB の最大サイズをバイト単位で設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nBlobSize`  
 BLOB のサイズの上限を指定します。  
  
## <a name="remarks"></a>コメント  
 BLOB の最大サイズ (バイト単位) に設定します。この値より大きい列のデータは、BLOB として扱われます。 一部のプロバイダーは、(2 GB) などの列のサイズがかなり大きくを提供します。 列サイズのメモリを割り当てるしようとするではなく、通常しようとする Blob としてこれらの列をバインドします。 その方法ですべてのメモリを割り当てることがないが、まだ切り捨てを心配せず、すべてのデータを読み取ることができます。 ただし、場合がありますを強制する`CDynamicAccessor`ネイティブ データ型の大きな列をバインドします。 これを行うには、呼び出す`SetBlobSizeLimit`呼び出す前に**開く**です。  
  
 コンス トラクター メソッド[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) BLOB の最大サイズを 8,000 バイトの既定値に設定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)