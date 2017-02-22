---
title: "リモート オートメーション接続マネージャー | Microsoft Docs"
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
  - "オートメーション クライアント, 構成 (リモート オートメーション用に)"
  - "オートメーション サーバー, 構成 (リモート オートメーション用に)"
  - "RAC マネージャー ツール"
  - "レジストリ, リモート オートメーション"
  - "リモート オートメーション接続マネージャー"
  - "リモート オートメーション, 構成 (クライアント コンピューターとサーバー コンピューターを)"
ms.assetid: 562eb7bc-f95c-46ad-ac97-f0dfa98362af
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# リモート オートメーション接続マネージャー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クライアントとサーバー コンピューターの両方を構成するには、レジストリの変更を加える必要があります。  これを手動でするのではなく、リモート オートメーションの Connectivity \(RAC\) マネージャー ツールを使用する方がより簡単です。  このツールは、RACMGR32.EXE、RACREG32.DLL とともに、選択したディレクトリにコピーする必要があります。  パス内に配置することにより、実行を使用してタスク バーから実行できます。  さらに、ショートカットを作成したり、スタート メニュー、その参照を配置できます。  
  
 したがって RACMGR32 は Visual Basic で記述され、Visual Basic サポート DLL が必要です。  これらのファイルは CD\-ROM に RACMGR32.EXE と同じディレクトリに配置されます。  Visual C\+\+ Enterprise Edition のセットアップによってインストールされたこれらのファイルのバージョンは、Visual Basic 5.0 Enterprise Edition に付属するバージョンより新しいまたは同等です。  Visual C\+\+ は、Visual Basic の新しいバージョンがシステム ディレクトリにコピーするファイルを作成します。  Windows 9x では、このディレクトリは、C:\\Windows\\System.です  Windows NT と Windows 2000 では、これは通常、C:\\WINNT\\system32.です  に登録するオペレーティング システムを使用してこれらのファイルを設定します。  Visual Basic のインストールから削除できます。  
  
## 参照  
 [オートメーション マネージャー \(MFC\)](../mfc/automation-manager-mfc.md)   
 [リモート オートメーションのユーザー コンポーネント](../mfc/remote-automation-user-components.md)   
 [リモート オートメーションのインストール](../Topic/Remote%20Automation%20Installation.md)