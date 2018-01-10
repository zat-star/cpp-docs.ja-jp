---
title: "プロバイダーでサポートされていないデータを変換する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 438d75ad3a36c82c4f9389d4c9b65d677603f6c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="converting-data-not-supported-by-the-provider"></a>プロバイダーでサポートされないデータの変換
コンシューマーはプロバイダーによってサポートされていないデータ型を要求するとき、OLE DB プロバイダー テンプレートのコードに`IRowsetImpl::GetData`データ型に変換する Msdadc.dll を呼び出します。  
  
 ようなインターフェイスを実装する場合`IRowsetChange`データ変換を必要とする、変換を行う Msdaenum.dll を呼び出すことができます。 使用して`GetData`で例として、Atldb.h で定義されています。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)