---
title: "CMFCCmdUsageCount クラス | Microsoft Docs"
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
  - "CMFCCmdUsageCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCmdUsageCount クラス"
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCCmdUsageCount クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーがメニューの項目を選択するときなどに、Windows メッセージの使用回数を追跡します。  
  
## 構文  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|既定のコンストラクターです。|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCCmdUsageCount::AddCmd](../Topic/CMFCCmdUsageCount::AddCmd.md)|指定されたコマンドに関連付けられたカウンターを 1 だけインクリメントします。|  
|[CMFCCmdUsageCount::GetCount](../Topic/CMFCCmdUsageCount::GetCount.md)|指定されたコマンド ID に関連付けられている使用カウントを取得します。|  
|[CMFCCmdUsageCount::HasEnoughInformation](../Topic/CMFCCmdUsageCount::HasEnoughInformation.md)|このオブジェクトが最低限のトラッキング データを収集したかどうかを判断します。|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](../Topic/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd.md)|指定したコマンドが頻繁に使用されているかどうかを判断します。|  
|[CMFCCmdUsageCount::Reset](../Topic/CMFCCmdUsageCount::Reset.md)|すべてのコマンドの使用カウントをクリアします。|  
|[CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md)|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます   \([CObject::Serialize](../Topic/CObject::Serialize.md) をオーバーライドします。\)|  
|[CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md)|`CMFCCmdUsageCount` クラスの共有データ メンバーの値を設定します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`m_CmdUsage`|コマンドを使用カウントにマップする `CMap` オブジェクト。|  
|`m_nMinUsagePercentage`|頻繁に使用されるコマンドの最低使用率。|  
|`m_nStartCount`|このオブジェクトが最低限のトラッキング データを収集したかどうかを判断するために使用される開始カウンター。|  
|`m_nTotalUsage`|トラッキングされているすべてのコマンドの数。|  
  
### 解説  
 `CMFCCmdUsageCount` クラスは、数値の各 Windows メッセージ ID を 32 ビットの符号なし整数カウンターに対応付けます。  `CMFCToolBar` は、このクラスを使用して、よく使用されるツール バー項目を表示します。  `CMFCToolBar` の詳細については、「[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)」を参照してください。  
  
 プログラムの実行後から次の実行まで、`CMFCCmdUsageCount` クラスのデータを維持できます。  クラス メンバー データをシリアル化するには [CMFCCmdUsageCount::Serialize](../Topic/CMFCCmdUsageCount::Serialize.md) メソッドを使用し、共有メンバー データを設定するには [CMFCCmdUsageCount::SetOptions](../Topic/CMFCCmdUsageCount::SetOptions.md) メソッドを使用します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcmdusagecount.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)