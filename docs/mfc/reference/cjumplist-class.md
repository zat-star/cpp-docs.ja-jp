---
title: "CJumpList クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxadv/CJumpList"
  - "CJumpList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CJumpList クラス"
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CJumpList クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CJumpList` はタスク バーのアイコンを右クリックしたときに表示されるショートカットの一覧です。  
  
## 構文  
  
```  
class CJumpList;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CJumpList::CJumpList](../Topic/CJumpList::CJumpList.md)|`CJumpList` オブジェクトを構築します。|  
|[CJumpList::~CJumpList](../Topic/CJumpList::~CJumpList.md)|`CJumpList` オブジェクトを破棄します。|  
  
|名前|説明|  
|--------|--------|  
|[CJumpList::AbortList](../Topic/CJumpList::AbortList.md)|コミットせずにリスト ビルドのトランザクションを中止します。|  
|[CJumpList::AddDestination](../Topic/CJumpList::AddDestination.md)|オーバーロードされます。  リストにコピー先を追加します。|  
|[CJumpList::AddKnownCategory](../Topic/CJumpList::AddKnownCategory.md)|リストに既知のカテゴリを追加します。|  
|[CJumpList::AddTask](../Topic/CJumpList::AddTask.md)|オーバーロードされます。  標準のタスク カテゴリに項目を追加します。|  
|[CJumpList::AddTasks](../Topic/CJumpList::AddTasks.md)|標準のタスク カテゴリに項目を追加します。|  
|[CJumpList::AddTaskSeparator](../Topic/CJumpList::AddTaskSeparator.md)|タスク間の区分線を追加します。|  
|[CJumpList::ClearAll](../Topic/CJumpList::ClearAll.md)|`CJumpList` の現在のインスタンスにこれまでに追加されている配置先とすべてのタスクを削除します。|  
|[CJumpList::ClearAllDestinations](../Topic/CJumpList::ClearAllDestinations.md)|`CJumpList` の現在のインスタンスにこれまでに追加されているすべての出力先を削除します。|  
|[CJumpList::CommitList](../Topic/CJumpList::CommitList.md)|一覧のビルドのトランザクションが終了し、関連付けられたストア \(この場合は\)。レジストリにレポート リストをコミットします|  
|[CJumpList::GetDestinationList](../Topic/CJumpList::GetDestinationList.md)|目的のリストへのインターフェイス ポインターを取得します。|  
|[CJumpList::GetMaxSlots](../Topic/CJumpList::GetMaxSlots.md)|呼び出し元のアプリケーションのメニューに表示できるカテゴリのヘッダーを含む項目の最大数を取得します。|  
|[CJumpList::GetRemovedItems](../Topic/CJumpList::GetRemovedItems.md)|削除対象を表す項目の配列を返します。|  
|[CJumpList::InitializeList](../Topic/CJumpList::InitializeList.md)|一覧のビルドのトランザクションを開始します。|  
|[CJumpList::SetAppID](../Topic/CJumpList::SetAppID.md)|ビルド リストのアプリケーションのユーザー モデル ID を設定します。|  
  
## 継承階層  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## 必要条件  
 **ヘッダー:** afxadv.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)