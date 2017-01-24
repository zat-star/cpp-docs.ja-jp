---
title: "MFC ActiveX コントロール : ストック プロパティ ページの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLSID_CPicturePropPage"
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLSID_CColorPropPage"
  - "CLSID_CFontPropPage"
  - "CLSID_CPicturePropPage"
  - "カラー ストック プロパティ ページ"
  - "フォント, ActiveX コントロール"
  - "MFC ActiveX コントロール, プロパティ ページ"
  - "ピクチャ ストック プロパティ ページ"
  - "ストック プロパティ, ストック プロパティ ページ"
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : ストック プロパティ ページの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールで使用できるストック プロパティ ページとその使用方法について説明します。  
  
 ActiveX コントロールのプロパティ ページを使用する詳細については、次のトピックを参照します:  
  
-   [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX コントロール: 他のカスタム プロパティ ページの追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC は、ActiveX コントロールを使用する 3 とおりのストック プロパティ ページについて: **CLSID\_CColorPropPage**、**CLSID\_CFontPropPage**と **CLSID\_CPicturePropPage**。  これらのページは、標準色、フォント、およびピクチャ プロパティのためのユーザー インターフェイスがそれぞれ表示されます。  
  
 コントロールに二つのプロパティ ページを組み込むには、コントロール プロパティ ページの ID の配列を初期化するコードの ID を追加します。  次の例では、コントロールの実装ファイル \(.cpp\) で、このコードは 3 個のストック プロパティ ページとすべて既定のプロパティ ページ \(この例で名前付きな `CMyPropPage`\) を含めるように配列を初期化します:  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/CPP/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 プロパティ ページの数が、`BEGIN_PROPPAGEIDS` マクロで、4.であることに注意してください。  これは、ActiveX コントロールでサポートされるプロパティ ページ数を表します。  
  
 これらの変更を作成した後、プロジェクトをリビルドします。  コントロールは、フォント、画像やカラー プロパティのプロパティ ページがあります。  
  
> [!NOTE]
>  コントロールのストック プロパティ ページにアクセスすることができない場合は、MFC DLL \(MFCxx.DLL\) が現在のオペレーティング システムで適切に登録されていない可能性があります。  通常、これは現在実行したものと異なるオペレーティング システムの Visual C\+\+ をインストールすることになります。  
  
> [!TIP]
>  ストック プロパティ ページが表示されない場合 \(前のメモを参照してください\)、完全パス名を指定して、コマンド ラインから DLL へ RegSvr32.exe を実行して DLL を登録します。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール : ストック プロパティの追加](../Topic/MFC%20ActiveX%20Controls:%20Adding%20Stock%20Properties.md)