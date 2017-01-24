---
title: "プロパティ マップ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マップ, プロパティ"
  - "OLE DB プロバイダー, プロパティ"
  - "プロパティ マップ"
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロパティ マップ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

セッション オブジェクト、行セット オブジェクト、および省略可能なコマンド オブジェクトのほかに、各プロバイダーは 1 つ以上のプロパティをサポートします。  これらのプロパティは、OLE DB プロバイダー ウィザードによって作成されるヘッダー ファイルに入っているプロパティ マップで定義されています。  各ヘッダー ファイルは、そのファイルで定義されたオブジェクトに対して定義されている OLE DB プロパティ グループのプロパティ マップを含んでいます。  データ ソース オブジェクトを持つヘッダー ファイルは、[DataSource プロパティ](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx)のプロパティ マップも含んでいます。  Session.h は、[Session プロパティ](https://msdn.microsoft.com/en-us/library/ms714221.aspx)のプロパティ マップを含んでいます。  行セット オブジェクトとコマンド オブジェクトは、*projectname*RS.h という 1 つのヘッダー ファイルに入っています。  これらのプロパティは [Rowset プロパティ](https://msdn.microsoft.com/en-us/library/ms711252.aspx) グループのメンバーです。  
  
## 参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)