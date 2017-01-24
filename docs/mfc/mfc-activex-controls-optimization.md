---
title: "MFC ActiveX コントロール : 最適化 | Microsoft Docs"
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
  - "デバイス コンテキスト, クリッピングを行わない (MFC ActiveX コントロールで)"
  - "ちらつきなしの ActiveX コントロール"
  - "MFC ActiveX コントロール, アクティブ/非アクティブの状態"
  - "MFC ActiveX コントロール, ちらつきなし"
  - "MFC ActiveX コントロール, マウスの反応"
  - "MFC ActiveX コントロール, 最適化"
  - "MFC ActiveX コントロール, ウィンドウなしの"
  - "最適化, ActiveX コントロール"
  - "最適化 (パフォーマンスの), ActiveX コントロール"
  - "パフォーマンス, ActiveX コントロール"
  - "ウィンドウなしの MFC ActiveX コントロール"
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : 最適化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、パフォーマンスの ActiveX コントロールを最適化するために使用できる手法を示します。  
  
 トピック [アクティブ化をオフにするときに表示されるオプション](../mfc/turning-off-the-activate-when-visible-option.md) と [アクティブでない間マウス操作の提供](../Topic/Providing%20Mouse%20Interaction%20While%20Inactive.md) がアクティブ化されるまでのウィンドウを作成するコントロールについて説明します。  使用する場合にも、トピック [ウィンドウなしでアクティブの提供](../mfc/providing-windowless-activation.md) は、ウィンドウを作成するコントロールについて説明します。  
  
 Windows に OLE オブジェクトの 2 種類の主要な欠点があります: これらはアクティブおよびコントロールのインスタンス化と表示に大量のオーバーヘッドを追加すると、オブジェクトが透明または四角形でないようにします。  通常、ウィンドウを作成すると、コントロールの作成時に 60 を要します。  単一の共有ウィンドウ \(通常はコンテナー\) およびディスパッチ コードでは、コントロールはパフォーマンスを失わずに同じウィンドウ サービスは、一般に受け取ります。  ウィンドウをオブジェクトの大部分が不要なオーバーヘッドが持つことで、  
  
 一部の最適化は、コントロールが特定のコンテナーで使用される場合のパフォーマンスが向上します。  たとえば、1996 より前にリリースされたコンテナーがウィンドウなしのアクティベーションをサポートしていないため、この機能を実装すると、古いコンテナーの利点はありません。  ただし、ほとんどのコンテナー サポートの永続性、つまりコントロールの永続化コードを最適化することによって、コンテナーのパフォーマンスが向上します。  コントロールは、コンテナーの 1 種類の特定の型で使用されるようになっている場合、最適化は、コンテナーでサポートされる調査する必要があります。  ただし、通常は、多数のコンテナーで、同じように、特定のコントロールに適用されるも行うコントロールを確認するには、これらの手法の大部分が実装することをお勧めします。  
  
 [コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページの [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)してこれらの最適化の多くが、実装できます。  
  
### MFC ActiveX コントロール ウィザードの OLE 最適化オプション  
  
|MFC ActiveX コントロール ウィザードのコントロール設定|アクション|詳細情報|  
|---------------------------------------|-----------|----------|  
|**Activate when visible** チェック ボックス|Clear|[アクティブ化をオフにするときに表示されるオプション](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**ウィンドウなしでアクティブ\(S\)** チェック ボックス|選択|[ウィンドウなしでアクティブの提供](../mfc/providing-windowless-activation.md)|  
|**クリッピングを行わないデバイス コンテキスト\(U\)** チェック ボックス|選択|[表示 Device Context を使用する](../mfc/using-an-unclipped-device-context.md)|  
|**ちらつきなしでアクティブ化\(V\)** チェック ボックス|選択|[ちらつきなしのアクティベーションの提供](../mfc/providing-flicker-free-activation.md)|  
|**非アクティブ時のマウス ポインター通知\(M\)** チェック ボックス|選択|[アクティブでない間マウス操作の提供](../Topic/Providing%20Mouse%20Interaction%20While%20Inactive.md)|  
|**最適化された描画コード\(P\)** チェック ボックス|選択|[Optimizing Control Drawing](../mfc/optimizing-control-drawing.md)|  
  
 これらの最適化を実装するメンバー関数の詳細については、「[COleControl](../mfc/reference/colecontrol-class.md)」を参照してください。  このメンバー関数は [操作ウィンドウなし](http://msdn.microsoft.com/ja-jp/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) と [アクティブでないポインターの処理関数](http://msdn.microsoft.com/ja-jp/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df)のように使用して、表示されます。  
  
 詳細については、次のトピックを参照してください。  
  
-   [最適化の永続性と初期化](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [ウィンドウなしでアクティブの提供](../mfc/providing-windowless-activation.md)  
  
-   [アクティブ化をオフにするときに表示されるオプション](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [アクティブでない間マウス操作の提供](../Topic/Providing%20Mouse%20Interaction%20While%20Inactive.md)  
  
-   [ちらつきなしのアクティベーションの提供](../mfc/providing-flicker-free-activation.md)  
  
-   [表示 Device Context を使用する](../mfc/using-an-unclipped-device-context.md)  
  
-   [Optimizing Control Drawing](../mfc/optimizing-control-drawing.md)  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)