---
title: "DAO データベース エンジンの初期化と終了 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "DAO (データ アクセス オブジェクト), 初期化"
  - "DAO (データ アクセス オブジェクト), 終了"
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# DAO データベース エンジンの初期化と終了
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DAO オブジェクトを使用する場合は、DAO データベース エンジンは、アプリケーションまたは DLL の終了前に初期化され、次に終了する必要があります。  2 個の関数、`AfxDaoInit` と `AfxDaoTerm`は、次のタスクを実行します。  
  
### DAO データベース エンジンの初期化と終了  
  
|||  
|-|-|  
|[AfxDaoInit](../Topic/AfxDaoInit.md)|DAO データベース エンジンを初期化します。|  
|[AfxDaoTerm](../Topic/AfxDaoTerm.md)|DAO データベース エンジンを終了します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)