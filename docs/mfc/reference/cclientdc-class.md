---
title: "CClientDC クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC class
- device contexts, client area
- client-area device context
- CDC class, device contexts for client areas
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
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
ms.openlocfilehash: 619bed4d31994bde8464ad710e9f050d6ba0696a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cclientdc-class"></a>CClientDC クラス
Windows 関数の呼び出しを行います[GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)構築時に、 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920)時に破棄します。  
  
## <a name="syntax"></a>構文  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|構築、`CClientDC`オブジェクトに接続されている、`CWnd`です。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND`対象のウィンドウの`CClientDC`は無効です。|  
  
## <a name="remarks"></a>コメント  
 つまり、デバイス コンテキストに関連付けられている、`CClientDC`オブジェクトは、ウィンドウのクライアント領域です。  
  
 詳細については`CClientDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cclientdc"></a>CClientDC::CClientDC  
 構築、`CClientDC`のクライアント領域にアクセスするオブジェクトを[CWnd](../../mfc/reference/cwnd-class.md)指す`pWnd`します。  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 デバイス コンテキスト オブジェクトがアクセス クライアント領域を持つウィンドウです。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、Windows の関数を呼び出します。 [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)します。  
  
 例外 (型の`CResourceException`) 場合にスローされますが、Windows`GetDC`呼び出しは失敗します。 Windows が既に割り当てられているすべての使用可能なデバイス コンテキストの場合は、デバイス コンテキストを使用しないことがあります。 共通のディスプレイ コンテキストでは、Windows の特定の時点で利用可能なの&5; つのアプリケーションが行う競合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&42;](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CClientDC::m_hWnd  
 `HWND`の`CWnd`ポインターの構築に使用される、`CClientDC`オブジェクトです。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hWnd`保護されている変数です。  
  
### <a name="example"></a>例  
  例を参照してください[CClientDC::CClientDC](#cclientdc)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)

