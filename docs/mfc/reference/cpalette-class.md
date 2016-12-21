---
title: "CPalette クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPalette"
  - "HPALETTE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "カラー パレット, MFC"
  - "CPalette クラス"
  - "HPALETTE"
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPalette クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のカラー パレットをカプセル化します。  
  
## 構文  
  
```  
class CPalette : public CGdiObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CPalette::CPalette](../Topic/CPalette::CPalette.md)|Windows のアタッチされたパレットを持たない `CPalette` オブジェクトを構築します。  使用する前に初期化のメンバー関数の 1 個の `CPalette` のオブジェクトを初期化する必要があります。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md)|`CPalette` によって識別される論理パレット内のエントリを追加します。  アプリケーションは、Windows がシステム パレットに新しいエントリを直ちにマッピングされるため、クライアント領域を更新する必要はありません。|  
|[CPalette::CreateHalftonePalette](../Topic/CPalette::CreateHalftonePalette.md)|デバイス コンテキストのハーフトーン パレットを作成し、`CPalette` のオブジェクトにアタッチします。|  
|[CPalette::CreatePalette](../Topic/CPalette::CreatePalette.md)|Windows のカラー パレットを作成し、`CPalette` のオブジェクトにアタッチします。|  
|[CPalette::FromHandle](../Topic/CPalette::FromHandle.md)|ハンドルは、Windows のパレット オブジェクトに指定されている場合、`CPalette` オブジェクトへのポインターを返します。|  
|[CPalette::GetEntryCount](../Topic/CPalette::GetEntryCount.md)|論理パレットのカラー パレット エントリの数を取得します。|  
|[CPalette::GetNearestPaletteIndex](../Topic/CPalette::GetNearestPaletteIndex.md)|に最も近い色の値と一致する論理パレット エントリのインデックスを返します。|  
|[CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)|論理パレットのカラー パレット エントリの範囲を取得します。|  
|[CPalette::ResizePalette](../Topic/CPalette::ResizePalette.md)|エントリの指定した数への `CPalette` のオブジェクトによって指定された論理パレットのサイズを変更します。|  
|[CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)|RGB カラー値を設定し、論理パレット エントリのスコープでフラグ。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CPalette::operator HPALETTE](../Topic/CPalette::operator%20HPALETTE.md)|アタッチされた `CPalette`に `HPALETTE` を返します。|  
  
## 解説  
 パレットは、アプリケーションと色の出力デバイス間のインターフェイスを提供します \(ディスプレイ デバイスなど\)。  インターフェイスは、他のアプリケーションによって表示される色と動作に干渉しない出力デバイスの色の機能を最大限に活用できます。  Windows は、アプリケーションの論理パレット \(必要な色のリスト\) および \(使用できる色を定義する\) 使用する色を決定するためにシステム パレット使用します。  
  
 `CPalette` のオブジェクトはオブジェクトによって参照されるパレットを操作するメンバー関数を提供します。  `CPalette` オブジェクトを構築し、実際のカラー パレット、グラフィック デバイス インターフェイス \(GDI\) の \(GDI\) のオブジェクトを作成し、エントリおよびそのほかのプロパティを処理するためにメンバー関数を使用します。  
  
 `CPalette`の使用の詳細については、[グラフィカル オブジェクト](../../mfc/graphic-objects.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC DIBLOOK サンプル](../../top/visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)   
 [CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)