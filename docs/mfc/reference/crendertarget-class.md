---
title: "CRenderTarget クラス | Microsoft Docs"
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
  - "CRenderTarget"
  - "afxrendertarget/CRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRenderTarget クラス"
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRenderTarget クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1RenderTarget のラッパー。  
  
## 構文  
  
```  
class CRenderTarget : public CObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRenderTarget::CRenderTarget](../Topic/CRenderTarget::CRenderTarget.md)|CRenderTarget オブジェクトを構築します。|  
|[CRenderTarget::~CRenderTarget](../Topic/CRenderTarget::~CRenderTarget.md)|デストラクターです。  レンダー ターゲット オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRenderTarget::Attach](../Topic/CRenderTarget::Attach.md)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|  
|[CRenderTarget::BeginDraw](../Topic/CRenderTarget::BeginDraw.md)|このレンダー ターゲットで描画を開始します。|  
|[CRenderTarget::Clear](../Topic/CRenderTarget::Clear.md)|描画領域を指定した色にクリアします。|  
|[CRenderTarget::COLORREF\_TO\_D2DCOLOR](../Topic/CRenderTarget::COLORREF_TO_D2DCOLOR.md)|GDI の色およびアルファ値を D2D1\_COLOR\_F オブジェクトに変換します。|  
|[CRenderTarget::CreateCompatibleRenderTarget](../Topic/CRenderTarget::CreateCompatibleRenderTarget.md)|中間オフスクリーン描画中に使用する、現在のレンダー ターゲットと互換性のある新しいビットマップ レンダー ターゲットを作成します。|  
|[CRenderTarget::Destroy](../Topic/CRenderTarget::Destroy.md)|1 つ以上のリソースを削除します。|  
|[CRenderTarget::Detach](../Topic/CRenderTarget::Detach.md)|レンダー ターゲット インターフェイスをオブジェクトからデタッチします。|  
|[CRenderTarget::DrawBitmap](../Topic/CRenderTarget::DrawBitmap.md)|指定した IDWriteTextLayout オブジェクトで示される書式付きテキストを描画します。|  
|[CRenderTarget::DrawEllipse](../Topic/CRenderTarget::DrawEllipse.md)|指定したストロークのスタイルを使用して、指定した楕円のアウトラインを描画します。|  
|[CRenderTarget::DrawGeometry](../Topic/CRenderTarget::DrawGeometry.md)|指定したストロークのスタイルを使用して、指定したジオメトリのアウトラインを描画します。|  
|[CRenderTarget::DrawGlyphRun](../Topic/CRenderTarget::DrawGlyphRun.md)|指定したグリフを描画します。|  
|[CRenderTarget::DrawLine](../Topic/CRenderTarget::DrawLine.md)|指定したストロークのスタイルを使用して、指定した 2 点の間に直線を描画します。|  
|[CRenderTarget::DrawRectangle](../Topic/CRenderTarget::DrawRectangle.md)|指定した寸法とストロークのスタイルの四角形のアウトラインを描画します。|  
|[CRenderTarget::DrawRoundedRectangle](../Topic/CRenderTarget::DrawRoundedRectangle.md)|指定したストロークのスタイルを使用して、指定した角の丸い四角形のアウトラインを描画します。|  
|[CRenderTarget::DrawText](../Topic/CRenderTarget::DrawText.md)|IDWriteTextFormat オブジェクトによって提供される書式情報を使用して、指定したテキストを描画します。|  
|[CRenderTarget::DrawTextLayout](../Topic/CRenderTarget::DrawTextLayout.md)|指定した IDWriteTextLayout オブジェクトで示される書式付きテキストを描画します。|  
|[CRenderTarget::EndDraw](../Topic/CRenderTarget::EndDraw.md)|レンダー ターゲットで描画操作を終了し、現在のエラー状態および関連付けられているタグを示します。|  
|[CRenderTarget::FillEllipse](../Topic/CRenderTarget::FillEllipse.md)|指定した楕円の内部を塗りつぶします。|  
|[CRenderTarget::FillGeometry](../Topic/CRenderTarget::FillGeometry.md)|指定したジオメトリの内部を塗りつぶします。|  
|[CRenderTarget::FillMesh](../Topic/CRenderTarget::FillMesh.md)|指定したメッシュの内部を塗りつぶします。|  
|[CRenderTarget::FillOpacityMask](../Topic/CRenderTarget::FillOpacityMask.md)|指定したビットマップで示される不透明マスクをブラシに適用し、そのブラシを使用してレンダー ターゲットの領域を塗りつぶします。|  
|[CRenderTarget::FillRectangle](../Topic/CRenderTarget::FillRectangle.md)|指定した四角形の内部を塗りつぶします。|  
|[CRenderTarget::FillRoundedRectangle](../Topic/CRenderTarget::FillRoundedRectangle.md)|指定した角の丸い四角形の内部を塗りつぶします。|  
|[CRenderTarget::Flush](../Topic/CRenderTarget::Flush.md)|保留中のすべての描画コマンドを実行します。|  
|[CRenderTarget::GetAntialiasMode](../Topic/CRenderTarget::GetAntialiasMode.md)|テキスト以外の描画操作の現在のアンチエイリアシング モードを取得します。|  
|[CRenderTarget::GetDpi](../Topic/CRenderTarget::GetDpi.md)|レンダー ターゲットの DPI \(1 インチあたりのドット数\) を返します。|  
|[CRenderTarget::GetMaximumBitmapSize](../Topic/CRenderTarget::GetMaximumBitmapSize.md)|デバイスに依存する単位 \(ピクセル\) で表された、レンダー ターゲットでサポートされるいずれかのビットマップの寸法の最大サイズを取得します。|  
|[CRenderTarget::GetPixelFormat](../Topic/CRenderTarget::GetPixelFormat.md)|レンダー ターゲットのピクセル形式とアルファ モードを取得します。|  
|[CRenderTarget::GetPixelSize](../Topic/CRenderTarget::GetPixelSize.md)|デバイス ピクセルで表されたレンダー ターゲットのサイズを返します。|  
|[CRenderTarget::GetRenderTarget](../Topic/CRenderTarget::GetRenderTarget.md)|ID2D1RenderTarget インターフェイスを返します。|  
|[CRenderTarget::GetSize](../Topic/CRenderTarget::GetSize.md)|デバイスに依存しないピクセルで表されたレンダー ターゲットのサイズを返します。|  
|[CRenderTarget::GetTags](../Topic/CRenderTarget::GetTags.md)|以降の描画操作のラベルを取得します。|  
|[CRenderTarget::GetTextAntialiasMode](../Topic/CRenderTarget::GetTextAntialiasMode.md)|テキストおよびグリフの描画操作の現在のアンチエイリアシング モードを取得します。|  
|[CRenderTarget::GetTextRenderingParams](../Topic/CRenderTarget::GetTextRenderingParams.md)|レンダー ターゲットの現在のテキスト レンダリング オプションを取得します。|  
|[CRenderTarget::GetTransform](../Topic/CRenderTarget::GetTransform.md)|指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。  以降の描画操作はすべて、変換された空間で行われます。|  
|[CRenderTarget::IsSupported](../Topic/CRenderTarget::IsSupported.md)|指定したプロパティがレンダー ターゲットでサポートされているかどうかを示します。|  
|[CRenderTarget::IsValid](../Topic/CRenderTarget::IsValid.md)|リソースの有効性を検証します。|  
|[CRenderTarget::PopAxisAlignedClip](../Topic/CRenderTarget::PopAxisAlignedClip.md)|レンダー ターゲットから最後の軸平行クリップを削除します。  このメソッドが呼び出された後、以降の描画操作にはこのクリップが適用されなくなります。|  
|[CRenderTarget::PopLayer](../Topic/CRenderTarget::PopLayer.md)|PushLayer の最後の呼び出しで指定されたレイヤーに対する、描画操作のリダイレクトを停止します。|  
|[CRenderTarget::PushAxisAlignedClip](../Topic/CRenderTarget::PushAxisAlignedClip.md)|レンダー ターゲットから最後の軸平行クリップを削除します。  このメソッドが呼び出された後、以降の描画操作にはこのクリップが適用されなくなります。|  
|[CRenderTarget::PushLayer](../Topic/CRenderTarget::PushLayer.md)|PopLayer が呼び出されるまでレンダー ターゲットで以降の描画操作をすべて受け取るように、指定したレイヤーをレンダー ターゲットに追加します。|  
|[CRenderTarget::RestoreDrawingState](../Topic/CRenderTarget::RestoreDrawingState.md)|レンダー ターゲットの描画の状態を、指定した ID2D1DrawingStateBlock の状態に設定します。|  
|[CRenderTarget::SaveDrawingState](../Topic/CRenderTarget::SaveDrawingState.md)|現在の描画の状態を、指定した ID2D1DrawingStateBlock に保存します。|  
|[CRenderTarget::SetAntialiasMode](../Topic/CRenderTarget::SetAntialiasMode.md)|レンダー ターゲットのアンチエイリアシング モードを設定します。  アンチエイリアシング モードは、テキストおよびグリフの描画操作を除く、以降のすべての描画操作に適用されます。|  
|[CRenderTarget::SetDpi](../Topic/CRenderTarget::SetDpi.md)|レンダー ターゲットの DPI \(1 インチあたりのドット数\) を設定します。|  
|[CRenderTarget::SetTags](../Topic/CRenderTarget::SetTags.md)|以降の描画操作のラベルを指定します。|  
|[CRenderTarget::SetTextAntialiasMode](../Topic/CRenderTarget::SetTextAntialiasMode.md)|以降のテキストおよびグリフの描画操作に使用するアンチエイリアシング モードを指定します。|  
|[CRenderTarget::SetTextRenderingParams](../Topic/CRenderTarget::SetTextRenderingParams.md)|以降のテキストおよびグリフのすべての描画操作に適用するテキスト レンダリング オプションを指定します。|  
|[CRenderTarget::SetTransform](../Topic/CRenderTarget::SetTransform.md)|オーバーロードされます。  指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。  以降の描画操作はすべて、変換された空間で行われます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRenderTarget::VerifyResource](../Topic/CRenderTarget::VerifyResource.md)|CD2DResource オブジェクトの有効性を検証します。このオブジェクトがまだ存在しない場合は作成します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CRenderTarget::operator ID2D1RenderTarget\*](../Topic/CRenderTarget::operator%20ID2D1RenderTarget*.md)|ID2D1RenderTarget インターフェイスを返します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CRenderTarget::m\_lstResources](../Topic/CRenderTarget::m_lstResources.md)|CD2DResource オブジェクトへのポインターのリスト。|  
|[CRenderTarget::m\_pRenderTarget](../Topic/CRenderTarget::m_pRenderTarget.md)|ID2D1RenderTarget オブジェクトへのポインター。|  
|[CRenderTarget::m\_pTextFormatDefault](../Topic/CRenderTarget::m_pTextFormatDefault.md)|既定のテキスト形式を格納している CD2DTextFormat オブジェクトへのポインター。|  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## 必要条件  
 **ヘッダー:** afxrendertarget.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)