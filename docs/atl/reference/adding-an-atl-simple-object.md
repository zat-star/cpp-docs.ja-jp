---
title: "ATL シンプル オブジェクトの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.classes.adding.atl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, 追加 (オブジェクトを)"
  - "ATL, シンプル オブジェクト"
  - "オブジェクト [ATL] "
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL シンプル オブジェクトの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL \(Active Template Library\) オブジェクトをプロジェクトに追加するには、プロジェクトを ATL アプリケーション、または ATL サポートを含む MFC アプリケーションとして作成しておく必要があります。  [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)を使用して ATL アプリケーションを作成するか、または [MFC アプリケーションに ATL オブジェクトを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)して MFC アプリケーション用の ATL サポートを実装できます。  
  
 新しい ATL オブジェクトの COM インターフェイスは、最初に ATL オブジェクトを作成したときに定義できます。または、クラス ビューのショートカット メニューの [&#91;インターフェイスの実装&#93;](../Topic/Implement%20Interface%20Wizard.md) を使用して後で追加できます。  
  
### ATL COM プロジェクトに ATL シンプル オブジェクトを追加するには  
  
1.  **ソリューション エクスプローラー**または[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で、ATL シンプル オブジェクトを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューの \[追加\] をポイントし、\[クラスの追加\] をクリックします。  
  
3.  [&#91;クラスの追加&#93;](../../ide/add-class-dialog-box.md) ダイアログ ボックスの \[テンプレート\] ペインの **\[ATL シンプル オブジェクト\]** をクリックし、次に **\[開く\]** をクリックして [ATL シンプル オブジェクト ウィザード](../../atl/reference/atl-simple-object-wizard.md)を表示します。  
  
4.  ATL シンプル オブジェクト ウィザードの [&#91;オプション&#93;](../../atl/reference/options-atl-simple-object-wizard.md) ページでプロジェクトのその他のオプションを設定します。  
  
5.  **\[完了\]** をクリックして、プロジェクトにオブジェクトを追加します。  
  
## 参照  
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [ATL プロジェクトでの新しいインターフェイスの追加](../Topic/Adding%20a%20New%20Interface%20in%20an%20ATL%20Project.md)   
 [オブジェクトへのコネクション ポイントの追加](../../atl/adding-connection-points-to-an-object.md)   
 [メソッドの追加](../../ide/adding-a-method-visual-cpp.md)   
 [MFC クラス](../../mfc/reference/adding-an-mfc-class.md)   
 [一般 C\+\+ クラスの追加](../../ide/adding-a-generic-cpp-class.md)