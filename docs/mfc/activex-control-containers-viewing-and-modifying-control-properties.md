---
title: "ActiveX コントロール コンテナー : コントロール プロパティの表示と変更 | Microsoft Docs"
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
  - "ActiveX コントロール コンテナー [C++], 表示と変更 (プロパティの)"
  - "ActiveX コントロール [C++], プロパティ"
  - "コントロール [MFC], プロパティ"
  - "プロパティ [MFC], 表示と変更"
  - "リソース エディター, 表示と変更 (ActiveX コントロールの)"
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX コントロール コンテナー : コントロール プロパティの表示と変更
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクトに ActiveX コントロールを挿入する場合、ActiveX コントロールでサポートされているプロパティを表示および変更すると便利です。  ここでは、これは Visual C\+\+ リソース エディターを使用する方法について説明します。  
  
 ActiveX コントロール コンテナー アプリケーションの埋め込みコントロールを使用する場合は、リソース エディターでコントロールのプロパティを表示および変更できます。  また、デザイン時に設定されたプロパティ値は、リソース エディターを使用できます。  リソース エディターでは、自動的にプロジェクトのリソース ファイルには、これらの値を格納します。  コントロールのインスタンスには、これらの値に初期化されたプロパティがあります。  
  
 この手順では、プロジェクトにコントロールを挿入することを前提としています。  詳細については、「[ActiveX コントロール コンテナー: コントロール コンテナー アプリケーションにコントロールを挿入できます。](../mfc/inserting-a-control-into-a-control-container-application.md)」を参照してください。  
  
 コントロールのプロパティを表示するには、まず、プロジェクト ダイアログ テンプレートにコントロールのインスタンスを追加します。  
  
### コントロールのプロパティを表示するには  
  
1.  リソース ビューで、**ダイアログ** フォルダーを開きます。  
  
2.  メイン ダイアログ ボックスのテンプレートを開きます。  
  
3.  **\[ActiveX コントロールの挿入\]** ダイアログ ボックスを使用して ActiveX コントロールを挿入します。  詳細については、「[ActiveX コントロールを Dialog Box に表示して追加します。](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md)」を参照してください。  
  
4.  ダイアログ ボックスに ActiveX コントロールを選択します。  
  
5.  プロパティ ウィンドウで、**\[プロパティ\]** ボタンをクリックします。  
  
 新しいプロパティを直ちに修正およびテストに **\[プロパティ\]** ダイアログ ボックスを使用します。  
  
## 参照  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)