---
title: "CMenuTearOffManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMenuTearOffManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenuTearOffManager クラス"
ms.assetid: ab7ca272-ce42-4678-95f7-6ad75038f5a0
caps.latest.revision: 31
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMenuTearOffManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ティアオフ メニューを管理します。  ティアオフ メニューはメニュー バー上のメニューの一種です。  ユーザーは、ティアオフ メニューをメニュー バーから外して、フローティング メニューにすることができます。  
  
## 構文  
  
```  
class CMenuTearOffManager : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMenuTearOffManager::CMenuTearOffManager](../Topic/CMenuTearOffManager::CMenuTearOffManager.md)|`CMenuTearOffManager` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMenuTearOffManager::Build](../Topic/CMenuTearOffManager::Build.md)||  
|[CMenuTearOffManager::GetRegPath](../Topic/CMenuTearOffManager::GetRegPath.md)||  
|[CMenuTearOffManager::Initialize](../Topic/CMenuTearOffManager::Initialize.md)|`CMenuTearOffManager` オブジェクトを初期化します。|  
|[CMenuTearOffManager::IsDynamicID](../Topic/CMenuTearOffManager::IsDynamicID.md)||  
|[CMenuTearOffManager::Parse](../Topic/CMenuTearOffManager::Parse.md)||  
|[CMenuTearOffManager::Reset](../Topic/CMenuTearOffManager::Reset.md)||  
|[CMenuTearOffManager::SetInUse](../Topic/CMenuTearOffManager::SetInUse.md)||  
|[CMenuTearOffManager::SetupTearOffMenus](../Topic/CMenuTearOffManager::SetupTearOffMenus.md)||  
  
## 解説  
 アプリケーションでティアオフ メニューを使用するには、`CMenuTearOffManager` オブジェクトが必要です。  ほとんどの場合、`CMenuTearOffManager` オブジェクトを直接作成することも、初期化することもありません。  これは、[CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md) 関数を呼び出すときに自動的に処理されます。  
  
## 使用例  
 次の例は、`CWinAppEX::EnableTearOffMenus` メソッドを呼び出すことによって `CMenuTearOffManager` オブジェクトを構築および初期化する方法を示しています。  このコード スニペットは [Word のスペースのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#12](../../mfc/reference/codesnippet/CPP/cmenutearoffmanager-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMenuTearOffManager](../../mfc/reference/cmenutearoffmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxmenutearoffmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)