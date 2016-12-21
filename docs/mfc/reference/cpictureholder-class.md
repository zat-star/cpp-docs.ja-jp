---
title: "CPictureHolder クラス | Microsoft Docs"
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
  - "Picture"
  - "CPictureHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [MFC], OLE"
  - "CPictureHolder クラス"
  - "OLE コントロール, イメージ"
  - "Picture プロパティ"
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPictureHolder クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーがコントロールにピクチャを表示できるように、ピクチャ プロパティを実装します。  
  
## 構文  
  
```  
class CPictureHolder  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPictureHolder::CPictureHolder](../Topic/CPictureHolder::CPictureHolder.md)|`CPictureHolder` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPictureHolder::CreateEmpty](../Topic/CPictureHolder::CreateEmpty.md)|空の `CPictureHolder` オブジェクトを作成します。|  
|[CPictureHolder::CreateFromBitmap](../Topic/CPictureHolder::CreateFromBitmap.md)|ビットマップの `CPictureHolder` のオブジェクトを作成します。|  
|[CPictureHolder::CreateFromIcon](../Topic/CPictureHolder::CreateFromIcon.md)|アイコンの `CPictureHolder` のオブジェクトを作成します。|  
|[CPictureHolder::CreateFromMetafile](../Topic/CPictureHolder::CreateFromMetafile.md)|メタファイルの `CPictureHolder` のオブジェクトを作成します。|  
|[CPictureHolder::GetDisplayString](../Topic/CPictureHolder::GetDisplayString.md)|コントロールのコンテナーのプロパティ ブラウザーに表示される文字列を取得します。|  
|[CPictureHolder::GetPictureDispatch](../Topic/CPictureHolder::GetPictureDispatch.md)|`CPictureHolder` のオブジェクトの `IDispatch` のインターフェイスを返します。|  
|[CPictureHolder::GetType](../Topic/CPictureHolder::GetType.md)|`CPictureHolder` のオブジェクトがビットマップ、メタファイル、またはアイコンであるかどうかを示します。|  
|[CPictureHolder::Render](../Topic/CPictureHolder::Render.md)|画像を表示します。|  
|[CPictureHolder::SetPictureDispatch](../Topic/CPictureHolder::SetPictureDispatch.md)|`CPictureHolder` のオブジェクトの `IDispatch` インターフェイスを設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CPictureHolder::m\_pPict](../Topic/CPictureHolder::m_pPict.md)|図のオブジェクトへのポインター。|  
  
## 解説  
 `CPictureHolder` には、基本クラスはありません。  
  
 標準的なピクチャ プロパティを使用すると、開発者は表示用にビットマップ、アイコン、メタファイルを指定できます。  
  
 カスタムのピクチャ プロパティの作成の詳細については、" " [MFC ActiveX コントロール: ActiveX コントロールの図を使用します](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)を参照してください。  
  
## 継承階層  
 `CPictureHolder`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFontHolder クラス](../../mfc/reference/cfontholder-class.md)