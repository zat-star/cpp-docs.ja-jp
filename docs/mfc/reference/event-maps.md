---
title: "イベント マップ | Microsoft Docs"
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
  - "イベント マップ"
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント マップ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ある動作 \(キーストローク、マウス クリック、コントロールの状態変更などの動作で、コントロールの開発者が決定します\) が発生したことをコントロールがコンテナーに通知するときは、イベント起動関数が呼び出されます。  この関数は、ある重要な動作が発生したときに、関連するイベントを起動することによって、コントロールのコンテナーにそれを通知します。  
  
 Microsoft Foundation Class ライブラリには、イベントの起動に最適化されたプログラミング モデルが用意されています。  このモデルでは、特定のコントロールに対してどの関数がどのイベントを発生させるかを指定した "イベント マップ" を使用します。  イベント マップには、イベントごとに 1 つのマクロがあります。  たとえば、ストック Click イベントを発生させるイベント マップは次のようになります。  
  
 [!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/CPP/event-maps_1.cpp)]  
  
 **EVENT\_STOCK\_CLICK** マクロは、コントロールがマウス クリックを検知するたびにストック Click イベントが発生することを示します。  ほかのストック イベントの詳細については、「[MFC ActiveX コントロール : イベント](../../mfc/mfc-activex-controls-events.md)」を参照してください。  マクロはカスタム イベントを示すためにも使用できます。  
  
 イベント マップ マクロは重要なマクロですが、通常は直接記述しません。  これは、ユーザーがイベントとイベント起動関数を関連付けると、\[プロパティ\] ウィンドウでイベント マップ エントリがソース ファイルに自動的に作成されるためです。  イベント マップ エントリは、\[プロパティ\] ウィンドウでいつでも編集および追加できます。  
  
 イベント マップをサポートするため、MFC には次のマクロが用意されています。  
  
### イベント マップの宣言と境界設定  
  
|||  
|-|-|  
|[DECLARE\_EVENT\_MAP](../Topic/DECLARE_EVENT_MAP.md)|イベントをイベント起動関数に割り当てるためにクラスでイベント マップを使用することを宣言します。クラスの宣言の中で使用する必要があります。|  
|[BEGIN\_EVENT\_MAP](../Topic/BEGIN_EVENT_MAP.md)|イベント マップの定義を開始します。クラスの実装の中で使用する必要があります。|  
|[END\_EVENT\_MAP](../Topic/END_EVENT_MAP.md)|イベント マップの定義を終了します。クラスの実装の中で使用する必要があります。|  
  
### イベント マップ マクロ  
  
|||  
|-|-|  
|[EVENT\_CUSTOM](../Topic/EVENT_CUSTOM.md)|指定したイベントを発生させるイベント起動関数を示します。|  
|[EVENT\_CUSTOM\_ID](../Topic/EVENT_CUSTOM_ID.md)|指定したディスパッチ ID を使用して、指定したイベントを発生させるイベント起動関数を示します。|  
  
### メッセージ マップ マクロ  
  
|||  
|-|-|  
|[ON\_OLEVERB](../Topic/ON_OLEVERB.md)|OLE コントロールが処理するカスタム動詞を示します。|  
|[ON\_STDOLEVERB](../Topic/ON_STDOLEVERB.md)|OLE コントロールの標準動詞マップをオーバーライドします。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)