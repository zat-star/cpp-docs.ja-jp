---
title: "IAxWinHostWindowLic インターフェイス | Microsoft Docs"
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
  - "IAxWinHostWindowLic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindowLic インターフェイス"
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinHostWindowLic インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このインターフェイスには、ライセンスされたコントロールとそのホスト オブジェクトを操作するためのメソッドが用意されています。  
  
## 構文  
  
```  
  
interface IAxWinHostWindowLic : IAxWinHostWindow  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CreateControlLic](../Topic/IAxWinHostWindowLic::CreateControlLic.md)|ライセンス コントロールを作成し、ホスト オブジェクトにアタッチします。|  
|[CreateControlLicEx](../Topic/IAxWinHostWindowLic::CreateControlLicEx.md)|ライセンス コントロールを作成し、ホスト オブジェクトにアタッチし、オプションでイベント ハンドラーを設定します。|  
  
## 解説  
 `IAxWinHostWindowLic` は [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) から継承し、ライセンスされたコントロールの作成をサポートするメソッドを追加します。  
  
 このインターフェイスのメンバーを使用する例については、[ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) を参照してください。  
  
## 必要条件  
 このインターフェイスの定義の型は、次の表のように IDL または C\+\+ に指定できます。  
  
|定義の型|File|  
|----------|----------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(ATLBase.h にもインクルードされます\)|