---
title: "ActiveX コントロールからのクラスの追加 (Visual C++) | Microsoft Docs"
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
  - "ActiveX コントロール [C++], 追加 (クラスを)"
  - "クラス [C++], 作成"
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX コントロールからのクラスの追加 (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このウィザードを使用して、利用できる ActiveX コントロールのインターフェイスから MFC クラスを作成します。  MFC クラスは、[MFC アプリケーション](../mfc/reference/creating-an-mfc-application.md)、[MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md)、および [MFC ActiveX コントロール](../mfc/reference/creating-an-mfc-activex-control.md)に追加できます。  
  
> [!NOTE]
>  ActiveX コントロールからクラスを追加するために、オートメーションを有効にして MFC プロジェクトを作成する必要はありません。  
  
 ActiveX コントロールは、コンポーネント オブジェクト モデル \(COM: Component Object Model\) に基づく再利用可能なソフトウェア コンポーネントです。多岐にわたる OLE の機能をサポートしており、さまざまなソフトウェアの要件に合わせてカスタマイズできます。  ActiveX コントロールは、通常の ActiveX コントロール コンテナーとインターネット上の WWW \(World Wide Web\) ページの両方で使用できるようにデザインされています。  
  
### ActiveX コントロールから MFC クラスを追加するには  
  
1.  **ソリューション エクスプローラー**または [&#91;クラス ビュー&#93;](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925) で、ActiveX コントロール クラスを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューの \[追加\] をポイントし、\[クラスの追加\] をクリックします。  
  
3.  [&#91;クラスの追加&#93;](../ide/add-class-dialog-box.md) ダイアログ ボックスでテンプレート ペインの \[ActiveX コントロールの MFC クラス\] をクリックし、次に \[開く\] をクリックして、[ActiveX コントロール クラス追加ウィザード](../ide/add-class-from-activex-control-wizard.md)を表示します。  
  
 このウィザードでは、ActiveX コントロール内の複数のインターフェイスを追加できます。  同様に、1 回のウィザード セッションで複数の ActiveX コントロールからクラスを作成できます。  
  
 システムに登録された ActiveX コントロールからクラスを追加したり、システムに登録せずに、タイプ ライブラリ ファイル \(.tlb、.olb、.dll、.ocx、または .exe\) にある ActiveX コントロールからクラスを追加したりできます。  ActiveX コントロールの登録の詳細については、「[OLE コントロールの登録](../Topic/Registering%20OLE%20Controls.md)」を参照してください。  
  
 ウィザードでは、選択した ActiveX コントロールから追加する各インターフェイスに対して、[CWnd](../Topic/CWnd%20Class.md) または [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) から派生した MFC クラスを作成します。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [COM および ATL の概要](../atl/introduction-to-com-and-atl.md)