---
title: "プログレス コントロールのスタイル | Microsoft Docs"
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
  - "CProgressCtrl クラス, スタイル"
  - "PBS_SMOOTH 形式"
  - "PBS_VERTICAL 形式"
  - "プログレス コントロール [C++], スタイル"
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プログレス コントロールのスタイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最初にプログレス コントロール \([CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)\) を作成すると、プログレス コントロールに目的のウィンドウ スタイルを指定するに `dwStyle` パラメーターを使用します。  次の一覧は、適度なウィンドウ スタイルについて詳しく説明します。  コントロールは、ここに示されているもの以外のウィンドウ スタイルは無視されます。  ダイアログ ボックスの親ウィンドウの子としてコントロール、通常は常に作成する必要があります。  
  
|ウィンドウ スタイル|効果|  
|----------------|--------|  
|`WS_BORDER`|ウィンドウの周りに境界が作成されます。|  
|**WS\_CHILD**|子ウィンドウを作成します。`CProgressCtrl`を必ず使用する必要があります\)。|  
|**WS\_CLIPCHILDREN**|親ウィンドウ内に描画するときの子ウィンドウが占める領域を除外します。  親ウィンドウを作成するときに使用します。|  
|**WS\_CLIPSIBLINGS**|相対的な子ウィンドウを相互切り取られます。|  
|**WS\_DISABLED**|最初に無効になるウィンドウを作成します。|  
|**WS\_VISIBLE**|最初に表示するウィンドウを作成します。|  
|**WS\_TABSTOP**|ユーザーがボタンの上に移動するには、Tab キーを押すとコントロールがフォーカスを受け取ることができることを指定します。|  
  
 さらに、プログレス コントロール、`PBS_VERTICAL` と `PBS_SMOOTH`にのみ適用される 2 種類のスタイルを指定できます。  
  
 水平方向ではなく、コントロールを垂直方向に `PBS_VERTICAL` を使用します。  使用するコントロールをインクリメント方式で満たす小さい説明した四角形を表示するのではなく、コントロールを完全に塗りつぶすために `PBS_SMOOTH` を。  
  
 `PBS_SMOOTH` のスタイル:なし  
  
 ![標準の進行状況バーのスタイル](../mfc/media/vc4ruw1.png "vc4RUW1")  
  
 `PBS_SMOOTH` と `PBS_VERTICAL` のスタイルを使用する場合:  
  
 ![進行状況バーのスタイル、スムーズおよび垂直](../mfc/media/vc4ruw2.png "vc4RUW2")  
  
 詳細については、" *MFC リファレンス"の*" [Window Styles](../mfc/reference/frame-window-styles-mfc.md) を参照します。  
  
## 参照  
 [CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)