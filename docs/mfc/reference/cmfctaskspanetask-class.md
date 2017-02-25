---
title: "CMFCTasksPaneTask クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPaneTask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTask クラス"
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCTasksPaneTask クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCTasksPaneTask` クラスは、作業ウィンドウ コントロール \([CMFCTasksPane](../Topic/CMFCTasksPane%20Class.md)\) のタスクを表すヘルパー クラスです。  タスク オブジェクトは、タスク グループ \([CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\) 内の項目を表します。  各タスクには、ユーザーがタスク名の左側に表示されるタスクやアイコンをクリックしたときにフレームワークが実行するコマンドを設定できます。  
  
## 構文  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](../Topic/CMFCTasksPaneTask::CMFCTasksPaneTask.md)|`CMFCTasksPaneTask` オブジェクトを構築して、初期化します。|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCTasksPaneTask::SetACCData](../Topic/CMFCTasksPaneTask::SetACCData.md)|現在のタスクのアクセシビリティ データを調べます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCTasksPaneTask::m\_bAutoDestroyWindow](../Topic/CMFCTasksPaneTask::m_bAutoDestroyWindow.md)|タスク ウィンドウが自動的に破棄されるかどうかを判断します。|  
|[CMFCTasksPaneTask::m\_bIsBold](../Topic/CMFCTasksPaneTask::m_bIsBold.md)|フレームワークがタスク ラベルを太字テキストで描画するかどうかを指定します。|  
|[CMFCTasksPaneTask::m\_dwUserData](../Topic/CMFCTasksPaneTask::m_dwUserData.md)|フレームワークによってタスクに関連付けられたユーザー定義データを格納します。  タスクにデータが関連付けられていない場合は、0 に設定します。|  
|[CMFCTasksPaneTask::m\_hwndTask](../Topic/CMFCTasksPaneTask::m_hwndTask.md)|タスク ウィンドウを識別するハンドルです。|  
|[CMFCTasksPaneTask::m\_nIcon](../Topic/CMFCTasksPaneTask::m_nIcon.md)|フレームワークがタスクの横に表示するイメージの、イメージ リスト内のインデックス。|  
|[CMFCTasksPaneTask::m\_nWindowHeight](../Topic/CMFCTasksPaneTask::m_nWindowHeight.md)|タスク ウィンドウの高さです。  タスク ウィンドウのないタスクの場合、この値は 0 です。|  
|[CMFCTasksPaneTask::m\_pGroup](../Topic/CMFCTasksPaneTask::m_pGroup.md)|このタスクが属する `CMFCTasksPaneTaskGroup` へのポインター。|  
|[CMFCTasksPaneTask::m\_rect](../Topic/CMFCTasksPaneTask::m_rect.md)|タスクの外接する四角形を指定します。|  
|[CMFCTasksPaneTask::m\_strName](../Topic/CMFCTasksPaneTask::m_strName.md)|タスクの名前です。|  
|[CMFCTasksPaneTask::m\_uiCommandID](../Topic/CMFCTasksPaneTask::m_uiCommandID.md)|ユーザーがタスクをクリックしたときにフレームワークが実行するコマンドのコマンド ID を指定します。  この値が有効なコマンド ID でない場合、タスクは単純なラベルとして扱われます。|  
  
## 解説  
 次の図は、3 つのタスクを含むタスク グループを示しています。  
  
 ![展開されたタスク グループ](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
> [!NOTE]
>  タスクに有効なコマンド ID が設定されていない場合、そのタスクは単純なラベルとして扱われます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## 必要条件  
 **ヘッダー :** afxTasksPane.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CObject クラス](../Topic/CObject%20Class.md)