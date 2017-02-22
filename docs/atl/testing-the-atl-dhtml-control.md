---
title: "ATL DHTML コントロールのテスト | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHTML コントロール"
  - "DHTML コントロール, テスト"
  - "HTML コントロール, テスト"
  - "テスト (コントロールを)"
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL DHTML コントロールのテスト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトを作成した場合は、サンプル コントロールをビルドしてテストできます。  これを行う前に、プロジェクトを確認するには、クラス ビュー、およびソリューション エクスプローラーを使用します。  プロジェクトの要素は [DHTML コントロールのプロジェクト要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md)で詳しく説明します。  
  
#### ATL DHTML コントロールをビルドしてテストするには  
  
1.  プロジェクトをビルドします。  \[ビルド\] メニューの \[ソリューションのビルド\] をクリックします。  
  
2.  ビルドが完了したときに、テスト コンテナーを開きます。  テスト コンテナーにアクセスする方法の詳細については、[テスト コンテナーでテストのプロパティおよびイベント](../mfc/testing-properties-and-events-with-test-container.md) を参照してください。  
  
3.  テスト コンテナーで、**\[編集\]** で、メニューのをクリック **Insert New Control**。  
  
4.  **\[コントロールの挿入\]** のダイアログ ボックスで、リスト ボックスから、コントロールを選択します。  名前、基づいた ATL コントロール ウィザードで指定した短い名前に注意してください。  **\[OK\]** をクリックします。  
  
5.  コントロールをチェックします。  それにスクロール バーがあることに注意してください。  スクロール バー コントロールをアクティブにするようにサイズ変更するためにコントロールのハンドルを使用します。  
  
6.  コントロールのボタンをテストします。  背景色、ボタンによって表示される色に変更されます。  
  
7.  近いテスト コンテナー。  
  
 次に、try [DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md)。  
  
## 参照  
 [DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)