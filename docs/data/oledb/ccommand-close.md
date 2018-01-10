---
title: "Ccommand::close |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cad9d6a892b31d4e0c3945d94c36466d72fb9c81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandclose"></a>CCommand::Close
コマンドに関連付けられているアクセサー行セットを解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void Close( );  
```  
  
## <a name="remarks"></a>コメント  
 コマンドは、行セット、結果セットのアクセサー、および (必要に応じて) (テーブル、パラメーターをサポートしており、パラメーター アクセサー必要はありません) とは異なり、パラメーター アクセサーを使用します。  
  
 コマンドを実行するときに、両方を呼び出す必要があります`Close`と[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)コマンドの後にします。  
  
 呼び出して各結果セットのアクセサーを解放する必要があります同じコマンドを繰り返し実行する場合は、`Close`呼び出す前に`Execute`です。 系列の末尾には、呼び出すことによってパラメーター アクセサーを解放する必要があります`ReleaseCommand`です。 もう 1 つの一般的なシナリオでは、出力パラメーターを持つストアド プロシージャを呼び出すはします。 多くのプロバイダー (、OLE DB provider for SQL Server など) では、結果セットのアクセサーを終了するまで、出力パラメーター値をアクセスできません。 呼び出す`Close`閉じるには、返される行セットと結果セットのアクセサー パラメーターのアクセサーはなく、できるので、出力パラメーターの値を取得します。  
  
## <a name="example"></a>例  
 次の例を呼び出す方法を示しています。`Close`と`ReleaseCommand`繰り返し、同じコマンドを実行するとします。  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CCommand クラス](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)