---
title: "CBitmap クラス | Microsoft Docs"
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
  - "CBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmap クラス"
  - "描画, ツール"
  - "GDI ビットマップ"
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBitmap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のグラフィック デバイス インターフェイス \(GDI: Graphics Device Interface\) のビットマップをカプセル化したもので、ビットマップを操作するためのメンバー関数を提供します。  
  
## 構文  
  
```  
class CBitmap : public CGdiObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CBitmap::CBitmap](../Topic/CBitmap::CBitmap.md)|`CBitmap` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBitmap::CreateBitmap](../Topic/CBitmap::CreateBitmap.md)|指定された幅、高さ、ビット パターンを持つデバイスに依存しないビットマップ メモリ内でオブジェクトを初期化します。|  
|[CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)|**BITMAP** の構造体で指定された幅、高さ、ビット パターンを含むビットマップを持つオブジェクトを \(1 バイトが指定されている場合\) 初期化します。|  
|[CBitmap::CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md)|指定されたデバイスと互換性を持つようにビットマップでオブジェクトを初期化します。|  
|[CBitmap::CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md)|指定されたデバイスと互換性のある破棄できるビットマップでオブジェクトを初期化します。|  
|[CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md)|Windows ハンドルを `HBITMAP` のビットマップに指定されている場合、`CBitmap` オブジェクトへのポインターを返します。|  
|[CBitmap::GetBitmap](../Topic/CBitmap::GetBitmap.md)|ビットマップに関する情報で **BITMAP** の構造を塗りつぶします。|  
|[CBitmap::GetBitmapBits](../Topic/CBitmap::GetBitmapBits.md)|指定したバッファーに指定したビットマップのビットをコピーします。|  
|[CBitmap::GetBitmapDimension](../Topic/CBitmap::GetBitmapDimension.md)|ビットマップの幅と高さを返します。  高さと幅は [SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md) のメンバー関数で事前に設定されていると見なされます。|  
|[CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md)|オブジェクトへのアプリケーションの実行可能ファイルから名前付きビットマップ リソースの読み込みおよびビットマップを割り当てることによってオブジェクトを初期化します。|  
|[CBitmap::LoadMappedBitmap](../Topic/CBitmap::LoadMappedBitmap.md)|ビットマップを読み込み、現在のシステム カラーに色をマップします。|  
|[CBitmap::LoadOEMBitmap](../Topic/CBitmap::LoadOEMBitmap.md)|オブジェクトへの Windows の定義済みのビットマップを読み込むこと、およびビットマップを割り当てることによってオブジェクトを初期化します。|  
|[CBitmap::SetBitmapBits](../Topic/CBitmap::SetBitmapBits.md)|指定したビット値にビットマップのビットを設定します。|  
|[CBitmap::SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md)|0.1 ミリメートル単位のビットマップの幅と高さを割り当てます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CBitmap::operator HBITMAP](../Topic/CBitmap::operator%20HBITMAP.md)|オブジェクトにアタッチされている `CBitmap` のウィンドウ ハンドルを返します。|  
  
## 解説  
 `CBitmap` のオブジェクトを使用するには、オブジェクトを構築し、初期化のメンバー関数の 1 つがでビットマップのハンドルをアタッチし、オブジェクトのメンバー関数を呼び出します。  
  
 グラフィカル オブジェクトの使用の詳細に `CBitmap`は、" "を [グラフィカル オブジェクト](../../mfc/graphic-objects.md)を使用した場合。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)