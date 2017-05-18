---
title: "CPaintDC クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- OnPaint handler
- WM_PAINT message
- CPaintDC class
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b781db7d4a6676e6fc6ad5df7553b9c9a0154ab9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cpaintdc-class"></a>CPaintDC クラス
デバイス コンテキスト クラスから派生[CDC](../../mfc/reference/cdc-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|構築、`CPaintDC`を指定した接続されている[CWnd](../../mfc/reference/cwnd-class.md)します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|含む、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)クライアント領域を描画するために使用します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|`HWND`先である`CPaintDC`オブジェクトがアタッチされています。|  
  
## <a name="remarks"></a>コメント  
 実行、 [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)構築時に、 [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint)破棄時です。  
  
 A`CPaintDC`オブジェクトに応答する場合にのみ使用できます、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージで通常、`OnPaint`メッセージ ハンドラーのメンバー関数。  
  
 使用する方法について`CPaintDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cpaintdc"></a>CPaintDC::CPaintDC  
 構築、`CPaintDC`オブジェクト、描画、するため、アプリケーション ウィンドウを準備し、保管、 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)構造体、[塗りつぶす対象となる](#m_ps)メンバー変数です。  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 指す、`CWnd`オブジェクトを`CPaintDC`オブジェクトが属しています。  
  
### <a name="remarks"></a>コメント  
 例外 (型の`CResourceException`) 場合にスローされますが、Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)呼び出しは失敗します。 Windows が既に割り当てられているすべての使用可能なデバイス コンテキストの場合は、デバイス コンテキストを使用しないことがあります。 共通のディスプレイ コンテキストでは、Windows の特定の時点で利用可能なの&5; つのアプリケーションが行う競合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&97;](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CPaintDC::m_hWnd  
 `HWND`先である`CPaintDC`オブジェクトがアタッチされています。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hWnd`保護されている型の変数は、`HWND`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&98;](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>CPaintDC::m_ps  
 `m_ps`型のパブリック メンバー変数[PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)します。  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>コメント  
 `PAINTSTRUCT`に渡される、記入を[CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)します。  
  
 `PAINTSTRUCT`アプリケーションが関連付けられているウィンドウのクライアント領域の描画に使用する情報を含む、`CPaintDC`オブジェクトです。  
  
 使ってデバイス コンテキスト ハンドルにアクセスできることに注意してください、`PAINTSTRUCT`です。 ただしを使って直接ハンドルをアクセスすることができます、`m_hDC`メンバー変数を`CPaintDC`から継承`CDC`します。  
  
### <a name="example"></a>例  
  例を参照してください[CPaintDC::m_hWnd](#m_hwnd)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




