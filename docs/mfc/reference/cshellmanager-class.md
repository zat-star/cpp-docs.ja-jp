---
title: "CShellManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CShellManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CShellManager クラス"
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CShellManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID リストへのポインター \(PIDL\) を操作するためのさまざまなメソッドを実装します。  
  
## 構文  
  
```  
class CShellManager : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CShellManager::CShellManager](../Topic/CShellManager::CShellManager.md)|`CShellManager` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CShellManager::BrowseForFolder](../Topic/CShellManager::BrowseForFolder.md)|ユーザーがシェル フォルダーを選択できるダイアログ ボックスを表示します。|  
|[CShellManager::ConcatenateItem](../Topic/CShellManager::ConcatenateItem.md)|2 つの PIDL を連結します。|  
|[CShellManager::CopyItem](../Topic/CShellManager::CopyItem.md)|新しい PIDL を作成し、指定した PIDL をコピーします。|  
|[CShellManager::CreateItem](../Topic/CShellManager::CreateItem.md)|指定したサイズの新しい PIDL を作成します。|  
|[CShellManager::FreeItem](../Topic/CShellManager::FreeItem.md)|指定した PIDL を削除します。|  
|[CShellManager::GetItemCount](../Topic/CShellManager::GetItemCount.md)|指定した PIDL の項目数を返します。|  
|[CShellManager::GetItemSize](../Topic/CShellManager::GetItemSize.md)|指定した PIDL のサイズを返します。|  
|[CShellManager::GetNextItem](../Topic/CShellManager::GetNextItem.md)|PIDL から次の項目を返します。|  
|[CShellManager::GetParentItem](../Topic/CShellManager::GetParentItem.md)|指定された項目の親項目を取得します。|  
|[CShellManager::ItemFromPath](../Topic/CShellManager::ItemFromPath.md)|指定されたパスにより識別される項目の PIDL を取得します。|  
  
## 解説  
 `CShellManager` クラスのメソッドはすべて、PIDL を処理します。  PIDL はシェル オブジェクトの一意の識別子です。  
  
 `CShellManager` オブジェクトは手動で作成しないでください。  アプリケーションのフレームワークによって自動的に作成されます。  ただし、アプリケーションの初期化中には [CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md) を呼び出す必要があります。  アプリケーションのシェル マネージャーへのポインターを取得するには、[CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md) を呼び出します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxshellmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)