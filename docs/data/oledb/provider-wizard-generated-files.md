---
title: "プロバイダー ウィザードで生成されたファイル |Microsoft ドキュメント"
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
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9cfcce4242cf985b8ffa50b9df234d609cfe7f3f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="provider-wizard-generated-files"></a>プロバイダー ウィザードで生成されたファイル
ATL OLE DB プロバイダー ウィザードでは、次のファイルを生成します。 次のトピックでは、短い名前"MyProvider"を使用するが、正確なファイル名は、プロバイダーを作成するときに対して行った選択によって異なります。  
  
|ファイル名|説明|  
|---------------|-----------------|  
|MyProviderRS.cpp|コマンドのヘルパーを含む`Execute`メソッドとプロバイダー 列のマップ。|  
|MyProviderDS.h|データ ソース オブジェクトを実装します。 このヘッダー ファイルには、データ ソースのプロパティのプロパティ マップが含まれています。|  
|MyProviderRS.h|コマンドや行セット オブジェクトを実装します。 このヘッダー ファイルには、行セットとコマンドのプロパティのプロパティ マップが含まれています。|  
|MyProviderSess.h|セッション オブジェクトを実装します。 このヘッダー ファイルには、セッションのプロパティのプロパティ マップが含まれています。|  
|MyProvider.rgs|OLE DB プロバイダー ウィザードによって生成された登録済みのオブジェクトが含まれています。|  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)