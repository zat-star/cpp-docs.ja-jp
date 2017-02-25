---
title: "CD2DBitmap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DBitmap"
  - "CD2DBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBitmap クラス"
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DBitmap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Bitmap のラッパー。  
  
## 構文  
  
```  
class CD2DBitmap : public CD2DResource;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|オーバーロードされます。  HBITMAP から CD2DBitmap オブジェクトを構築します。|  
|[CD2DBitmap::~CD2DBitmap](../Topic/CD2DBitmap::~CD2DBitmap.md)|デストラクターです。  D2D ビットマップ オブジェクトが破棄されるときに呼び出されます。|  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmap::CD2DBitmap](../Topic/CD2DBitmap::CD2DBitmap.md)|オーバーロードされます。  CD2DBitmap オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmap::Attach](../Topic/CD2DBitmap::Attach.md)|既存のリソース インターフェイスをオブジェクトにアタッチします。|  
|[CD2DBitmap::CopyFromBitmap](../Topic/CD2DBitmap::CopyFromBitmap.md)|指定したビットマップの指定した領域を現在のビットマップにコピーします。|  
|[CD2DBitmap::CopyFromMemory](../Topic/CD2DBitmap::CopyFromMemory.md)|指定したメモリの指定した領域を現在のビットマップにコピーします。|  
|[CD2DBitmap::CopyFromRenderTarget](../Topic/CD2DBitmap::CopyFromRenderTarget.md)|指定したレンダー ターゲットの指定した領域を現在のビットマップにコピーします。|  
|[CD2DBitmap::Create](../Topic/CD2DBitmap::Create.md)|CD2DBitmap を作成します。  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) をオーバーライドします\)。|  
|[CD2DBitmap::Destroy](../Topic/CD2DBitmap::Destroy.md)|CD2DBitmap オブジェクトを破棄します。  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) をオーバーライドします\)。|  
|[CD2DBitmap::Detach](../Topic/CD2DBitmap::Detach.md)|リソース インターフェイスをオブジェクトからデタッチします。|  
|[CD2DBitmap::Get](../Topic/CD2DBitmap::Get.md)|ID2D1Bitmap インターフェイスを返します。|  
|[CD2DBitmap::GetDPI](../Topic/CD2DBitmap::GetDPI.md)|ビットマップの DPI \(1 インチあたりのドット数\) を返します。|  
|[CD2DBitmap::GetPixelFormat](../Topic/CD2DBitmap::GetPixelFormat.md)|ビットマップのピクセル形式とアルファ モードを取得します。|  
|[CD2DBitmap::GetPixelSize](../Topic/CD2DBitmap::GetPixelSize.md)|デバイスに依存する単位 \(ピクセル\) で表されたビットマップのサイズを返します。|  
|[CD2DBitmap::GetSize](../Topic/CD2DBitmap::GetSize.md)|デバイスに依存しないピクセル \(DIP\) で表されたビットマップのサイズを返します。|  
|[CD2DBitmap::IsValid](../Topic/CD2DBitmap::IsValid.md)|リソースの有効性を検証します \([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) をオーバーライドします\)。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmap::CommonInit](../Topic/CD2DBitmap::CommonInit.md)|オブジェクトを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmap::operator ID2D1Bitmap\*](../Topic/CD2DBitmap::operator%20ID2D1Bitmap*.md)|ID2D1Bitmap インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CD2DBitmap::m\_bAutoDestroyHBMP](../Topic/CD2DBitmap::m_bAutoDestroyHBMP.md)|m\_hBmpSrc を破棄する場合は TRUE、それ以外の場合は FALSE。|  
|[CD2DBitmap::m\_hBmpSrc](../Topic/CD2DBitmap::m_hBmpSrc.md)|ソース ビットマップのハンドル。|  
|[CD2DBitmap::m\_lpszType](../Topic/CD2DBitmap::m_lpszType.md)|リソースの種類。|  
|[CD2DBitmap::m\_pBitmap](../Topic/CD2DBitmap::m_pBitmap.md)|ID2D1Bitmap オブジェクトへのポインターを格納します。|  
|[CD2DBitmap::m\_sizeDest](../Topic/CD2DBitmap::m_sizeDest.md)|ビットマップの描画サイズ。|  
|[CD2DBitmap::m\_strPath](../Topic/CD2DBitmap::m_strPath.md)|ビットマップ ファイルのパス。|  
|[CD2DBitmap::m\_uiResID](../Topic/CD2DBitmap::m_uiResID.md)|ビットマップ リソース ID。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CD2DResource](../Topic/CD2DResource%20Class.md)  
  
 [CD2DBitmap](../../mfc/reference/cd2dbitmap-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)