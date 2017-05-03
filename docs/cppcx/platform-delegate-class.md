---
title: "Platform::Delegate クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Delegate クラス"
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Delegate クラス
関数オブジェクトを表します。  
  
## 構文  
  
```cpp  
public delegate void delegate_name();  
```  
  
## メンバー  
 Delegate クラスには、[Platform::Object クラス](../cppcx/platform-object-class.md) から派生した Equals\(\)、GetHashCode\(\)、ToString\(\) メソッドがあります。  
  
## 解説  
 デリゲートを作成するには [delegate](../Topic/delegate%20%20\(C++%20Component%20Extensions\).md) キーワードを使用します。Platform::Delegate を明示的に使用しないでください。 詳細については、「[デリゲート](../cppcx/delegates-c-cx.md)」を参照してください。 デリゲートを作成および使用する方法の例については、[C\+\+ で Windows ランタイム コンポーネントを作成する](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md) を参照してください。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)