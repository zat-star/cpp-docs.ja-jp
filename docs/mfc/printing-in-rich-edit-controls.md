---
title: "リッチ エディット コントロールでの印刷 | Microsoft Docs"
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
  - "CRichEditCtrl クラス, 印刷"
  - "印刷 [MFC], CRichEditCtrl"
  - "リッチ エディット コントロール, 印刷"
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールでの印刷
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) をプリンターなどの指定されたデバイスの出力を行うことができます。  、リッチ エディット コントロールがテキストを書式設定する出力デバイスを指定できます。  
  
 指定したデバイスのリッチ エディット コントロールの内容の一部を書式設定するには、[FormatRange](../Topic/CRichEditCtrl::FormatRange.md) メンバー関数を使用できます。  この関数で使用される [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) 構造体で書式設定するテキストの範囲を指定して、対象デバイスのデバイス コンテキスト \(DC\)。  
  
 出力デバイスのテキストの書式設定の後に、デバイスに [DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md) メンバー関数を使用して出力を送ることができます。  繰り返しで `FormatRange` と `DisplayBand`を使用して、印刷するアプリケーションはリッチ エディット コントロールのコンテンツ バンド処理を実装できます。\(バンド処理はより小さなパートに出力を印刷するために除算です\)。  
  
 リッチ エディット コントロールがテキストを書式設定するターゲット デバイスを指定するために [SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md) メンバー関数を使用できます。  この関数は、アプリケーションが画面の代わりに既定のプリンターのフォント メトリックを使用してテキストを配置する WYSIWYG \(What You によって参照する処理を\) 書式に役立ちます。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)