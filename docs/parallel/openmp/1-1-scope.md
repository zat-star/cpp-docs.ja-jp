---
title: "1.1 Scope | Microsoft Docs"
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
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.1 Scope
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この仕様はプログラムを並列に実行するユーザーが明示的にコンパイラとランタイム システムによって実行されるアクションを指定するかユーザー操作の並列について説明します。  OpenMP C および C\+\+ の実装は依存関係競合デッドロックと競合状態または不適切なプログラムの実行が発生する別の問題をチェックする必要はありません。  ユーザーはOpenMP C および C\+\+ の API を使用してアプリケーション構造が正しく実行されることを確認します。  このような並列化をこのドキュメントで役立つコンパイラにより生成された自動並列とディレクティブは説明しません。