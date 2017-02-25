---
title: "通常オーバーライドされるメンバー関数 | Microsoft Docs"
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
  - "CDialog クラス, メンバー"
  - "ダイアログ クラス, 通常オーバーライドされるメンバー関数"
  - "MFC ダイアログ ボックス, オーバーライド (メンバー関数を)"
  - "OnCancel 関数"
  - "OnInitDialog 関数"
  - "OnOK 関数"
  - "オーバーライド, ダイアログ クラス メンバー"
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 通常オーバーライドされるメンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は `CDialog`\-派生クラスでオーバーライドする可能性が高いメンバー関数の一覧です。  
  
### 一般に、CDialog クラスのオーバーライドされたメンバー関数  
  
|メンバー関数|これは、メッセージに応答します。|オーバーライドの目的|  
|------------|----------------------|----------------|  
|`OnInitDialog`|**WM\_INITDIALOG**|ダイアログ ボックスのコントロールを初期化してください。|  
|`OnOK`|ボタン **IDOK**の**BN\_CLICKED**|ユーザーが OK ボタンをクリックしたときに応答します。|  
|`OnCancel`|ボタン **IDCANCEL**の**BN\_CLICKED**|ユーザーが Cancel ボタンをクリックしたときに応答します。|  
  
 `OnInitDialog`、`OnOK`と `OnCancel` は仮想関数です。  これらをオーバーライドするには、[プロパティ ウィンドウ](../Topic/Properties%20Window.md)を使用して派生ダイアログ クラスのオーバーライド関数を宣言します。  
  
 `OnInitDialog` は ダイアログ ボックスが表示される直前に呼び出されます。  ハンドラーの最初のアクションとしてオーバーライドの既定の `OnInitDialog` —通常ハンドラーを呼び出す必要があります。  既定で、`OnInitDialog` にフォーカスがダイアログ ボックスの最初のコントロールに設定する必要があることを示すために **TRUE** を返します。  
  
 `OnOK` は モードレス、モーダル ダイアログ ボックスの場合は、通常はオーバーライドされます。  モーダル ダイアログ ボックスのこのハンドラーをオーバーライドした場合は、— `EndDialog` が呼び出されることを確認するようにオーバーライド—または独自 `EndDialog` 呼び出しから基本クラスのバージョンを呼び出します。  
  
 `OnCancel` は 通常、モードレス ダイアログ ボックス用にオーバーライドされます。  
  
 これらのメンバー関数に関する詳細については、" *MFC リファレンス"の* 対応するクラス [CDialog](../mfc/reference/cdialog-class.md) と [Dialog Box の Life Cycle](../mfc/life-cycle-of-a-dialog-box.md)の説明を参照します。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [通常追加されるメンバー関数](../Topic/Commonly%20Added%20Member%20Functions.md)