---
title: "プロバイダー ウィザードで生成されたファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB プロバイダー, ウィザードが生成したファイル"
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# プロバイダー ウィザードで生成されたファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL OLE DB プロバイダー ウィザードは、以下のファイルを生成します。  以下のトピックでは短縮名として "MyProvider" を使用しますが、実際のファイル名はプロバイダーの作成時の選択内容によって決まります。  
  
|ファイル名|説明|  
|-----------|--------|  
|MyProviderRS.cpp|コマンド ヘルパー `Execute` メソッドと、プロバイダー列マップが入っています。|  
|MyProviderDS.h|データ ソース オブジェクトを実装します。  このヘッダー ファイルには、データ ソース プロパティのプロパティ マップが入っています。|  
|MyProviderRS.h|コマンド オブジェクトと行セット オブジェクトを実装します。  このヘッダー ファイルには、行セット プロパティとコマンド プロパティのプロパティ マップが入っています。|  
|MyProviderSess.h|セッション オブジェクトを実装します。  このヘッダー ファイルには、セッション プロパティのプロパティ マップが入っています。|  
|MyProvider.rgs|OLE DB プロバイダー ウィザードにより生成された登録済みオブジェクトが入っています。|  
  
## 参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)