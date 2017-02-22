---
title: "ローカル サーバーとしてのプログラムの実行 | Microsoft Docs"
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
  - "ATL サービス, 実行 (ローカル サーバーとして)"
  - "デバッグ [ATL], 実行 (ローカル サーバーとしてサービスを)"
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ローカル サーバーとしてのプログラムの実行
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サービスとしてプログラムを実行することは不便な場合は、プログラムが正常なローカル サーバーとして実行するようにレジストリを変更できます。  `LocalService` の値の AppID の下に `_LocalService` に簡易名を変更し、の CLSID の下に `LocalServer32` のキーが正しく設定されていることを確認します。  \(DCOMCNFG を使用してアプリケーションを別のコンピューターで実行できるように指定することは `_LocalServer32`に `LocalServer32` のキーと名前が変更されます。\) ローカル サーバーとして、プログラムの実行が失敗する前に `CAtlServiceModuleT::Start` の **StartServiceCtrlDispatcher** の呼び出しが数秒かかるため、起動時にいくつかの詳細に秒かかります。  
  
## 参照  
 [デバッグのヒント](../atl/debugging-tips.md)