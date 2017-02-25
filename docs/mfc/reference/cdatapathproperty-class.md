---
title: "CDataPathProperty クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 非同期"
  - "非同期コントロール [C++]"
  - "CDataPathProperty クラス"
  - "OLE コントロール [C++], 非同期"
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDataPathProperty クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非同期で読み込める OLE コントロール プロパティを実装します。  
  
## 構文  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDataPathProperty::CDataPathProperty](../Topic/CDataPathProperty::CDataPathProperty.md)|`CDataPathProperty` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDataPathProperty::GetControl](../Topic/CDataPathProperty::GetControl.md)|`CDataPathProperty` のオブジェクトに関連付けられている非同期 OLE コントロールを取得します。|  
|[CDataPathProperty::GetPath](../Topic/CDataPathProperty::GetPath.md)|プロパティ パス名を取得します。|  
|[CDataPathProperty::Open](../Topic/CDataPathProperty::Open.md)|関連付けられている ActiveX \(OLE\) コントロールのプロパティの非同期読み込みを開始します。|  
|[CDataPathProperty::ResetData](../Topic/CDataPathProperty::ResetData.md)|コントロールのプロパティが変更されたこと `CAsyncMonikerFile::OnDataAvailable` をコンテナーに通知するために呼び出されます。|  
|[CDataPathProperty::SetControl](../Topic/CDataPathProperty::SetControl.md)|非同期 ActiveX \(OLE\) コントロールをプロパティに関連付けられる。|  
|[CDataPathProperty::SetPath](../Topic/CDataPathProperty::SetPath.md)|プロパティ パス名を設定します。|  
  
## 解説  
 非同期プロパティは、同期起動後に読み込まれます。  
  
 クラス `CDataPathProperty` は **CAysncMonikerFile**から派生します。  は、OLE コントロールの非同期プロパティを実装するには、クラスを `CDataPathProperty`から派生し、[OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md)をオーバーライドします。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次のトピックを参照:  
  
-   [インターネットの対処方法: &#91;ActiveX コントロール&#93;](../../mfc/activex-controls-on-the-internet.md)  
  
-   [インターネットの対処方法: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [MFC のサンプル イメージ](../../top/visual-cpp-samples.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile クラス](../../mfc/reference/casyncmonikerfile-class.md)