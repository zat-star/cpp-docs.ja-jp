---
title: "プロバイダーのデバッグ | Microsoft Docs"
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
  - "デバッグ [C++], プロバイダー"
  - "OLE DB プロバイダー, デバッグ"
  - "Visual C++ デバッガー"
  - "Visual C++ デバッガー, デバッグ (プロバイダーを)"
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロバイダーのデバッグ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーをデバッグするには、次の 2 つの方法があります。  
  
-   プロバイダーはプロセス内で作成されているため、OLE DB コンシューマー テンプレートを使用して一部のコンシューマー コードを作成し、通常の方法でプロバイダーをステップ実行できます。  
  
-   Visual C\+\+ に同梱されている ITEST ユーティリティを使用できます。  
  
### ITEST ユーティリティを使用するには  
  
1.  プロバイダー プロジェクトを開きます。  
  
2.  \[プロジェクト\] メニューの **\[プロパティ\]** をクリックします。  
  
3.  **\[プロパティ ページ\]** ダイアログ ボックスの \[デバッグ\] タブをクリックします。  
  
4.  \[デバッグ セッションの実行可能ファイル\] ボックスで ITEST アプリケーションを選択します。  
  
5.  通常の方法でブレークポイントを設定してデバッグします。  
  
## 参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)