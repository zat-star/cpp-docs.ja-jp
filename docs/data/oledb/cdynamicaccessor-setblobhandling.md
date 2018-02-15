---
title: "Cdynamicaccessor::setblobhandling |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs:
- C++
helpviewer_keywords:
- SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 921ec36872d10c5109eeeb694cdf0fe1394022df
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
BLOB の現在の行の値の処理を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `eBlobHandling`  
 BLOB データを処理する方法を指定します。 次の値がかかることができます。  
  
-   **DBBLOBHANDLING_DEFAULT**: よりも大きい列のデータを処理`nBlobSize`(によって設定`SetBlobSizeLimit`) として BLOB データとを通じて取得、`ISequentialStream`または`IStream`オブジェクト。 このオプションはよりも大きいデータを含むすべての列をバインドしよう`nBlobSize`として示すまたは**DBTYPE_IUNKNOWN** BLOB データとして。  
  
-   **DBBLOBHANDLING_NOSTREAMS**: よりも大きい列のデータを処理`nBlobSize`(によって設定`SetBlobSizeLimit`) として BLOB データと、プロバイダーに割り当てられた、コンシューマー所有のメモリ内の参照を取得します。 このオプションは、1 つ以上の BLOB 列を含むテーブルに対して便利とプロバイダーがサポートする 1 つだけ`ISequentialStream`アクセサーごとのオブジェクト。  
  
-   **DBBLOBHANDLING_SKIP**: Skip (バインドしない) を含む Blob として修飾列 (アクセサーはバインドまたは列の値を取得されませんが、列のステータスや長さも取得されます)。  
  
## <a name="remarks"></a>コメント  
 呼び出す必要があります`SetBlobHandling`呼び出す前に**開く**です。  
  
 コンス トラクター メソッド[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) BLOB 処理する値を設定**DBBLOBHANDLING_DEFAULT**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)