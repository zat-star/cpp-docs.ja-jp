---
title: "ATL_DRAWINFO 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::ATL_DRAWINFO"
  - "ATL_DRAWINFO"
  - "ATL.ATL_DRAWINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL_DRAWINFO 構造体"
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# ATL_DRAWINFO 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリンター、メタファイル、または ActiveX コントロールなど、さまざまなターゲットに表示に使用される情報が含まれます。  
  
## 構文  
  
```  
  
      struct ATL_DRAWINFO{  
   UINT cbSize;  
   DWORD dwDrawAspect;  
   LONG lindex;  
   DVTARGETDEVICE* ptd;  
   HDC hicTargetDev;  
   HDC hdcDraw;  
   LPCRECTL prcBounds;  
   LPCRECTL prcWBounds;  
   BOOL bOptimize;  
   BOOL bZoomed;  
   BOOL bRectInHimetric;  
   SIZEL ZoomNum;  
   SIZEL ZoomDen;  
};  
```  
  
## メンバー  
 `cbSize`  
 バイトの構造体のサイズ。  
  
 **dwDrawAspect**  
 ターゲットが表現する方法を指定します。  表示内容は、アイコン、スケーリング、表示または印刷されたドキュメントを含めることができます。  使用できる値の一覧については、[DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) と [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644)を参照してください。  
  
 **lindex**  
 描画操作の対象となる複数の部分。  この解釈は **dwDrawAspect** のメンバーの値によって異なります。  
  
 **ptd**  
 指定された要素によって描画の最適化を有効にする [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) の構造体へのポインター。  最適化したサポートがインターフェイスを描画このメンバーをサポートすることによって新しいオブジェクトとコンテナー注意してください。  最適化されたコンテナー サポートしないこのメンバーに、古いオブジェクトは、インターフェイスを描画 **null** を必ず指定します。  
  
 **hicTargetDev**  
 ターゲット デバイスの情報コンテキストは、オブジェクトがデバイスのメトリックを配置できるポイントして、デバイスの機能をテストします **ptd** によって。  **ptd** が **null**場合、オブジェクトは **hicTargetDev** メンバーの値を無視します。  
  
 **hdcDraw**  
 描画するデバイス コンテキスト。  ウィンドウなしのオブジェクト、含むウィンドウのクライアント座標に一致する論理座標のモードをマップする **hdcDraw** のメンバーは `MM_TEXT` にあります。  また、デバイス コンテキストは、通常、`WM_PAINT` のメッセージを渡されたポインターと同じ状態になります。  
  
 **prcBounds**  
 指定する [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) の構造体へのポインター オブジェクトをで **hdcDraw** で四角形を描画します。  このメンバーは、オブジェクトの配置と伸縮を制御します。  このメンバーは、埋め込み先でアクティブ ウィンドウなしのオブジェクトを描画 **null** 必要があります。  そのほかのすべての状況では、**null** 値は有効にし、`E_INVALIDARG` のエラー コードを生成する必要があります。  コンテナーがウィンドウなしのオブジェクトに**null** に以外の値を渡すと、オブジェクトは指定されたデバイス コンテキストと四角形に必要な側面を表示する必要があります。  コンテナーがウィンドウなしのオブジェクトからこれをオブジェクトの 2 番目の、非活動的な概要を表示するか、オブジェクトを印刷するように要求できます。  
  
 **prcWBounds**  
 **hdcDraw** がメタファイルのデバイス コンテキスト \( [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) を参照\) である場合は、**RECTL** の構造体へ基になるメタファイルに外接する四角形を指定するポインターです。  四角形構造体は、ウィンドウの範囲とウィンドウの原点が含まれます。  これらの値は、メタファイルを描画するために役立ちます。  **prcBounds** に示す四角形は **prcWBounds** のこの四角形内に含まれています; これらは同じ座標空間にあります。  
  
 **bOptimize**  
 コントロールの描画を最適化する場合は 0 以外を返します。  描画を最適化した場合、デバイス コンテキストの状態が自動的に終了するレンダリングのと同じになります。  
  
 **bZoomed**  
 ターゲットにズームの要因がゼロ以外の場合は 0。  ズームの要素は **ZoomNum**に格納されます。  
  
 **bRectInHimetric**  
 **prcBounds** のサイズが **HIMETRIC**にある場合、ゼロ以外の場合は 0。  
  
 **ZoomNum**  
 オブジェクトを表示する四角形の幅と高さ。  ターゲットの x 軸 \(現在の範囲にオブジェクトの自然なサイズの比率\) に沿ってズームの要素は **ZoomDen.cx**の値によって **ZoomNum.cx** の値分割します。  y 軸に沿ってズーム率は同様です。  
  
 **ZoomDen**  
 ターゲットの実際の幅と高さ。  
  
## 解説  
 この構造体の一般的な用途は、ターゲット オブジェクトのレンダリング時に情報の検索です。  たとえば、[CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)のオーバーロードの中の `ATL_DRAWINFO` の値を取得できます。  
  
 この構造体は、ターゲット デバイスのオブジェクトの外観を表示するために使用する適切な情報を格納します。  表示される情報は画面、プリンター、または、メタファイルへの描画に使用できます。  
  
## 必要条件  
 **ヘッダー :** atlctl.h  
  
## 参照  
 [構造体](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)