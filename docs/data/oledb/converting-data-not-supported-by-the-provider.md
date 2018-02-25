---
title: "プロバイダーでサポートされていないデータを変換する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2fd46e57397eba0e8e732bba586df384951a86dc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換
コンシューマーはプロバイダーによってサポートされていないデータ型を要求するとき、OLE DB プロバイダー テンプレートのコードに`IRowsetImpl::GetData`データ型に変換する Msdadc.dll を呼び出します。  
  
 ようなインターフェイスを実装する場合`IRowsetChange`データ変換を必要とする、変換を行う Msdaenum.dll を呼び出すことができます。 使用して`GetData`で例として、Atldb.h で定義されています。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)