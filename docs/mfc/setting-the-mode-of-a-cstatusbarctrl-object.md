---
title: "CStatusBarCtrl オブジェクトのモードの設定 | Microsoft Docs"
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
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl クラス, 簡易モードと標準モード"
  - "IsSimple メソッド, 使用"
  - "非簡易モード コントロールとステータス バー コントロール"
  - "SetSimple メソッド"
  - "簡易モードとステータス バー コントロール"
  - "ステータス バー コントロール, 簡易モードと標準モード"
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBarCtrl オブジェクトのモードの設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CStatusBarCtrl` オブジェクトの 2 の二つのモードがあります。:、nonsimple。  ほとんどの場合には、ステータス バー コントロールにテキストとアイコン、またはアイコンとともに一つ以上の部分があります。  これは nonsimple モードと呼ばれます。  このモードで詳細については、「[CStatusBarCtrl オブジェクトの一部の初期化](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)」を参照してください。  
  
 ただし、ApplicationScopedSettingAttribute、単一行のテキストを表示する必要がある場合もあります。  この場合、簡易モードは必要で十分です。  簡単に `CStatusBarCtrl` オブジェクトのモードを変更するには、[SetSimple](../Topic/CStatusBarCtrl::SetSimple.md) のメンバー関数の呼び出しを作成します。  ステータス バー コントロールは簡易モードの場合、**nPane** パラメーターの値として 255 を渡す **SetText** のメンバー関数を呼び出すことによって、テキストを設定します。  
  
 どのモードに `CStatusBarCtrl` オブジェクトがあるかを判断するために [IsSimple](../Topic/CStatusBarCtrl::IsSimple.md) 関数を使用できます。  
  
> [!NOTE]
>  ステータス バー オブジェクトが nonsimple から簡単に、またはその逆に変更すると、ウィンドウは直ちに再描画され、\(該当する場合は、定義した部分が自動的に復元されます。  
  
## 参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)