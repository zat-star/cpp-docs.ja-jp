---
title: "CFontHolder クラス | Microsoft Docs"
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
  - "CFontHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontHolder クラス"
  - "カスタム フォント"
  - "フォント, ActiveX コントロール"
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFontHolder クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストック フォント プロパティを実装し、Windows のフォント オブジェクトと `IFont` インターフェイスの機能をカプセル化します。  
  
## 構文  
  
```  
class CFontHolder  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFontHolder::CFontHolder](../Topic/CFontHolder::CFontHolder.md)|`CFontHolder` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFontHolder::GetDisplayString](../Topic/CFontHolder::GetDisplayString.md)|コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|  
|[CFontHolder::GetFontDispatch](../Topic/CFontHolder::GetFontDispatch.md)|フォントの `IDispatch` のインターフェイスを返します。|  
|[CFontHolder::GetFontHandle](../Topic/CFontHolder::GetFontHandle.md)|Windows フォントのハンドルを返します。|  
|[CFontHolder::InitializeFont](../Topic/CFontHolder::InitializeFont.md)|`CFontHolder` オブジェクトを初期化します。|  
|[CFontHolder::QueryTextMetrics](../Topic/CFontHolder::QueryTextMetrics.md)|関連フォントの情報を取得します。|  
|[CFontHolder::ReleaseFont](../Topic/CFontHolder::ReleaseFont.md)|`IFont` と `IFontNotification` のインターフェイスから `CFontHolder` のオブジェクトを削除します。|  
|[CFontHolder::Select](../Topic/CFontHolder::Select.md)|デバイス コンテキストにフォント リソースを選択します。|  
|[CFontHolder::SetFont](../Topic/CFontHolder::SetFont.md)|`IFont` インターフェイスへの `CFontHolder` のオブジェクトを接続します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFontHolder::m\_pFont](../Topic/CFontHolder::m_pFont.md)|`CFontHolder` のオブジェクトの `IFont` インターフェイスへのポインター。|  
  
## 解説  
 `CFontHolder` には、基本クラスはありません。  
  
 コントロール用のカスタム フォント プロパティを実装するには、このクラスを使用します。  このようなプロパティの作成の詳細については、" " [ActiveX コントロール: フォントが使用されます](../../mfc/mfc-activex-controls-using-fonts.md)を参照してください。  
  
## 継承階層  
 `CFontHolder`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPropExchange クラス](../Topic/CPropExchange%20Class.md)