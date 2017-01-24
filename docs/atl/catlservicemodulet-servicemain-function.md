---
title: "CAtlServiceModuleT::ServiceMain 関数 | Microsoft Docs"
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
  - "ServiceMain"
  - "CServiceModule::ServiceMain"
  - "CServiceModule.ServiceMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ServiceMain メソッド"
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::ServiceMain 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\(SCM\) サービス コントロール マネージャーはサービスのコントロール パネルのアプリケーションを開き、サービスを選択し、を **\[開始\]**をクリックすると `ServiceMain` を呼び出します。  
  
 SCM が `ServiceMain`を呼び出した後、サービスは SCM にハンドラー関数を付ける必要があります。  この関数は SCM がサービスの状態を取得し、特定の命令を渡すようにします \(一時停止、停止など\)。  SCM は、Win32 API の関数にこの関数を時サービス パス **\_Handler**、[RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054)取得します。  \(**\_Handler** は静的でないメンバー関数を呼び出す [&#91;ハンドラー&#93;](../Topic/CAtlServiceModuleT::Handler%20Function.md)静的メンバー関数です\)。  
  
 起動時に、サービスは、状態を SCM に通知する必要があります。  このクラスは Win32 API 関数に **SERVICE\_START\_PENDING** 渡すことによってこれを、[SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241)を説明します。  
  
 `ServiceMain` は、`CAtlExeModuleT::InitializeCom`を呼び出し、Win32 API 関数 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)を呼び出す。  既定では、`InitializeCom` は、関数に **COINIT\_MULTITHREADED** のフラグを渡します。  このフラグは、プログラムでフリー スレッド サーバーであることを示します。  
  
 次に、`CAtlServiceModuleT::Run` は、サービスの主要な処理を実行するために呼び出されます。  **\[実行\]** は、サービスを停止するまで継続します。  
  
## 参照  
 [サービス](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)