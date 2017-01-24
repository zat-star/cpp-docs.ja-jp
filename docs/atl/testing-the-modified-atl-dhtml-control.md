---
title: "変更した ATL DHTML コントロールのテスト | Microsoft Docs"
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
  - "DHTML コントロール, テスト"
  - "HTML コントロール, テスト"
  - "テスト (コントロールを)"
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 変更した ATL DHTML コントロールのテスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在の動作を確認するには、新しいコントロールをテストします。  
  
#### 変更したコントロールをビルドしてテストするには  
  
1.  プロジェクトを再度ビルドし、テスト コンテナーで開きます。  テスト コンテナーにアクセスする方法の詳細については、[テスト コンテナーでテストのプロパティおよびイベント](../mfc/testing-properties-and-events-with-test-container.md) を参照してください。  
  
     追加したすべてのボタンを表示するようにコントロールのサイズを変更します。  
  
2.  、HTML 変更によって挿入される 2 ボタンを確認します。  各ボタンは、で [ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)で指定したラベルに耐えます: **最新の情報に更新** と **HelloHTML**。  
  
3.  の動作を確認するには、2 種類の新しいボタンをテストします。  
  
 これで、UI の一部ではなくメソッドをテストします。  
  
1.  コントロールを強調表示し、その境界線がアクティブになります。  
  
2.  **コントロール** で、メニューの **Invoke Methods**をクリックします。  
  
 **\[メソッド名\]** ラベルとリストのメソッドを呼び出して、コンテナーのできるメソッドです: `MethodInvoked`と`GoToURL`。  他のすべてのメソッドは、UI によって制御されます。  
  
1.  `Invoke` を起動し、メソッドのメッセージ ボックスを表示するか、www.microsoft.com に移動するには、をクリックするか、メソッドを選択します。  
  
2.  **Invoke Methods** のダイアログ ボックスで、**\[終値\]**をクリックします。  
  
 ATL DHTML コントロールを構成するファイルとさまざまな要素について学習するには、[DHTML コントロールのプロジェクト要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)を参照してください。  
  
## 参照  
 [DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)