---
title: "データベース マクロとデータベース グローバル関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データベースのグローバル関数 [C++]"
  - "データベースのマクロ [C++]"
  - "グローバル データベース関数 [C++]"
  - "グローバル関数 [C++], データベース関数"
  - "マクロ [C++], MFC データベース"
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データベース マクロとデータベース グローバル関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次に示すマクロとグローバルは ODBC ベースのデータベース アプリケーションに適用されます。  これらは DAO ベースのアプリケーションで使用されます。  
  
 MFC 4.2 以前では、マクロ `AFX_SQL_ASYNC` と `AFX_SQL_SYNC` は、非同期操作の他のプロセスに時間を得ることを説明しました。  MFC 4.2 以降では、これらのマクロの実装は、MFC ODBC クラスが同期操作のみ使用後に変更されています。  `AFX_ODBC_CALL` マクロは、MFC 4.2 に新しかったです。  
  
### データベース マクロ  
  
|||  
|-|-|  
|[AFX\_ODBC\_CALL](../Topic/AFX_ODBC_CALL.md)|ODBC の API 関数を返す `SQL_STILL_EXECUTING`呼び出します。  `AFX_ODBC_CALL` が 繰り返し、`SQL_STILL_EXECUTING`を返さないまで関数を呼び出します。|  
|[AFX\_SQL\_ASYNC](../Topic/AFX_SQL_ASYNC.md)|`AFX_ODBC_CALL` を呼び出します。|  
|[AFX\_SQL\_SYNC](../Topic/AFX_SQL_SYNC.md)|`SQL_STILL_EXECUTING`を返さないの ODBC API 関数を呼び出します。|  
  
### Globals データベース  
  
|||  
|-|-|  
|[AfxGetHENV](../Topic/AfxGetHENV.md)|MFC には、現在使用中の ODBC 環境へのハンドルを取得します。  ODBC の直接呼び出しでこのハンドルを使用できます。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)