---
title: "ダイアログ ボックスの初期化 | Microsoft Docs"
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
  - "初期化 (ダイアログ ボックスを)"
  - "MFC ダイアログ ボックス, 初期化"
  - "モーダル ダイアログ ボックス, 初期化"
  - "モードレス ダイアログ ボックス, 初期化"
  - "OnInitDialog メソッド"
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイアログ ボックスの初期化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックス コントロールとすべてが作成されてから、\(いずれかの種類\) ダイアログ ボックスが画面上で表示される直前に、ダイアログ オブジェクトの [OnInitDialog](../Topic/CDialog::OnInitDialog.md) のメンバー関数が呼び出されます。  モーダル ダイアログ ボックスの場合は `DoModal` の呼び出しの間に発生します。  モードレス ダイアログ ボックスでは、`OnInitDialog` は **作成** が呼び出されるときに呼び出されます。  通常、エディット ボックスの最初のテキストの設定など、ダイアログ ボックスのコントロールを初期化するに `OnInitDialog` をオーバーライドします。  基本クラス、`OnInitDialog` のオーバーライドの `CDialog`の `OnInitDialog`、メンバー関数を呼び出す必要があります。  
  
 ダイアログ ボックスの背景色とアプリケーションの他のすべてのダイアログ ボックスの背景色を設定する場合は、[Dialog Box の背景色を設定する](../mfc/setting-the-dialog-box’s-background-color.md)を参照してください。  
  
## 参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)