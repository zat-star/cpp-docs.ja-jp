---
title: "プロパティ マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c51d50cb52562b60c1d9615e0617a02bef0cbcf3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="property-maps"></a>プロパティ マップ
セッション、行セット、および省略可能なコマンド オブジェクトで、他は、各プロバイダーは、1 つまたは複数のプロパティをサポートします。 これらのプロパティは、OLE DB プロバイダー ウィザードによって作成されたヘッダー ファイルに含まれているプロパティのマップで定義されます。 各ヘッダー ファイルには、オブジェクトまたはそのファイルで定義されたオブジェクトに対して定義されている OLE DB プロパティ グループ内のプロパティのマップが含まれています。 データ ソース オブジェクトを含むヘッダー ファイルにものプロパティ マップが含まれています、 [DataSource プロパティ](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx)です。 Session.h にはプロパティ マップが含まれています、[セッション プロパティ](https://msdn.microsoft.com/en-us/library/ms714221.aspx)です。 という 1 つのヘッダー ファイルに行セットとコマンド オブジェクトが存在する*projectname*RS.h です。 これらのプロパティのメンバーである、[行セット プロパティ](https://msdn.microsoft.com/en-us/library/ms711252.aspx)グループ。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)