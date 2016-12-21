---
title: "ATL コントロール ホスト API とは何ですか? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "API [C++], ホスト"
  - "コントロール ホスト API"
  - "コントロール [ATL], ホスト API"
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: 15
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL コントロール ホスト API とは何ですか?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL のコントロール ホスト API は、ウィンドウを ActiveX コントロール コンテナーとして使用できるようにする、関数のセットです。  これらの関数は、ソース コードとして使用でき、ATL90.dll によって公開されるため、プロジェクトに静的または動的にリンクできます。  これらのコントロール ホスト関数を次の表に示します。  
  
|Function|説明|  
|--------------|--------|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|ホスト オブジェクトを作成して指定されたウィンドウに接続し、既存のコントロールをアタッチします。|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|ホスト オブジェクトを作成して指定されたウィンドウに接続し、コントロールを読み込みます。|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|ライセンス ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。[AtlAxCreateControl](../Topic/AtlAxCreateControl.md) に似た関数です。|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|ホスト オブジェクトを作成して指定されたウィンドウに接続し、コントロールを読み込みます \(イベント シンクのセットアップも可能です\)。|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|ライセンス ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md) に似た関数です。|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|ダイアログ リソースからモードレス ダイアログ ボックスを作成し、ウィンドウ ハンドルを返します。|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|ダイアログ リソースからモーダル ダイアログ ボックスを作成します。|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|ウィンドウでホストされるコントロールの **IUnknown** インターフェイス ポインターを返します。|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|ウィンドウに接続されたホスト オブジェクトの **IUnknown** インターフェイス ポインターを返します。|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|コントロール ホスト コードを初期化します。|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|コントロール ホスト コードを初期化前の状態に戻します。|  
  
 最初の 3 つの関数の `HWND` パラメーターは、既存のウィンドウであることが必要です。ほとんどの種類のウィンドウを指定できます。  これらの 3 つの関数のいずれかを明示的に呼び出す場合は \(通常、その必要はありません\)、既にホストとして使用しているウィンドウにハンドルを渡さないでください。渡した場合、既存のホスト オブジェクトが解放されません。  
  
 最初の 7 つの関数は、暗黙的に [AtlAxWinInit](../Topic/AtlAxWinInit.md) を呼び出します。  
  
> [!NOTE]
>  コントロール ホスト API は、ActiveX コントロール コンテインメントに対する ATL のサポートの基礎となります。  ただし、ATL のラッパー クラスを十分に活用すると、これらの関数を呼び出す必要はほとんどありません。  詳細については、「[どの ATL クラスを使用すると ActiveX コントロール コンテインメントに役立ちますか?](../atl/which-atl-classes-facilitate-activex-control-containment-q.md)」を参照してください。  
  
## 参照  
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)