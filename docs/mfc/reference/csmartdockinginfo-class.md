---
title: "CSmartDockingInfo クラス | Microsoft Docs"
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
  - "CSmartDockingInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmartDockingInfo クラス"
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSmartDockingInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スマート ドッキング マーカーの外観を定義します。  
  
## 構文  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CSmartDockingInfo::CSmartDockingInfo`|既定のコンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSmartDockingInfo::CopyTo](../Topic/CSmartDockingInfo::CopyTo.md)|現在のスマート ドッキング情報のパラメーターを、指定された [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) オブジェクトにコピーします。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CSmartDockingInfo::m\_bUseThemeColorInShading](../Topic/CSmartDockingInfo::m_bUseThemeColorInShading.md)|フレームワークがスマート ドッキング マーカーを表示するときに現在のテーマの色を使用するかどうかを指定します。|  
|[CSmartDockingInfo::m\_clrBaseBackground](../Topic/CSmartDockingInfo::m_clrBaseBackground.md)|スマート ドッキング マーカーの基本背景色を指定します。|  
|[CSmartDockingInfo::m\_clrToneDest](../Topic/CSmartDockingInfo::m_clrToneDest.md)|スマート ドッキング マーカー ビットマップの `m_clrToneSrc` を置き換える色を指定します。|  
|[CSmartDockingInfo::m\_clrToneSrc](../Topic/CSmartDockingInfo::m_clrToneSrc.md)|スマート ドッキング マーカー ビットマップの色を指定します。|  
|[CSmartDockingInfo::m\_clrTransparent](../Topic/CSmartDockingInfo::m_clrTransparent.md)|スマート ドッキング マーカー ビットマップが透明な場合の色を指定します。|  
|[CSmartDockingInfo::m\_nCentralGroupOffset](../Topic/CSmartDockingInfo::m_nCentralGroupOffset.md)|中央のグループを示す四角形の境界を基点とする、スマート ドッキング マーカーの中央のグループのオフセットを指定します。|  
|[CSmartDockingInfo::m\_sizeTotal](../Topic/CSmartDockingInfo::m_sizeTotal.md)|グループ内にあるすべてのスマート ドッキング マーカーの合計サイズを指定します。|  
|[CSmartDockingInfo::m\_uiMarkerBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerBmpResID.md)|フレームワークが、強調表示されていないスマート ドッキング マーカーに使用するビットマップのリソース ID を定義します。|  
|[CSmartDockingInfo::m\_uiMarkerLightBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerLightBmpResID.md)|フレームワークが、強調表示されているスマート ドッキング マーカーに使用するビットマップのリソース ID を定義します。|  
  
## 解説  
 フレームワークは、スマート ドッキング マーカーを内部処理します。  次の図は、標準のスマート ドッキング マーカーを示しています。  
  
 ![スマート ドッキングの標準マーカー](../../mfc/reference/media/nextsdmarkers.png "nextSDmarkers")  
  
 この図で、左側のイメージは、タブへのドッキングが有効になっていない中央のグループのスマート ドッキング マーカーを示しています。  中央のイメージは、右端のスマート ドッキング マーカーを示しています。  右側のイメージは、タブへのドッキングが有効になっている中央のグループのスマート ドッキング マーカーを示しています。  中央のグループのスマート ドッキング マーカーには、メイン ビットマップと 5 つのスマート ドッキング マーカー ビットマップがあります。  
  
 スマート ドッキング マーカーの次のパラメーターをカスタマイズできます。  
  
-   色  たとえば、図中のマーカーの青い色をユーザー定義の色に変えることができます。  
  
-   透明色。  
  
-   外接する四角形の境界線を基点とする、中央のグループ内のスマート ドッキング マーカーのオフセット。  
  
-   中央のグループを表すメイン ビットマップ。  
  
-   通常のスマート ドッキング マーカーおよび強調表示されたスマート ドッキング マーカーを表すビットマップ。  
  
 次の図は、カスタマイズされたスマート ドッキング マーカーの例を示しています。  
  
 ![スマート ドッキングのカスタム マーカー](../Image/nextSDmarkersCustom.png "nextSDmarkersCustom")  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## 必要条件  
 **ヘッダー :** afxDockingManager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CObject クラス](../Topic/CObject%20Class.md)