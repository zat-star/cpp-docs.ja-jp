---
title: "IUMSCompletionList 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSCompletionList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSCompletionList 構造体"
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# IUMSCompletionList 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

UMS の完了リストを表します。  UMS スレッドがブロックされると、基になる仮想プロセッサ ルートでスケジュールする内容を決定するためにスケジューラで指定されているスケジュールのコンテキストがディスパッチされ、元のスレッドがブロックされます。  元のスレッドがブロックされない場合、オペレーション システムは、このインターフェイスからアクセスできる完了リストのキューにそれを配置します。  スケジューラは指定されたスケジュール コンテキスト、または作業を検索するその他の場所にある完了リストを照会できます。  
  
## 構文  
  
```  
struct IUMSCompletionList;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IUMSCompletionList::GetUnblockNotifications メソッド](../Topic/IUMSCompletionList::GetUnblockNotifications%20Method.md)|関連付けられているスレッド プロキシのブロックが、このメソッドが最後に呼び出されたときから解除されている実行コンテキストを表す `IUMSUnblockNotification` インターフェイスのチェーンを取得します。|  
  
## 解説  
 このインターフェイスを使用して完了リストのキューから項目を取り出した後で実行される操作を、スケジューラで十分に注意する必要があります。  項目はスケジューラの実行可能コンテキスト リストに配置され、通常はすぐにアクセスできる必要があります。  キューから取り出された項目に、任意のロックの所有権を付与することができます。  スケジューラは、項目をキューから取り出す呼び出し操作の後で、これらの項目を通常スケジューラ内からアクセスできるリストに配置する操作をブロックする可能性のある関数呼び出しを実行できません。  
  
## 継承階層  
 `IUMSCompletionList`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler 構造体](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSUnblockNotification 構造体](../../../parallel/concrt/reference/iumsunblocknotification-structure.md)