---
title: "メッセージ マップ マクロ (ATL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
caps.latest.revision: 16
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メッセージ マップ マクロ (ATL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのマクロは、メッセージ マップ エントリとを定義します。  
  
|||  
|-|-|  
|[ALT\_MSG\_MAP](../Topic/ALT_MSG_MAP.md)|代替メッセージ マップの開始位置を示します。|  
|[BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)|既定のメッセージ マップの開始位置を示します。|  
|[CHAIN\_MSG\_MAP\_ALT](../Topic/CHAIN_MSG_MAP_ALT.md)|基本クラスの代替メッセージ マップのチェーン。|  
|[CHAIN\_MSG\_MAP\_ALT\_MEMBER](../Topic/CHAIN_MSG_MAP_ALT_MEMBER.md)|クラスのデータ メンバーの代替メッセージ マップのチェーン。|  
|[CHAIN\_MSG\_MAP](../Topic/CHAIN_MSG_MAP.md)|基本クラスの既定のメッセージ マップのチェーン。|  
|[CHAIN\_MSG\_MAP\_DYNAMIC](../Topic/CHAIN_MSG_MAP_DYNAMIC.md)|実行時にクラスのメッセージ マップのチェーン。|  
|[CHAIN\_MSG\_MAP\_MEMBER](../Topic/CHAIN_MSG_MAP_MEMBER.md)|クラスのデータ メンバーの既定のメッセージ マップのチェーン。|  
|[COMMAND\_CODE\_HANDLER](../Topic/COMMAND_CODE_HANDLER.md)|通知コードに基づいてハンドラー関数に **WM\_COMMAND** のメッセージが割り当てられます。|  
|[COMMAND\_HANDLER](../Topic/COMMAND_HANDLER.md)|メニュー項目、コントロール、またはアクセラレータの通知コードと識別子に基づいてハンドラー関数に **WM\_COMMAND** のメッセージが割り当てられます。|  
|[COMMAND\_ID\_HANDLER](../Topic/COMMAND_ID_HANDLER.md)|メニュー項目、コントロール、またはアクセラレータの ID に基づいてハンドラー関数に **WM\_COMMAND** のメッセージが割り当てられます。|  
|[COMMAND\_RANGE\_CODE\_HANDLER](../Topic/COMMAND_RANGE_CODE_HANDLER.md)|コントロール ID の通知コードおよび連続した範囲に基づいてハンドラー関数に **WM\_COMMAND** のメッセージが割り当てられます。|  
|[COMMAND\_RANGE\_HANDLER](../Topic/COMMAND_RANGE_HANDLER.md)|コントロール ID の連続した範囲に基づいてハンドラー関数に **WM\_COMMAND** のメッセージが割り当てられます。|  
|[DECLARE\_EMPTY\_MSG\_MAP](../Topic/DECLARE_EMPTY_MSG_MAP.md)|空のメッセージ マップを実装します。|  
|[DEFAULT\_REFLECTION\_HANDLER](../Topic/DEFAULT_REFLECTION_HANDLER.md)|別の方法で処理されないリフレクション メッセージに既定のハンドラーを提供します。|  
|[END\_MSG\_MAP](../Topic/END_MSG_MAP.md)|メッセージ マップの終了位置を示します。|  
|[FORWARD\_NOTIFICATIONS](../Topic/FORWARD_NOTIFICATIONS.md)|親ウィンドウに通知メッセージを転送します。|  
|[MESSAGE\_HANDLER](../Topic/MESSAGE_HANDLER.md)|ハンドラー関数に Windows のメッセージを割り当てます。|  
|[MESSAGE\_RANGE\_HANDLER](../Topic/MESSAGE_RANGE_HANDLER.md)|ハンドラー関数に Windows メッセージの連続する範囲をマップします。|  
|[NOTIFY\_CODE\_HANDLER](../Topic/NOTIFY_CODE_HANDLER.md)|通知コードに基づいてハンドラー関数に **WM\_NOTIFY** のメッセージが割り当てられます。|  
|[NOTIFY\_HANDLER](../Topic/NOTIFY_HANDLER.md)|通知コードとコントロール ID に基づいてハンドラー関数に **WM\_NOTIFY** のメッセージが割り当てられます。|  
|[NOTIFY\_ID\_HANDLER](../Topic/NOTIFY_ID_HANDLER.md)|コントロール ID に基づいてハンドラー関数に **WM\_NOTIFY** のメッセージが割り当てられます。|  
|[NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/NOTIFY_RANGE_CODE_HANDLER.md)|コントロール ID の通知コードおよび連続した範囲に基づいてハンドラー関数に **WM\_NOTIFY** のメッセージが割り当てられます。|  
|[NOTIFY\_RANGE\_HANDLER](../Topic/NOTIFY_RANGE_HANDLER.md)|コントロール ID の連続した範囲に基づいてハンドラー関数に **WM\_NOTIFY** のメッセージが割り当てられます。|  
|[REFLECT\_NOTIFICATIONS](../Topic/REFLECT_NOTIFICATIONS.md)|クッキーを送信するウィンドウへの通知メッセージが反映されます。|  
|[REFLECTED\_COMMAND\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_CODE_HANDLER.md)|通知コードに基づいてハンドラー関数に **WM\_COMMAND** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_COMMAND\_HANDLER](../Topic/REFLECTED_COMMAND_HANDLER.md)|メニュー項目、コントロール、またはアクセラレータの通知コードと識別子に基づいてハンドラー関数に **WM\_COMMAND** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_COMMAND\_ID\_HANDLER](../Topic/REFLECTED_COMMAND_ID_HANDLER.md)|メニュー項目、コントロール、またはアクセラレータの ID に基づいてハンドラー関数に **WM\_COMMAND** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_COMMAND\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_CODE_HANDLER.md)|コントロール ID の通知コードおよび連続した範囲に基づいてハンドラー関数に **WM\_COMMAND** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_COMMAND\_RANGE\_HANDLER](../Topic/REFLECTED_COMMAND_RANGE_HANDLER.md)|コントロール ID の連続した範囲に基づいてハンドラー関数に **WM\_COMMAND** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_NOTIFY\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_CODE_HANDLER.md)|通知コードに基づいてハンドラー関数に **WM\_NOTIFY** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_NOTIFY\_HANDLER](../Topic/REFLECTED_NOTIFY_HANDLER.md)|通知コードとコントロール ID に基づいてハンドラー関数に **WM\_NOTIFY** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_NOTIFY\_ID\_HANDLER](../Topic/REFLECTED_NOTIFY_ID_HANDLER.md)|コントロール ID に基づいてハンドラー関数に **WM\_NOTIFY** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_NOTIFY\_RANGE\_CODE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_CODE_HANDLER.md)|コントロール ID の通知コードおよび連続した範囲に基づいてハンドラー関数に **WM\_NOTIFY** のリフレクション メッセージを割り当てられます。|  
|[REFLECTED\_NOTIFY\_RANGE\_HANDLER](../Topic/REFLECTED_NOTIFY_RANGE_HANDLER.md)|コントロール ID の連続した範囲に基づいてハンドラー関数に **WM\_NOTIFY** のリフレクション メッセージを割り当てられます。|  
  
## 参照  
 [マクロ](../../atl/reference/atl-macros.md)