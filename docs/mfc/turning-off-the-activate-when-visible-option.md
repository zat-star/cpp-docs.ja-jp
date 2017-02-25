---
title: "[表示時にアクティブ] オプションのオフ | Microsoft Docs"
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
  - "MFC ActiveX コントロール [C++]、アクティブ化オプション"
  - "[表示時にアクティブ] オプション"
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# [表示時にアクティブ] オプションのオフ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

各コントロールには、アクティブおよび非アクティブという 2 つの基本的な状態があります。  従来、これらの状態は、コントロールがウィンドウを持つかどうかという形で判別されていました。  アクティブなコントロールはウィンドウを持ち、非アクティブなコントロールはウィンドウを持たないという分類でした。  ウィンドウなしのアクティブ状態が導入された結果、この区別はもう普遍的ではありませんが、今でも多くのコントロールに適用されます。  
  
 通常、ActiveX コントロールが実行する他の初期化と比較してウィンドウの作成はラージ コストがかかる操作です。  理想的には、コントロールは特に必要までウィンドウを作成することをお勧めします。  
  
 多くのコントロールは、コンテナーに表示されると、アクティブである必要はありません。  多くの場合、コントロールはアクティブでない状態にユーザーが、アクティブにするために必要な操作を実行するまで維持できます \(たとえば、マウスをクリックするか、Tab キーを押して\)。  コントロールをコンテナーまでアクティブでなく残存する可能性はコントロールのそのほかのフラグから削除します **OLEMISC\_ACTIVATEWHENVISIBLE** フラグをアクティブにする必要があります:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/CPP/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 **OLEMISC\_ACTIVATEWHENVISIBLE** フラグが自動的にコントロールを作成する場合は、MFC ActiveX コントロール ウィザードの [コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページの **Activate When Visible** オプションをオフにした場合は省略されます。  
  
## 参照  
 [MFC ActiveX コントロール : 最適化](../mfc/mfc-activex-controls-optimization.md)