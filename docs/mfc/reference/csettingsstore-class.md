---
title: "CSettingsStore クラス | Microsoft Docs"
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
  - "CSettingsStore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStore クラス"
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSettingsStore クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows API 関数をラップし、レジストリへのアクセスに使用するオブジェクト指向インターフェイスを提供します。  
  
## 構文  
  
```  
class CSettingsStore : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSettingsStore::CSettingsStore](../Topic/CSettingsStore::CSettingsStore.md)|`CSettingsStore` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSettingsStore::Close](../Topic/CSettingsStore::Close.md)|開いているレジストリ キーを閉じます。|  
|[CSettingsStore::CreateKey](../Topic/CSettingsStore::CreateKey.md)|指定されたキーを開くか、存在しない場合は作成します。|  
|[CSettingsStore::DeleteKey](../Topic/CSettingsStore::DeleteKey.md)|指定されたキーとそのすべての子を削除します。|  
|[CSettingsStore::DeleteValue](../Topic/CSettingsStore::DeleteValue.md)|開いているキーの指定された値を削除します。|  
|[CSettingsStore::Open](../Topic/CSettingsStore::Open.md)|指定されたキーを開きます。|  
|[CSettingsStore::Read](../Topic/CSettingsStore::Read.md)|指定されたキー値のデータを取得します。|  
|[CSettingsStore::Write](../Topic/CSettingsStore::Write.md)|開いているキーの下のレジストリに値を書き込みます。|  
  
## 解説  
 メンバー関数の `CreateKey` と `Open` はよく似ています。  レジストリ キーが既に存在する場合、`CreateKey` と `Open` は同じように機能します。  ただし、レジストリ キーが存在しない場合、`CreateKey` はレジストリ キーを作成し、`Open` はエラー値を返します。  
  
## 使用例  
 `CSettingsStore` クラスの Open メソッドと Read メソッドの使用方法を次の例に示します。  このコード スニペットは [ツール ヒントのデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_ToolTipDemo#1](../../mfc/reference/codesnippet/CPP/csettingsstore-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSettingsStore](../../mfc/reference/csettingsstore-class.md)  
  
## 必要条件  
 **ヘッダー :** afxsettingsstore.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)