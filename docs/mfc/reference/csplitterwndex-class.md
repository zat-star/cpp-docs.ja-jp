---
title: "CSplitterWndEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWndEx
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: 24
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 08b26bc2321485181941dbaaa9a903de9a401ef8
ms.lasthandoff: 02/24/2017

---
# <a name="csplitterwndex-class"></a>CSplitterWndEx クラス



カスタマイズされた分割ウィンドウを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|既定のコンストラクター|  
|`CSplitterWndEx::~CSplitterWndEx`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|分割ウィンドウを描画するためにフレームワークによって呼び出されます。 (上書き[CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter))。|  
  
## <a name="remarks"></a>コメント  
 オーバーライド、`OnDrawSplitter`された分割ウィンドウのグラフィック要素の外観をカスタマイズする方法です。  
  
 `CSplitterWndEx`と共に使用するクラス、 [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder)、 [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)、および[OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground)メソッドで、ビジュアル マネージャーによって実装されます。 宣言を置き換えるには、アプリケーションで分割ウィンドウを描画するビジュアル マネージャー、`CSplitterWnd`クラス、`CSplitterWndEx`クラスです。 フレーム ウィンドウのアプリケーションでは、分割ウィンドウ クラスは、mainfrm.h に配置されている CMainFrame クラスで宣言されています。 例については、次を参照してください。、`OutlookDemo`サンプル、サンプル ディレクトリにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>要件  
 **ヘッダー:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 分割ウィンドウを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。 このパラメーターは場合`NULL`フレームワークは、アクティブなウィンドウを再描画します。  
  
 [入力] `nType`  
 いずれか、`CSplitterWnd::ESplitType`を描画する分割ウィンドウ要素を指定する列挙値。 有効な値は`splitBox`、 `splitBar`、 `splitIntersection`、および`splitBorder`です。  
  
 [入力] `rect`  
 ディメンションと、指定された分割ウィンドウ要素を描画する場所を指定する外接する四角形。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../hierarchy-chart.md)   
 [クラス](mfc-classes.md)   
 [CSplitterWnd クラス](csplitterwnd-class.md)   
 [CMFCVisualManager クラス](cmfcvisualmanager-class.md)
