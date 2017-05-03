---
title: "Platform::CallbackContext 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::CallbackContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::CallbackContext 列挙型"
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::CallbackContext 列挙型
コールバック関数 \(イベント ハンドラー\) が実行するスレッド コンテキストを指定します。  
  
## 構文  
  
```cpp  
enum class CallbackContext {};  
```  
  
## メンバー  
  
|型コード|説明|  
|----------|--------|  
|どれでも可|コールバック関数は、任意のスレッド コンテキストで実行できます。|  
|同|コールバック関数は、非同期操作を開始したスレッド コンテキストでのみ実行できます。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd