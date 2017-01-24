---
title: "CStockPropImpl クラス | Microsoft Docs"
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
  - "CStockPropImpl"
  - "ATL::CStockPropImpl"
  - "ATL.CStockPropImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [ATL], ストック プロパティ"
  - "CStockPropImpl クラス"
  - "ストック プロパティ, ATL コントロール"
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStockPropImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ストック プロパティ値をサポートするためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T,  
class InterfaceName,   
const IID* piid= &_ATL_IIDOF(InterfaceName),   
const GUID* plibid= &CComModule::m_libid,   
WORD wMajor= 1,  
WORD wMinor= 0,   
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE CStockPropImpl :  
public IDispatchImpl< InterfaceName, piid, plibid, wMajor,  
   wMinor, tihclass>  
```  
  
#### パラメーター  
 `T`  
 コントロールを実装して `CStockPropImpl`から派生するクラス。  
  
 `InterfaceName`  
 ストック プロパティを公開するデュアル インターフェイス。  
  
 `piid`  
 `InterfaceName` の IID へのポインター。  
  
 `plibid`  
 `InterfaceName`の定義を含むタイプ ライブラリの LIBID へのポインター。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョン。  既定値は 1 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョン。  既定値は 0 です。  
  
 `tihclass`  
 `T` の型情報の管理に使用されるクラス。  既定値 `CComTypeInfoHolder` です。  
  
## メンバー  
  
### パブリック メソッド  
  
|||  
|-|-|  
|[get\_Appearance](../Topic/CStockPropImpl::get_Appearance.md)|描画スタイルをコントロール、たとえば、フラットであるか 3D で使用するには、このメソッドを呼び出します。|  
|[get\_AutoSize](../Topic/CStockPropImpl::get_AutoSize.md)|コントロールが他のサイズもでもない示すフラグの状態を取得するときにこのメソッドを呼び出します。|  
|[get\_BackColor](../Topic/CStockPropImpl::get_BackColor.md)|コントロールの背景色を取得するときにこのメソッドを呼び出します。|  
|[get\_BackStyle](../Topic/CStockPropImpl::get_BackStyle.md)|透明または不透明なコントロールの背景スタイルを取得するには、このメソッドを呼び出します。|  
|[get\_BorderColor](../Topic/CStockPropImpl::get_BorderColor.md)|コントロールの境界の色を取得するときにこのメソッドを呼び出します。|  
|[get\_BorderStyle](../Topic/CStockPropImpl::get_BorderStyle.md)|コントロールの境界線スタイルを取得するときにこのメソッドを呼び出します。|  
|[get\_BorderVisible](../Topic/CStockPropImpl::get_BorderVisible.md)|コントロールの境界線が表示されている場合、はない示すフラグの状態を取得するときにこのメソッドを呼び出します。|  
|[get\_BorderWidth](../Topic/CStockPropImpl::get_BorderWidth.md)|コントロールの境界線の幅 \(ピクセル単位\) を取得するときにこのメソッドを呼び出します。|  
|[get\_Caption](../Topic/CStockPropImpl::get_Caption.md)|テキストをオブジェクトのキャプションに指定するには、このメソッドを呼び出します。|  
|[get\_DrawMode](../Topic/CStockPropImpl::get_DrawMode.md)|コントロールの描画モード \(XOR のペンを取得するときにこのメソッドを呼び出す場合、または色を反転させます。|  
|[get\_DrawStyle](../Topic/CStockPropImpl::get_DrawStyle.md)|コントロールの描画スタイル \(たとえば、塗りつぶし、破線のを取得するときにこのメソッドを呼び出すか、ドットを打ちました。|  
|[get\_DrawWidth](../Topic/CStockPropImpl::get_DrawWidth.md)|描画の幅 \(ピクセル単位\) コントロールの描画メソッドによって使用されて取得するときにこのメソッドを呼び出します。|  
|[get\_Enabled](../Topic/CStockPropImpl::get_Enabled.md)|コントロールが有効な場合は示すフラグの状態を取得するときにこのメソッドを呼び出します。|  
|[get\_FillColor](../Topic/CStockPropImpl::get_FillColor.md)|コントロールの塗りつぶしの色を取得するときにこのメソッドを呼び出します。|  
|[get\_FillStyle](../Topic/CStockPropImpl::get_FillStyle.md)|コントロールの塗りつぶしスタイル、たとえば、塗りつぶし、透過的なを取得するときにこのメソッドを呼び出すか、イメージを付けられた|  
|[get\_Font](../Topic/CStockPropImpl::get_Font.md)|コントロールのフォント プロパティへのポインターを取得するときにこのメソッドを呼び出します。|  
|[get\_ForeColor](../Topic/CStockPropImpl::get_ForeColor.md)|コントロールの前景色を取得するときにこのメソッドを呼び出します。|  
|[get\_HWND](../Topic/CStockPropImpl::get_HWND.md)|ウィンドウ ハンドルをコントロールに関連付ける取得するときにこのメソッドを呼び出します。|  
|[get\_MouseIcon](../Topic/CStockPropImpl::get_MouseIcon.md)|マウスがコントロール上にあるときグラフィックス \(アイコン、ビットマップ、メタファイル\) のピクチャ プロパティを表示するには、このメソッドを呼び出します。|  
|[get\_MousePointer](../Topic/CStockPropImpl::get_MousePointer.md)|マウスをコントロール、たとえば、矢印、クロス、または砂時計にあるときに、マウス ポインターの型を表示する取得するときにこのメソッドを呼び出します。|  
|[get\_Picture](../Topic/CStockPropImpl::get_Picture.md)|グラフィックス \(アイコン、ビットマップ、メタファイル\) のピクチャ プロパティへのポインターを要求する場合には、このメソッドを呼び出します。|  
|[get\_ReadyState](../Topic/CStockPropImpl::get_ReadyState.md)|コントロールの準備状態など、読み込みを取得するときにこのメソッドを呼び出すか、読み込んでいました。|  
|[get\_TabStop](../Topic/CStockPropImpl::get_TabStop.md)|コントロールがタブ ストップつまりでないことを示すフラグを取得するときにこのメソッドを呼び出します。|  
|[get\_Text](../Topic/CStockPropImpl::get_Text.md)|コントロールによって表示されるテキストを取得するときにこのメソッドを呼び出します。|  
|[get\_Valid](../Topic/CStockPropImpl::get_Valid.md)|コントロールが有効またはない示すフラグの状態を取得するときにこのメソッドを呼び出します。|  
|[get\_Window](../Topic/CStockPropImpl::get_Window.md)|ウィンドウ ハンドルをコントロールに関連付ける取得するときにこのメソッドを呼び出します。  [CStockPropImpl::get\_HWND](../Topic/CStockPropImpl::get_HWND.md)と同じ。|  
|[put\_Appearance](../Topic/CStockPropImpl::put_Appearance.md)|描画スタイルをコントロール、たとえば、フラットであるか 3D で使用される設定するには、このメソッドを呼び出します。|  
|[put\_AutoSize](../Topic/CStockPropImpl::put_AutoSize.md)|コントロールが他のサイズもでもない示すフラグ値を設定するには、このメソッドを呼び出します。|  
|[put\_BackColor](../Topic/CStockPropImpl::put_BackColor.md)|コントロールの背景色を設定するには、このメソッドを呼び出します。|  
|[put\_BackStyle](../Topic/CStockPropImpl::put_BackStyle.md)|コントロールの背景スタイルを設定するには、このメソッドを呼び出します。|  
|[put\_BorderColor](../Topic/CStockPropImpl::put_BorderColor.md)|コントロールの境界の色を設定するには、このメソッドを呼び出します。|  
|[put\_BorderStyle](../Topic/CStockPropImpl::put_BorderStyle.md)|コントロールの境界線のスタイルを設定するには、このメソッドを呼び出します。|  
|[put\_BorderVisible](../Topic/CStockPropImpl::put_BorderVisible.md)|コントロールの境界線が表示されている場合、はない示すフラグ値を設定するには、このメソッドを呼び出します。|  
|[put\_BorderWidth](../Topic/CStockPropImpl::put_BorderWidth.md)|コントロールの境界線の幅を設定するには、このメソッドを呼び出します。|  
|[put\_Caption](../Topic/CStockPropImpl::put_Caption.md)|コントロールによって表示されるテキストを設定するには、このメソッドを呼び出します。|  
|[put\_DrawMode](../Topic/CStockPropImpl::put_DrawMode.md)|コントロールの描画モード \(XOR のペンを設定するには、このメソッドを呼び出す場合、または色を反転させます。|  
|[put\_DrawStyle](../Topic/CStockPropImpl::put_DrawStyle.md)|コントロールの描画スタイル \(たとえば、塗りつぶし、破線のを設定するには、このメソッドを呼び出すか、ドットを打ちました。|  
|[put\_DrawWidth](../Topic/CStockPropImpl::put_DrawWidth.md)|幅 \(ピクセル単位\) コントロールの描画メソッドによって使用されて設定するには、このメソッドを呼び出します。|  
|[put\_Enabled](../Topic/CStockPropImpl::put_Enabled.md)|コントロールが有効な場合は示すフラグを設定するには、このメソッドを呼び出します。|  
|[put\_FillColor](../Topic/CStockPropImpl::put_FillColor.md)|コントロールの塗りつぶしの色を設定するには、このメソッドを呼び出します。|  
|[put\_FillStyle](../Topic/CStockPropImpl::put_FillStyle.md)|コントロールの塗りつぶしスタイル、たとえば、塗りつぶし、透過的なを設定するには、このメソッドを呼び出すか、イメージを付けられた|  
|[put\_Font](../Topic/CStockPropImpl::put_Font.md)|コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。|  
|[put\_ForeColor](../Topic/CStockPropImpl::put_ForeColor.md)|コントロールの前景色を設定するには、このメソッドを呼び出します。|  
|[put\_HWND](../Topic/CStockPropImpl::put_HWND.md)|このメソッドは E\_FAIL を返します。|  
|[put\_MouseIcon](../Topic/CStockPropImpl::put_MouseIcon.md)|マウスがコントロール上にあるときに表示されるグラフィックス \(アイコン、ビットマップ、メタファイル\) の図のプロパティを設定するには、このメソッドを呼び出します。|  
|[put\_MousePointer](../Topic/CStockPropImpl::put_MousePointer.md)|マウスをコントロール、たとえば、矢印、クロス、または砂時計にあるときに、マウス ポインターの型を表示する設定するには、このメソッドを呼び出します。|  
|[put\_Picture](../Topic/CStockPropImpl::put_Picture.md)|表示されるグラフィックス \(アイコン、ビットマップ、メタファイル\) の図のプロパティを設定するには、このメソッドを呼び出します。|  
|[put\_ReadyState](../Topic/CStockPropImpl::put_ReadyState.md)|コントロールの準備状態などを設定するには、このメソッドを呼び出すと読み込みまたは読み込んでいました。|  
|[put\_TabStop](../Topic/CStockPropImpl::put_TabStop.md)|コントロールがタブ ストップつまりでないことを示すフラグ値を設定するには、このメソッドを呼び出します。|  
|[put\_Text](../Topic/CStockPropImpl::put_Text.md)|コントロールによって表示されるテキストを設定するには、このメソッドを呼び出します。|  
|[put\_Valid](../Topic/CStockPropImpl::put_Valid.md)|コントロールが有効またはない示すフラグを設定するには、このメソッドを呼び出します。|  
|[put\_Window](../Topic/CStockPropImpl::put_Window.md)|E\_FAIL を返すこのメソッドは [CStockPropImpl::put\_HWND](../Topic/CStockPropImpl::put_HWND.md)を呼び出します。|  
|[putref\_Font](../Topic/CStockPropImpl::putref_Font.md)|参照カウントのコントロールのフォント プロパティを設定するには、このメソッドを呼び出します。|  
|[putref\_MouseIcon](../Topic/CStockPropImpl::putref_MouseIcon.md)|マウスがコントロール上にある参照カウントとときに表示されるグラフィックス \(アイコン、ビットマップ、メタファイル\) の図のプロパティを設定するには、このメソッドを呼び出します。|  
|[putref\_Picture](../Topic/CStockPropImpl::putref_Picture.md)|参照カウントが表示されるグラフィックス \(アイコン、ビットマップ、メタファイル\) の図のプロパティを設定するには、このメソッドを呼び出します。|  
  
## 解説  
 `CStockPropImpl` は **put** を提供し、それぞれの **get** のメソッドは、プロパティに格納されます。  これらのメソッドは、どのプロパティが変更されたときに設定またはデータ メンバーを各プロパティに関連付けられているを取得し、コンテナーによって通知し、同期するために必要なコードを提供します。  
  
 Visual C\+\+ では、ウィザードを使用して標準プロパティをサポートします。  コントロールに標準プロパティを追加する方法の詳細については、[ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)を参照してください。  
  
 下位互換性のために、`CStockPropImpl` は、`get_Window` と `get_HWND` と `put_HWND`を呼び出す `put_Window` のメソッドをそれぞれ公開します。  `put_HWND` の既定の実装は `HWND` を読み取り専用プロパティ必要があるため、**E\_FAIL** を返します。  
  
 次のプロパティにも **putref** の実装があります:  
  
-   フォント  
  
-   MouseIcon  
  
-   画像  
  
 同じ 3 種類の標準プロパティには、対応するデータ型またはメンバーが `CComPtr` 代入演算子によって適切なインターフェイスの参照カウントを提供する他のクラスである必要があります。  
  
## 継承階層  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)