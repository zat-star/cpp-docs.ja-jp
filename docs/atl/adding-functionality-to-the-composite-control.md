---
title: "複合コントロールへの機能の追加 | Microsoft Docs"
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
  - "ActiveX コントロール [C++], イベント"
  - "複合コントロール, 処理 (イベントを)"
  - "イベント ハンドラー [C++], ActiveX コントロール"
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 複合コントロールへの機能の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

複合コントロールに必要なコントロールを挿入し、次は、新しい機能を追加します。  この新しい機能は、通常 2 種類に分類されます:  
  
-   さらに、特定の機能をサポートする追加のインターフェイスと、複合コントロールの動作をカスタマイズする。  
  
-   含まれている ActiveX コントロール \(またはコントロール\) からのイベントを処理する。  
  
 この記事の目的と範囲の場合、このセクションの後半では、ActiveX コントロールからのイベント処理のみに焦点を絞ります。  
  
> [!NOTE]
>  Windows コントロールからのメッセージを処理する必要がある場合は、ATL のメッセージ処理の詳細については [ウィンドウの実行](../atl/implementing-a-window.md) を参照してください。  
  
 ダイアログ リソースの ActiveX コントロールを挿入したら、コントロールを右クリックし、**\[イベント ハンドラーの追加\]**をクリックします。  、**\[追加して編集\]**を処理し、をクリックするイベントを選択します。  イベント ハンドラー コードは、コントロールの .h ファイルに追加されます。  
  
 [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)への複合コントロールの ActiveX コントロールのコネクション ポイントは自動的に呼び出しによって接続されており、ドロップします。  
  
## 参照  
 [複合コントロールの基本](../Topic/ATL%20Composite%20Control%20Fundamentals.md)