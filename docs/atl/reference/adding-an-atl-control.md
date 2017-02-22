---
title: "ATL コントロールの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, 追加 (コントロールを)"
  - "コントロール [ATL], 追加 (プロジェクトに)"
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ATL コントロールの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このウィザードを使用して、使用する可能性のあるすべてのコンテナーのインターフェイスをサポートするユーザー インターフェイスのオブジェクトをプロジェクトに追加します。  これらのインターフェイスをサポートするには、プロジェクトが ATL アプリケーション、または ATL サポートを含む MFC アプリケーションとして作成されている必要があります。  [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)を使用して ATL アプリケーションを作成するか、または [MFC アプリケーションに ATL オブジェクトを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)して MFC アプリケーション用の ATL サポートを実装できます。  
  
### ATL コントロールをプロジェクトに追加するには  
  
1.  **ソリューション エクスプローラー**または[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で、ATL シンプル オブジェクトを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューの **\[追加\]** をクリックし、さらに **\[クラスの追加\]** をクリックします。  
  
3.  [&#91;クラスの追加&#93;](../../ide/add-class-dialog-box.md) ダイアログ ボックスのテンプレート ペインの **\[ATL コントロール\]** をクリックしてから、**\[追加\]** をクリックして [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)を表示します。  
  
 **ATL コントロール ウィザード**を使用すると、以下の 3 種類のコントロールを作成できます。  
  
-   標準コントロール  
  
-   複合コントロール  
  
-   DHTML コントロール  
  
 さらに、このウィザードの **\[オプション\]** ページの \[ライト コントロール\] を選択すると、コントロールのサイズを縮小し、ほとんどのコンテナーからも使用されないインターフェイスを削除できます。  
  
## 参照  
 [複合コントロールへの機能の追加](../../atl/adding-functionality-to-the-composite-control.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATLFire Sample](http://msdn.microsoft.com/ja-jp/5b2649f1-f45b-4cfb-9c4b-4d9459c26b09)