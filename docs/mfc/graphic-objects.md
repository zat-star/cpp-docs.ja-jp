---
title: "グラフィック オブジェクト | Microsoft Docs"
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
  - "HRGN"
  - "HFONT"
  - "HBITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ビットマップ [C++], 作成 (デバイス コンテキストで)"
  - "ブラシ, 作成 (デバイス コンテキストで)"
  - "CBitmap クラス, HBITMAP ハンドル型"
  - "CBrush クラス, HBRUSH ハンドル型"
  - "CFont クラス, HFONT ハンドル型"
  - "CPalette クラス, HPALETTE ハンドル型"
  - "CPen クラス, HPEN ハンドル型"
  - "CRgn クラス, HRGN ハンドル型"
  - "デバイス コンテキスト, グラフィック オブジェクト"
  - "描画, デバイス コンテキストで"
  - "フォント [C++], 作成 (デバイス コンテキストで)"
  - "GDI [C++], グラフィック オブジェクト クラス"
  - "GDI オブジェクト [C++]"
  - "GDI オブジェクト [C++], グラフィック オブジェクト クラス"
  - "グラフィック オブジェクト"
  - "グラフィック オブジェクト, 作成 (デバイス コンテキストで)"
  - "HBITMAP と CBitmap クラス"
  - "HBRUSH およびクラス CBrush"
  - "HFONT と CFont クラス"
  - "HPALETTE と CPalette クラス"
  - "HPEN"
  - "HRGN"
  - "イメージ [C++], グラフィック オブジェクト"
  - "メモリ [C++], ディスプレイ コンテキスト"
  - "MFC, グラフィック オブジェクト"
  - "オブジェクト [C++], グラフィック"
  - "オブジェクト [C++], グラフィック オブジェクト"
  - "描画とデバイス コンテキスト"
  - "パレット オブジェクト"
  - "パレット, 作成 (デバイス コンテキストで)"
  - "ペン オブジェクト"
  - "ペン, 作成 (デバイス コンテキストで)"
  - "領域オブジェクト"
  - "領域, 作成 (デバイス コンテキストで)"
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# グラフィック オブジェクト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows には、さまざまなデバイス コンテキストで使用する描画ツールが用意されています。  たとえば、線を描画するためのペン、内部を塗りつぶすためのブラシ、テキストを描画するためのフォントがあります。  MFC には、Windows の描画ツールと同等のグラフィック オブジェクト クラスが用意されています。  使用可能なクラスと、それに対応する Windows グラフィックス デバイス インターフェイス \(GDI\) ハンドル型を次の表に示します。  
  
> [!NOTE]
>  GDI\+ は Windows XP に含まれており、Windows NT 4.0 SP6、Windows 2000、Windows 98、および Windows Me の再頒布可能物として使用できます。  最新の再頒布可能パッケージをダウンロードするには、[http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm) を参照してください。  詳細については、MSDN で GDI\+ SDK ドキュメント \([http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp)\) を参照してください。  
  
 この記事では、これらのグラフィック オブジェクト クラスの使用方法について説明します。  
  
### Windows GDI オブジェクトのクラス  
  
|クラス|Windows のハンドル型|  
|---------|--------------------|  
|[CPen](../Topic/CPen%20Class.md)|`HPEN`|  
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|  
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|  
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|  
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|  
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|  
  
> [!NOTE]
>  [CImage](../atl-mfc-shared/reference/cimage-class.md) クラスは、ビットマップの拡張サポートを提供します。  
  
 クラス ライブラリに含まれる各グラフィック オブジェクト クラスには、そのクラスのグラフィック オブジェクトを作成するためのコンストラクターがあります。グラフィック オブジェクトは、`CreatePen` などの適切な関数を使用して初期化する必要があります。  
  
 クラス ライブラリに含まれる各グラフィック オブジェクト クラスには、MFC オブジェクトを関連付けられた Windows ハンドルにキャストするキャスト演算子があります。  結果として得られるハンドルは、関連付けられたオブジェクトによってデタッチされるまで有効です。  ハンドルをデタッチするには、オブジェクトの **Detach** メンバー関数を使用します。  
  
 次のコードは、`CPen` オブジェクトを Windows ハンドルにキャストしています。  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/CPP/graphic-objects_1.cpp)]  
  
#### デバイス コンテキストでグラフィック オブジェクトを作成するには  
  
1.  スタック フレーム上でグラフィック オブジェクトを定義します。  型に固有の作成関数 \(たとえば、`CreatePen`\) を使用して、オブジェクトを初期化します。  または、コンストラクター内でオブジェクトを初期化します。  コード例については、[1 段階での構築と 2 段階での構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)に関するページを参照してください。  
  
2.  [現在のデバイス コンテキストにオブジェクトを選択](../mfc/selecting-a-graphic-object-into-a-device-context.md)し、以前に選択されていた古いグラフィック オブジェクトを保存します。  
  
3.  現在のグラフィック オブジェクトの操作が完了したら、古いグラフィック オブジェクトをデバイス コンテキストに選択してその状態を復元します。  
  
4.  スコープが終了したときにフレームによって割り当てられたグラフィック オブジェクトが自動的に削除されるように設定します。  
  
> [!NOTE]
>  グラフィック オブジェクトを繰り返し使用する場合は、1 回割り当てておけば、後で必要になったときに各デバイス コンテキストに選択できます。  これらのオブジェクトが不要になったときは必ず削除してください。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [1 段階でのグラフィック オブジェクトの構築と 2 段階でのグラフィック オブジェクトの構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [1 段階および 2 段階でペンを作成する例](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [グラフィック オブジェクトをデバイス コンテキストに選択する](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [デバイス コンテキスト](../Topic/Device%20Contexts.md)  
  
-   [以前のオペレーティング システムにおける CImage の制限](../mfc/cimage-limitations-with-earlier-operating-systems.md)  
  
## 参照  
 [ウィンドウ オブジェクト](../mfc/window-objects.md)