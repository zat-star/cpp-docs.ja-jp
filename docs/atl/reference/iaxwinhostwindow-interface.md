---
title: "IAxWinHostWindow インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindow インターフェイス"
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindow インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このインターフェイスには、コントロールとそのホスト オブジェクトを操作するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
interface IAxWinHostWindow : IUnknown  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[AttachControl](../Topic/IAxWinHostWindow::AttachControl.md)|ホスト オブジェクトに既存のコントロールをアタッチします。|  
|[CreateControl](../Topic/IAxWinHostWindow::CreateControl.md)|コントロールを作成し、ホスト オブジェクトにアタッチします。|  
|[CreateControlEx](../Topic/IAxWinHostWindow::CreateControlEx.md)|コントロールを作成し、ホスト オブジェクトにアタッチし、オプションでイベント ハンドラーを設定します。|  
|[QueryControl](../Topic/IAxWinHostWindow::QueryControl.md)|ホストされるコントロールへのインターフェイス ポインターを返します。|  
|[SetExternalDispatch](../Topic/IAxWinHostWindow::SetExternalDispatch.md)|`IDispatch` の外部インターフェイスを設定します。|  
|[SetExternalUIHandler](../Topic/IAxWinHostWindow::SetExternalUIHandler.md)|`IDocHostUIHandlerDispatch` の外部インターフェイスを設定します。|  
  
## 解説  
 このインターフェイスは、オブジェクトをホストする ATL ActiveX コントロールによって公開されます。  Web ブラウザーをホストする場合のホスト コントロールをオブジェクトにインターフェイスを、ホストされるコントロールから作成するために、またはアタッチを取得するか、このインターフェイスのメソッドは使用の外部ディスパッチ インターフェイスまたは UI ハンドラーを設定します。  
  
## 必要条件  
 このインターフェイスの定義の型は、次の表のように IDL または C\+\+ に指定できます。  
  
|定義の型|File|  
|----------|----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(ATLBase.h にもインクルードされます\)|  
  
## 参照  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)