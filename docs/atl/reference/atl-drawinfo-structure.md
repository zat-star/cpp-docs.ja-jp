---
title: "ATL_DRAWINFO 構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: bc124de97acf85d6e706605afb55b0747a327ade
ms.lasthandoff: 02/24/2017

---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO 構造体
プリンター、メタファイル、または ActiveX コントロールなどのさまざまなターゲットへのレンダリングに使用される情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```
struct ATL_DRAWINFO {
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
  
## <a name="members"></a>メンバー  
 `cbSize`  
 バイト単位で、構造体のサイズ。  
  
 **dwDrawAspect**  
 ターゲットが表示される方法を指定します。 表現には、コンテンツ、アイコン、縮小表示または印刷したドキュメントを含めることができます。 使用可能な値の一覧は、次を参照してください。[型](http://msdn.microsoft.com/library/windows/desktop/ms690318)と[DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644)します。  
  
 **lindex**  
 描画操作の対象は、ターゲットの部分です。 その解釈は、値によって、 **dwDrawAspect**メンバーです。  
  
 **ptd**  
 ポインター、 [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)指定されたアスペクトに応じて描画の最適化を使用する構造体。 新しいオブジェクトおよび最適化された描画インターフェイスをサポートするコンテナーが同様に、このメンバーをサポートすることに注意してください。 古いオブジェクトおよびコンテナーを常に最適化された描画インターフェイスをサポートしない指定**NULL**このメンバーにします。  
  
 **hicTargetDev**  
 ターゲット デバイスの情報コンテキストが指す**ptd**元となるオブジェクトはデバイス メトリックを抽出し、デバイスの機能をテストします。 場合**ptd**は**NULL**、オブジェクトの値を無視する、 **hicTargetDev**メンバーです。  
  
 **hdcDraw**  
 描画を行うデバイス コンテキスト。 ウィンドウなしのオブジェクト、 **hdcDraw**内のメンバーは、`MM_TEXT`マッピング モードの論理座標が格納先ウィンドウのクライアント座標に一致するとします。 さらに、デバイス コンテキストが通常と同じ状態にする必要があります、`WM_PAINT`メッセージです。  
  
 **prcBounds**  
 ポインター、 [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907)に四角形を指定する構造体**hdcDraw**オブジェクトを描画する必要があります。 このメンバーは、移動と、オブジェクトの拡大を制御します。 このメンバーを指定する必要があります**NULL**ウィンドウなしのインプレース アクティブなオブジェクトを描画します。 その他のすべての状況で**NULL**有効な値ではないと、結果である、`E_INVALIDARG`エラー コード。 コンテナーを渡す以外の場合**NULL**ウィンドウなしのオブジェクトはオブジェクトに値が、指定したデバイス コンテキストおよび四角形に要求された外観を表示する必要があります。 コンテナーは、オブジェクトの&2; 番目の非アクティブなビューをレンダリングするか、オブジェクトを印刷するウィンドウなしのオブジェクトからこれを要求できます。  
  
 **prcWBounds**  
 場合**hdcDraw**メタファイル デバイス コンテキストは、(を参照してください[調べるため](http://msdn.microsoft.com/library/windows/desktop/dd144877)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)])、これへのポインター、 **RECTL**基になるメタファイル内の外接する四角形を指定する構造体。 四角形の構造には、ウィンドウのエクステントとウィンドウの原点が含まれています。 これらの値はメタファイルを描画するために便利です。 示された四角形**prcBounds**内で入れ子になって**prcWBounds**領域の四角形が同じ座標空間。  
  
 **bOptimize**  
 コントロールの描画の最適化、それ以外の場合 0 場合 0 以外の値。 描画を最適化すると、デバイス コンテキストの状態は自動的に回復が完了すると表示されます。  
  
 **bZoomed**  
 以外の場合は、ターゲットがある 0 のそれ以外の場合、ズームの倍率。 ズームの倍率に格納されている**ZoomNum**します。  
  
 **bRectInHimetric**  
 0 以外の値の大きさ**prcBounds**に**HIMETRIC**、それ以外の場合に 0 です。  
  
 **ZoomNum**  
 幅と、オブジェクトの描画先の四角形の高さ。 ターゲットの x 軸 (現在の大きさに対するオブジェクトの自然なサイズの比率) に倍率の値は、 **ZoomNum.cx**の値で除算した**ZoomDen.cx**します。 Y 軸方向の倍率は、同様の方法で実現されます。  
  
 **ZoomDen**  
 実際の幅とターゲットの高さ。  
  
## <a name="remarks"></a>コメント  
 この構造体の一般的な使用方法は、ターゲット オブジェクトの表示中に情報の取得になります。 たとえばから値を取得できません`ATL_DRAWINFO`のオーバー ロード内[CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced)します。  
  
 この構造体は、対象デバイスのオブジェクトの外観を表示するために使用する関連の情報を格納します。 提供された情報は、画面、プリンター、またはメタファイルの描画に使用できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
## <a name="see-also"></a>関連項目  
 [構造体](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)






