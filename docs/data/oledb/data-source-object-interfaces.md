---
title: "データ ソース オブジェクト インターフェイス |Microsoft ドキュメント"
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
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0a045657b80ddaf70792d1c7f617b0e1f7c0b4a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="data-source-object-interfaces"></a>データ ソース オブジェクト インターフェイス
次の表は、データ ソース オブジェクトの OLE DB で定義されている必須およびオプションのインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるか。|  
|---------------|---------------|--------------------------------------|  
|`IDBCreateSession`|必須|[はい]|  
|`IDBInitialize`|必須|[はい]|  
|`IDBProperties`|必須|[はい]|  
|[IPersist](http://msdn.microsoft.com/library/windows/desktop/ms688695)|必須|[はい]|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|×|  
|`IDBDataSourceAdmin`|Optional|×|  
|`IDBInfo`|Optional|×|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Optional|×|  
|`ISupportErrorInfo`|Optional|×|  
  
 データ ソース オブジェクトを実装して、 `IDBProperties`、 `IDBInitialize`、および`IDBCreateSession`継承によってインターフェイスです。 継承、またはそのいずれかのこれらの実装クラスから継承せず、追加の機能をサポートするために選択できます。 サポートする場合、`IDBDataSourceAdmin`インターフェイスから継承する必要があります、`IDBDataSourceAdminImpl`クラスです。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)