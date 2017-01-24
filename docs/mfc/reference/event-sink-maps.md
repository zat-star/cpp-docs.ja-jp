---
title: "イベント シンク マップ | Microsoft Docs"
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
  - "vc.mfc.macros.maps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "イベント シンク マップ"
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント シンク マップ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

埋め込まれた OLE コントロールがイベントを発生させると、コントロールのコンテナーは、MFC に用意されている "イベント シンク マップ" という機構を使用して、イベントを受信します。  このイベント シンク マップは、各イベントのパラメーターだけではなく、各イベント用のハンドラー関数も指定します。  イベント シンク マップの詳細については、「[ActiveX コントロール コンテナー](../../mfc/activex-control-containers.md)」を参照してください。  
  
### イベント シンク マップ  
  
|||  
|-|-|  
|[BEGIN\_EVENTSINK\_MAP](../Topic/BEGIN_EVENTSINK_MAP.md)|イベント シンク マップの定義を開始します。|  
|[DECLARE\_EVENTSINK\_MAP](../Topic/DECLARE_EVENTSINK_MAP.md)|イベント シンク マップを宣言します。|  
|[END\_EVENTSINK\_MAP](../Topic/END_EVENTSINK_MAP.md)|イベント シンク マップの定義を終了します。|  
|[ON\_EVENT](../Topic/ON_EVENT.md)|特定のイベントのイベント ハンドラーを定義します。|  
|[ON\_EVENT\_RANGE](../Topic/ON_EVENT_RANGE.md)|OLE コントロールのセットから発生した特定のイベントのイベント ハンドラーを定義します。|  
|[ON\_EVENT\_REFLECT](../Topic/ON_EVENT_REFLECT.md)|コントロールによって発生したイベントを、コントロールのコンテナーが処理する前に受け取ります。|  
|[ON\_PROPNOTIFY](../Topic/ON_PROPNOTIFY.md)|OLE コントロールからのプロパティ通知を処理するためのハンドラーを定義します。|  
|[ON\_PROPNOTIFY\_RANGE](../Topic/ON_PROPNOTIFY_RANGE.md)|OLE コントロールのセットからのプロパティ通知を処理するためのハンドラーを定義します。|  
|[ON\_PROPNOTIFY\_REFLECT](../Topic/ON_PROPNOTIFY_REFLECT.md)|コントロールから送信されたプロパティ通知を、コントロールのコンテナーが処理する前に受け取ります。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)