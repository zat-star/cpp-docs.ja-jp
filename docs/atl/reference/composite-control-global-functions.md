---
title: "複合コントロールに関するグローバル関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "複合コントロール, グローバル関数"
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
caps.latest.revision: 20
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 複合コントロールに関するグローバル関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらの関数は、ダイアログ ボックスを作成するライセンス ActiveX コントロールを作成する方法、およびホストするためのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
|||  
|-|-|  
|[AtlAxDialogBox](../Topic/AtlAxDialogBox.md)|ユーザーが用意するダイアログ テンプレートからモーダル ダイアログ ボックスを作成します。  表示されたダイアログ ボックスは、ActiveX コントロールを含めることができます。|  
|[AtlAxCreateDialog](../Topic/AtlAxCreateDialog.md)|ユーザーが用意するダイアログ テンプレートからモードレス ダイアログ ボックスを作成します。  表示されたダイアログ ボックスは、ActiveX コントロールを含めることができます。|  
|[AtlAxCreateControl](../Topic/AtlAxCreateControl.md)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)|ActiveX コントロールを作成して初期化し、指定されたウィンドウでホスト、およびコントロールからインターフェイスのポインター \(複数可\) を取得します。|  
|[AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)|ライセンスされた ActiveX コントロールを作成して初期化し、指定されたウィンドウでホストします。|  
|[AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)|ライセンス ActiveX コントロールを作成して初期化し、指定されたウィンドウでホスト、およびコントロールからインターフェイスのポインター \(複数可\) を取得します。|  
|[AtlAxAttachControl](../Topic/AtlAxAttachControl.md)|事前に作成されたコントロールを指定されたウィンドウにアタッチします。|  
|[AtlAxGetHost](../Topic/AtlAxGetHost.md)|ハンドルが与えられた指定のウィンドウのコンテナーへのダイレクト インターフェイス ポインターを取得するために使用されます \(存在する場合\)。|  
|[AtlAxGetControl](../Topic/AtlAxGetControl.md)|内に含まれるコントロールへのダイレクト インターフェイス ポインターを取得するために使用されるハンドルが与えられた指定のウィンドウ \(存在する場合\)。|  
|[AtlSetChildSite](../Topic/AtlSetChildSite.md)|子サイトの **IUnknown** を初期化します。|  
|[AtlAxWinInit](../Topic/AtlAxWinInit.md)|AxWin のオブジェクトのホスト コードを初期化します。|  
|[AtlAxWinTerm](../Topic/AtlAxWinTerm.md)|戻します AxWin のオブジェクトのホスト コード。|  
|[AtlGetObjectSourceInterface](../Topic/AtlGetObjectSourceInterface.md)|オブジェクトの既定のソース インターフェイスに関する情報を返します。|  
  
## 参照  
 [関数](../../atl/reference/atl-functions.md)   
 [複合コントロールに関するマクロ](../../atl/reference/composite-control-macros.md)