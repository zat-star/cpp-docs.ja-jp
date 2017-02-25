---
title: "CD2DBitmapBrush クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DBitmapBrush"
  - "afxrendertarget/CD2DBitmapBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmapBrush クラス"
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DBitmapBrush クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1BitmapBrush のラッパー。  
  
## 構文  
  
```  
class CD2DBitmapBrush : public CD2DBrush;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmapBrush::CD2DBitmapBrush](../Topic/CD2DBitmapBrush::CD2DBitmapBrush.md)|オーバーロードされます。  ファイルから CD2DBitmapBrush オブジェクトを構築します。|  
|[CD2DBitmapBrush::~CD2DBitmapBrush](../Topic/CD2DBitmapBrush::~CD2DBitmapBrush.md)|デストラクターです。  D2D ビットマップ ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmapBrush::Attach](../Topic/CD2DBitmapBrush::Attach.md)|既存のリソース インターフェイスをオブジェクトにアタッチします。|  
|[CD2DBitmapBrush::Create](../Topic/CD2DBitmapBrush::Create.md)|CD2DBitmapBrush を作成します。  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) をオーバーライドします\)。|  
|[CD2DBitmapBrush::Destroy](../Topic/CD2DBitmapBrush::Destroy.md)|CD2DBitmapBrush オブジェクトを破棄します。  \([CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md) をオーバーライドします\)。|  
|[CD2DBitmapBrush::Detach](../Topic/CD2DBitmapBrush::Detach.md)|リソース インターフェイスをオブジェクトからデタッチします。|  
|[CD2DBitmapBrush::Get](../Topic/CD2DBitmapBrush::Get.md)|ID2D1BitmapBrush インターフェイスを返します。|  
|[CD2DBitmapBrush::GetBitmap](../Topic/CD2DBitmapBrush::GetBitmap.md)|このブラシで描画する際に使用するビットマップ ソースを取得します。|  
|[CD2DBitmapBrush::GetExtendModeX](../Topic/CD2DBitmapBrush::GetExtendModeX.md)|ビットマップを越える領域を水平方向に並べるためにブラシが使用する方法を取得します。|  
|[CD2DBitmapBrush::GetExtendModeY](../Topic/CD2DBitmapBrush::GetExtendModeY.md)|ビットマップを越える領域を垂直方向に並べるためにブラシが使用する方法を取得します。|  
|[CD2DBitmapBrush::GetInterpolationMode](../Topic/CD2DBitmapBrush::GetInterpolationMode.md)|ブラシのビットマップのスケーリングまたは回転を行うときに使用する補間方法を取得します。|  
|[CD2DBitmapBrush::SetBitmap](../Topic/CD2DBitmapBrush::SetBitmap.md)|このブラシで描画する際に使用するビットマップ ソースを指定します。|  
|[CD2DBitmapBrush::SetExtendModeX](../Topic/CD2DBitmapBrush::SetExtendModeX.md)|ビットマップを越える領域を水平方向に並べるためにブラシが使用する方法を指定します。|  
|[CD2DBitmapBrush::SetExtendModeY](../Topic/CD2DBitmapBrush::SetExtendModeY.md)|ビットマップを越える領域を垂直方向に並べるためにブラシが使用する方法を指定します。|  
|[CD2DBitmapBrush::SetInterpolationMode](../Topic/CD2DBitmapBrush::SetInterpolationMode.md)|ブラシのビットマップのスケーリングまたは回転を行うときに使用する補間モードを指定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmapBrush::CommonInit](../Topic/CD2DBitmapBrush::CommonInit.md)|オブジェクトを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmapBrush::operator ID2D1BitmapBrush\*](../Topic/CD2DBitmapBrush::operator%20ID2D1BitmapBrush*.md)|ID2D1BitmapBrush インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmapBrush::m\_pBitmap](../Topic/CD2DBitmapBrush::m_pBitmap.md)|CD2DBitmap オブジェクトへのポインターを格納します。|  
|[CD2DBitmapBrush::m\_pBitmapBrush](../Topic/CD2DBitmapBrush::m_pBitmapBrush.md)|ID2D1BitmapBrush オブジェクトへのポインターを格納します。|  
|[CD2DBitmapBrush::m\_pBitmapBrushProperties](../Topic/CD2DBitmapBrush::m_pBitmapBrushProperties.md)|ビットマップ ブラシのプロパティ。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DBitmapBrush](../../mfc/reference/cd2dbitmapbrush-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)