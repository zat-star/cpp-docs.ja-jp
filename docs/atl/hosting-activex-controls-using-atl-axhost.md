---
title: "ATL AXHost を使用した ActiveX コントロールのホスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], ホスト"
  - "AXHost メソッド"
  - "Calendar コントロール (ActiveX)"
  - "Calendar コントロール (ActiveX), ホスト (ATL AXHost を使用した)"
  - "CAxWindow2T クラス"
  - "ホスト (ActiveX コントロールを)"
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ATL AXHost を使用した ActiveX コントロールのホスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックの例では AXHost を作成する方法、およびさまざまな ATL 関数を使用して ActiveX コントロールをホストする方法を示します。  コントロールもアクセス ホストされているコントロールからのイベントを [IDispEventImpl](../atl/reference/idispeventimpl-class.md) \(を使用\) シンクする方法を示します。  サンプルは、メイン ウィンドウまたは子ウィンドウのカレンダー コントロールをホストします。  
  
 `USE_METHOD` のシンボルの定義に注意してください。  1 ~ 8.の間で変わるようにこのシンボル値を変更できます。  シンボル値は、コントロールを作成する方法を決定します:  
  
-   `USE_METHOD`、コントロールのホストにホストのサブクラスをウィンドウの変換、その作成する呼び出しの偶数の値。  奇数の値の場合、コードはホストとして機能する子ウィンドウを作成します。  
  
-   1 ~ 4 の `USE_METHOD` の値では、コントロールへのアクセスとイベントの沈降は、ホストを作成する呼び出しによって実行されます。  5 ~ 8 の値は、インターフェイスのホストを照会し、シンクをなしにトラップ。  
  
 :概要を次に示します。  
  
|USE\_METHOD|ホスト|アクセスおよびイベントの沈降を制御します。|という名前の関数|  
|-----------------|---------|---------------------------|--------------|  
|1|子ウィンドウ|1 ステップ|CreateControlLicEx|  
|2|メイン ウィンドウ|1 ステップ|AtlAxCreateControlLicEx|  
|3|子ウィンドウ|1 ステップ|CreateControlEx|  
|4|メイン ウィンドウ|1 ステップ|AtlAxCreateControlEx|  
|5|子ウィンドウ|複数のステップ|CreateControlLic|  
|6|メイン ウィンドウ|複数のステップ|AtlAxCreateControlLic|  
|7|子ウィンドウ|複数のステップ|CreateControl|  
|8|メイン ウィンドウ|複数のステップ|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/CPP/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## 参照  
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](../Topic/AtlAxCreateControl.md)   
 [AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)   
 [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)   
 [AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)   
 [CAxWindow2T クラス](../Topic/CAxWindow2T%20Class.md)   
 [IAxWinHostWindowLic インターフェイス](../atl/reference/iaxwinhostwindowlic-interface.md)