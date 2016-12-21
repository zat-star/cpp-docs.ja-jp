---
title: "CImage クラス | Microsoft Docs"
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
  - "CImage"
  - "ATL.CImage"
  - "ATL::CImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".gif ファイル, ATL と MFC のサポート"
  - "ビットマップ [C++], ATL と MFC のサポート"
  - "CImage クラス"
  - "gif ファイル, ATL と MFC のサポート"
  - "イメージ [C++], ATL と MFC のサポート"
  - "jpeg ファイル"
  - "PNG ファイル, ATL と MFC のサポート"
  - "透明色"
ms.assetid: 52861e3d-bf7e-481f-a240-90e88f76c490
caps.latest.revision: 20
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CImage クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CImage` は、BMP、GIF、JPEG、PNG \(Portable Network Graphics \(PNG\) の形式のイメージの読み込みや保存などが強化されたビットマップ サポートを提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CImage  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CImage::CImage](../Topic/CImage::CImage.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CImage::AlphaBlend](../Topic/CImage::AlphaBlend.md)|透明または半透明のピクセルがあるビットマップを表示します。|  
|[CImage::Attach](../Topic/CImage::Attach.md)|`CImage` のオブジェクトに `HBITMAP` をアタッチします。  非 DIB セクションのビットマップまたは DIB セクションのビットマップを使用できます。|  
|[CImage::BitBlt](../Topic/CImage::BitBlt.md)|元のデバイス コンテキストからこの現在のデバイス コンテキストにビットマップをコピーします。|  
|[CImage::Create](../Topic/CImage::Create.md)|DIB セクションのビットマップを作成し、`CImage` の前に構築されたオブジェクトにアタッチします。|  
|[CImage::CreateEx](../Topic/CImage::CreateEx.md)|`CImage` の前に構築されたオブジェクトにビットマップ \(DIB セクションの追加のパラメーターとともにアタッチし、を作成します。|  
|[CImage::Destroy](../Topic/CImage::Destroy.md)|`CImage` のオブジェクトからビットマップをデタッチし、ビットマップを破棄します。|  
|[CImage::Detach](../Topic/CImage::Detach.md)|`CImage` のオブジェクトからビットマップをデタッチします。|  
|[CImage::Draw](../Topic/CImage::Draw.md)|コピー先の四角形に元の四角形からビットマップをコピーします。  **\[描画\]** は伸縮したり、描画先の四角形の寸法に収まるように必要に応じてビットマップを圧縮し、アルファ ブレンドと透明な色を処理します。|  
|[CImage::GetBits](../Topic/CImage::GetBits.md)|ビットマップの実際のピクセル値へのポインターを取得します。|  
|[CImage::GetBPP](../Topic/CImage::GetBPP.md)|ピクセルを取得します。|  
|[CImage::GetColorTable](../Topic/CImage::GetColorTable.md)|色テーブルのエントリの範囲から赤、緑、青 \(RGB\) のカラー値を取得します。|  
|[CImage::GetDC](../Topic/CImage::GetDC.md)|現在のビットマップが選択されたデバイス コンテキストを取得します。|  
|[CImage::GetExporterFilterString](../Topic/CImage::GetExporterFilterString.md)|使用可能なイメージ形式と説明を検索します。|  
|[CImage::GetHeight](../Topic/CImage::GetHeight.md)|ピクセルの現在のイメージの高さを取得します。|  
|[CImage::GetImporterFilterString](../Topic/CImage::GetImporterFilterString.md)|使用可能なイメージ形式と説明を検索します。|  
|[CImage::GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)|色テーブルのエントリの最大数を取得します。|  
|[CImage::GetPitch](../Topic/CImage::GetPitch.md)|バイトの現在のイメージの距離を取得します。|  
|[CImage::GetPixel](../Topic/CImage::GetPixel.md)|*x* と *y.*で指定したピクセルの色を取得します。|  
|[CImage::GetPixelAddress](../Topic/CImage::GetPixelAddress.md)|特定のピクセルのアドレスを取得します。|  
|[CImage::GetTransparentColor](../Topic/CImage::GetTransparentColor.md)|色テーブルの透明色の位置を取得します。|  
|[CImage::GetWidth](../Topic/CImage::GetWidth.md)|ピクセルの現在のイメージの幅を取得します。|  
|[CImage::IsDIBSection](../Topic/CImage::IsDIBSection.md)|アタッチされているビットマップの DIB セクションであるかどうかを判定します。|  
|[CImage::IsIndexed](../Topic/CImage::IsIndexed.md)|ビットマップの色がパレット インデックスにマップされていることを示します。|  
|[CImage::IsNull](../Topic/CImage::IsNull.md)|ソース ビットマップが現在読み込まれている示します。|  
|[CImage::IsTransparencySupported](../Topic/CImage::IsTransparencySupported.md)|アプリケーションが透明なビットマップをサポートし、Windows 2000 以降のコンパイルするかどうか。|  
|[CImage::Load](../Topic/CImage::Load.md)|指定したファイルからイメージを読み込みます。|  
|[CImage::LoadFromResource](../Topic/CImage::LoadFromResource.md)|指定したリソースからイメージを読み込みます。|  
|[CImage::MaskBlt](../Topic/CImage::MaskBlt.md)|指定したマスクとラスター オペレーションを使用して元とコピー先のビットマップの色データを結合します。|  
|[CImage::PlgBlt](../Topic/CImage::PlgBlt.md)|コピー先のデバイス コンテキストの平行四辺形に元のデバイス コンテキストで四角形のビット ブロック転送を行います。|  
|[CImage::ReleaseDC](../Topic/CImage::ReleaseDC.md)|[CImage::GetDC](../Topic/CImage::GetDC.md)で取得されたデバイス コンテキストを解放します。|  
|[CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md)|GDI\+ によって使用されるリソースを解放します。  `CImage` のグローバル オブジェクトで作成されたリソースを解放するために呼び出す必要があります。|  
|[CImage::Save](../Topic/CImage::Save.md)|イメージをとして型指定されます。  **上書き保存** は、イメージのオプションを指定することはできません。|  
|[CImage::SetColorTable](../Topic/CImage::SetColorTable.md)|DIB セクションのカラー テーブルのエントリの範囲の赤、緑、青\) の RGB カラー値を設定します。|  
|[CImage::SetPixel](../Topic/CImage::SetPixel.md)|指定した色に指定した座標をピクセル単位で設定します。|  
|[CImage::SetPixelIndexed](../Topic/CImage::SetPixelIndexed.md)|パレットで色の指定したインデックスに指定した座標をピクセル単位で設定します。|  
|[CImage::SetPixelRGB](../Topic/CImage::SetPixelRGB.md)|\(RGB\) で指定された赤、緑、青の値に指定した座標をピクセル単位で設定します。|  
|[CImage::SetTransparentColor](../Topic/CImage::SetTransparentColor.md)|色のインデックスを扱う透過的として設定します。  パレットの 1 色のみ透過的になります。|  
|[CImage::StretchBlt](../Topic/CImage::StretchBlt.md)|ビットマップを描画先の四角形に合うように伸縮または圧縮する先の四角形と元の四角形からビットマップを必要に応じてコピーします。|  
|[CImage::TransparentBlt](../Topic/CImage::TransparentBlt.md)|元のデバイス コンテキストからこの現在のデバイス コンテキストに透明な色のビットマップをコピーします。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CImage::operator HBITMAP](../Topic/CImage::operator%20HBITMAP.md)|オブジェクトにアタッチされている `CImage` のウィンドウ ハンドルを返します。|  
  
## 解説  
 `CImage` は、デバイスに依存しないビットマップの \(DIB\) のセクションまたは、ではないビットマップを使用します; ただし、DIB セクションだけで [&#91;作成&#93;](../Topic/CImage::Create.md) か [CImage::Load](../Topic/CImage::Load.md) を使用できます。  [&#91;アタッチ&#93;](../Topic/CImage::Attach.md)を使用して `CImage` のオブジェクトに、DIB セクションのビットマップをアタッチできますが、その場合は DIB セクションのビットマップだけをサポートする `CImage` の次のメソッドを使用できません:  
  
-   [GetBits](../Topic/CImage::GetBits.md)  
  
-   [GetColorTable](../Topic/CImage::GetColorTable.md)  
  
-   [GetMaxColorTableEntries](../Topic/CImage::GetMaxColorTableEntries.md)  
  
-   [GetPitch](../Topic/CImage::GetPitch.md)  
  
-   [GetPixelAddress](../Topic/CImage::GetPixelAddress.md)  
  
-   [IsIndexed](../Topic/CImage::IsIndexed.md)  
  
-   [SetColorTable](../Topic/CImage::SetColorTable.md)  
  
 アタッチされているビットマップの DIB セクションであるかどうかを確認するには、[IsDibSection](../Topic/CImage::IsDIBSection.md)**.**を呼び出します。  
  
> [!NOTE]
>  Visual Studio .NET 2003 の**Note** は、このクラス `CImage` のオブジェクトの数を作成しておきます。  カウントが 0 に移動するたびに GDI\+ によって使用されるリソースを解放するための関数 [GdiplusShutdown](_gdiplus_func_gdiplusshutdown_) は自動的に呼び出されます。  これは、DLL によって直接または間接的に作成される `CImage` のオブジェクトは、常に適切に破棄されていること、および **GdiplusShutdown** が `DllMain`から呼び出されていないことを確認します。  
  
> [!NOTE]
>  DLL の `CImage` のグローバル オブジェクトはお勧めしません。  DLL で `CImage` のグローバル オブジェクトを使用する必要がある場合、明示的に GDI\+ が使用していたリソースを解放する呼び出し [CImage::ReleaseGDIPlus](../Topic/CImage::ReleaseGDIPlus.md)。  
  
 `CImage` は、新しい [CDC](../Topic/CDC%20Class.md)に選択することはできません。  `CImage`、イメージの独自の **HDC** を作成します。  `HBITMAP` が 1 **HDC** に一度に選択できないため `CImage` に関連付けられている `HBITMAP` は別の **HDC**に選択することはできません。  `CDC`が必要な場合は、**HDC** を `CImage` から取得し、[CDC::FromHandle](../Topic/CDC::FromHandle.md)にそれを付けます。  
  
## 使用例  
 [!code-cpp[NVC_ATLMFC_Utilities#70](../../atl-mfc-shared/codesnippet/CPP/cimage-class_1.cpp)]  
  
 MFC プロジェクトに `CImage` を使用すると、プロジェクトのメンバー関数が [CBitmap](../../mfc/reference/cbitmap-class.md) のオブジェクトへのポインターを要求されます。  このような関数に `CImage` を、[CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)、使用 [CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md)を使用して、の `CImage``HBITMAP`を渡し、返された `CBitmap*`を使用する場合は。  
  
## 使用例  
 [!code-cpp[NVC_ATLMFC_Utilities#71](../../atl-mfc-shared/codesnippet/CPP/cimage-class_2.cpp)]  
  
 `CImage`によって、DIB セクションの実際のビットにアクセスできます。  `CImage` のオブジェクトを使用して、どこでも、以前に Win32 HBITMAP かの DIB セクションを使用します。  
  
> [!NOTE]
>  `CImage` の次のメソッドの使用に関する制限事項があります:  
  
|メソッド|制限|  
|----------|--------|  
|[PlgBlt](../Topic/CImage::PlgBlt.md)|Windows NT 4.0 以降だけを使用します。  \/98 Windows 95 以降で実行されるアプリケーションに Per Request Impersonation Does Not Work|  
|[MaskBlt](../Topic/CImage::MaskBlt.md)|Windows NT 4.0 以降だけを使用します。  \/98 Windows 95 以降で実行されるアプリケーションに Per Request Impersonation Does Not Work|  
|[AlphaBlend](../Topic/CImage::AlphaBlend.md)|Windows 2000、Windows 98 以降のシステムのみを使用します。|  
|[TransparentBlt](../Topic/CImage::TransparentBlt.md)|Windows 2000、Windows 98 以降のシステムのみを使用します。|  
|[&#91;描画&#93;](../Topic/CImage::Draw.md)|Windows 2000、Windows 98 以降のシステムのみの透過性をサポートします。|  
  
 これらのメソッドの制限に関する詳細については [以前のオペレーティング システムに CImage の制限](../../mfc/cimage-limitations-with-earlier-operating-systems.md) を参照してください。  
  
 MFC または ATL の `CImage` を使用できます。  
  
> [!NOTE]
>  `CImage`を使用してプロジェクトを作成すると、`atlimage.h`をインクルードする前に `CString` を定義する必要があります。  プロジェクトが MFC なしでは、ATL を使用している場合は、`atlimage.h`をインクルードする前に `atlstr.h` を含めます。  これは MFC サポートを使用して ATL プロジェクトを使用している場合は、プロジェクトが MFC \(または\)、`atlimage.h`をインクルードする前に `afxstr.h` を含めます。  
>   
>  同様に `atlimpl.cpp`をインクルードする前に、`atlimage.h` を含める必要があります。  これを簡単に実現するには、の `stdafx.h`に `atlimage.h` を含めます。  
  
## 必要条件  
 **Header:** atlimage.h  
  
## 参照  
 [MMXSwarm サンプル](../../top/visual-cpp-samples.md)   
 [SimpleImage サンプル](../../top/visual-cpp-samples.md)   
 [Device\-Independent Bitmaps](http://msdn.microsoft.com/library/windows/desktop/dd183562)   
 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183494)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)