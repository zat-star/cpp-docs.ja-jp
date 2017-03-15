---
title: "ドキュメントでのコマンドの処理 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WM_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド処理"
  - "コマンド処理, コマンド (ドキュメントの)"
  - "ドキュメント, 処理 (メッセージを)"
  - "ドキュメント, メッセージ マップ"
  - "メッセージ処理, WM_COMMAND メッセージ"
  - "メッセージ マップ, ドキュメント クラスで"
  - "WM_COMMAND"
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ドキュメントでのコマンドの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ドキュメント クラスには、メニュー項目、ツール バー ボタン、またはアクセラレータ キーによって生成される特定のコマンドを処理する場合があります。  既定で、**CDocument** はシリアル化を使用して、ファイル メニューの名前を付けて保存コマンドと、保存を処理します。  データに影響するそのほかのコマンドには、ドキュメントのメンバー関数によって処理される場合があります。  たとえば、Scribble プログラムでは、クラス `CScribDoc` は編集を明確にハンドラーを現在のドキュメントに格納されているデータをすべて削除するすべてのコマンドが用意されています。  ドキュメントは、メッセージ マップを指定できます。ビューとは異なり、ドキュメントは標準 Windows メッセージ— **WM\_COMMAND** メッセージ、または「コマンドのみ処理できません」。  
  
## 参照  
 [ドキュメントの使い方](../mfc/using-documents.md)