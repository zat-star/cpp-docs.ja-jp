---
title: "オートメーション マネージャー (MFC) | Microsoft Docs"
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
  - "AUTMGR32.exe"
  - "オートメーション クライアント, オートメーション マネージャー"
  - "オートメーション マネージャー"
  - "オートメーション サーバー, オートメーション マネージャー"
  - "オートメーション, オートメーション マネージャー"
  - "リモート オートメーション, オートメーション マネージャー"
ms.assetid: 6bf3429e-1946-41c5-86d0-ad7f5b8585b8
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# オートメーション マネージャー (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

AUTMGR32.EXE はリモート オートメーション オブジェクトを提供することを目的としている各コンピューターの Windows システム ディレクトリにコピーする必要があります。  Windows 95 および Windows 98 では、このディレクトリは、C:\\WINDOWS\\SYSTEM.です  Windows NT と Windows 2000 では、これは通常、C:\\WINNT\\SYSTEM32.です  
  
 サーバーからクライアントにコールバックを有効にする場合は、この実行可能ファイルは、各クライアント コンピューターのシステム ディレクトリにコピーする必要があります。  
  
 オートメーション マネージャーが実行されている場合は、短いステータス情報を含むサーバー コンピューターの小さなウィンドウを表示します。  それを非表示にするには、Microsoft サポート技術情報の記事 Q138067 "を参照してください。  
  
## 参照  
 [リモート オートメーション接続マネージャー](../mfc/remote-automation-connection-manager.md)   
 [リモート オートメーションのユーザー コンポーネント](../mfc/remote-automation-user-components.md)   
 [リモート オートメーションのインストール](../Topic/Remote%20Automation%20Installation.md)