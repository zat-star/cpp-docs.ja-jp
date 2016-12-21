---
title: "CBrush クラス | Microsoft Docs"
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
  - "CBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブラシ, CBrush クラス"
  - "CBrush クラス"
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBrush クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のグラフィック デバイス インターフェイス \(GDI\) のブラシをカプセル化します。  
  
## 構文  
  
```  
class CBrush : public CGdiObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CBrush::CBrush](../Topic/CBrush::CBrush.md)|`CBrush` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBrush::CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md)|[LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) の構造体に指定されたスタイル、色やパターンを持つブラシを初期化します。|  
|[CBrush::CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md)|デバイスに依存しないビットマップ \(DIB\) によって指定されるパターンで、ブラシを初期化します。|  
|[CBrush::CreateHatchBrush](../Topic/CBrush::CreateHatchBrush.md)|指定したハッチ パターンと色のブラシを初期化します。|  
|[CBrush::CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md)|ビットマップで指定されるパターンで、ブラシを初期化します。|  
|[CBrush::CreateSolidBrush](../Topic/CBrush::CreateSolidBrush.md)|指定した純色のブラシを初期化します。|  
|[CBrush::CreateSysColorBrush](../Topic/CBrush::CreateSysColorBrush.md)|既定のシステム カラーであるブラシを作成します。|  
|[CBrush::FromHandle](../Topic/CBrush::FromHandle.md)|Windows ハンドルを `HBRUSH` のオブジェクトに指定されている場合、`CBrush` オブジェクトへのポインターを返します。|  
|[CBrush::GetLogBrush](../Topic/CBrush::GetLogBrush.md)|[LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) の構造を取得します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CBrush::operator HBRUSH](../Topic/CBrush::operator%20HBRUSH.md)|オブジェクトにアタッチされている `CBrush` のウィンドウ ハンドルを返します。|  
  
## 解説  
 `CBrush` のオブジェクトを使用し、`CBrush` オブジェクトを構築し、ブラシを必要とする `CDC` のメンバー関数に渡します。  
  
 ソリッド ブラシは、ハッチングされたか、ダミーされます。  
  
 `CBrush`の詳細については、[グラフィカル オブジェクト](../../mfc/graphic-objects.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC PROPDLG サンプル](../../top/visual-cpp-samples.md)   
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CDC クラス](../Topic/CDC%20Class.md)