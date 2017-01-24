---
title: "ActiveX コントロールのイベント ハンドラーを設定する | Microsoft Docs"
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
  - "ActiveX コントロール [C++], イベント"
  - "イベント [C++], ActiveX コントロール"
ms.assetid: c076386f-c78b-4dc9-9201-a544252d5337
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX コントロールのイベント ハンドラーを設定する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イベントに応答するには、ActiveX コントロールのインターフェイスを変更します。  プロパティで **ControlEvents** を使用して、コントロールで利用できるイベントを表示し、イベント ハンドラーを作成できます。  イベント処理の通常の目的は、データ ソース クエリの変更をトラップすることです。  変更点は以下のとおりです。  
  
-   状態監視の実装。  DBCombo ボックスなどのコントロールの値が変更されたときは、変更イベントをトラッピングして、データ コントロールのクエリを更新します。  
  
-   マスター\/詳細リレーションシップの実装。  ダイアログ ボックスに、マスター用と詳細用の 2 つのデータ コントロールを追加します。  マスター側データ ソースが変更されるたびに、イベント ハンドラーによって詳細側データ ソースのクエリが更新されます。  
  
-   エラーのトラッピング。  大部分のコントロールには、エラー イベントがあるため、これを使用してエラー ハンドラーを作成できます \(「[エラー トラッピング](../../data/ado-rdo/error-trapping.md)」を参照\)。  
  
 詳細については、「[関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)」を参照してください。  
  
## 参照  
 [ActiveX コントロールを使用する](../Topic/Using%20ActiveX%20Controls.md)