---
title: "CWindowDC クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWindowDC
- No header/CWindowDC
- No header/CWindowDC::CWindowDC
- No header/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- device contexts, window
- screen output classes
- CWindowDC class
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
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
ms.openlocfilehash: 8a941e1b6f8a398706498ec5d1ce1bfc9156f115
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowdc-class"></a>CWindowDC クラス
`CDC`の派生クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|`CWindowDC` オブジェクトを構築します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|`HWND` の割り当て先である `CWindowDC`。|  
  
## <a name="remarks"></a>コメント  
 Windows 関数を呼び出す[GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)構築時に、 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx)破棄時です。 つまり、`CWindowDC`の全画面領域にアクセスする、 [CWnd](../../mfc/reference/cwnd-class.md) (クライアントおよび非クライアント領域の両方)。  
  
 使用する方法について`CWindowDC`を参照してください[デバイス コンテキスト](../../mfc/device-contexts.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>要件  
 ヘッダー: afxwin.h  
  
##  <a name="cwindowdc"></a>CWindowDC::CWindowDC  
 構築、`CWindowDC`の全画面領域 (クライアントと非クライアントの両方) にアクセスするオブジェクトを`CWnd`によって指されるオブジェクト`pWnd`します。  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 デバイス コンテキスト オブジェクトがアクセス クライアント領域を持つウィンドウです。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、Windows の関数を呼び出します。 [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947)します。  
  
 例外 (型の`CResourceException`) 場合にスローされますが、Windows`GetWindowDC`呼び出しは失敗します。 Windows が既に割り当てられているすべての使用可能なデバイス コンテキストの場合は、デバイス コンテキストを使用しないことがあります。 共通のディスプレイ コンテキストでは、Windows の特定の時点で利用可能なの&5; つのアプリケーションが行う競合します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&188;](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CWindowDC::m_hWnd  
 `HWND`の`CWnd`ポインターを使用して作成、`CWindowDC`オブジェクトです。  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>コメント  
 `m_hWnd`保護されている型の変数は、`HWND`です。  
  
### <a name="example"></a>例  
  例を参照してください[CWindowDC::CWindowDC](#cwindowdc)します。  
  
## <a name="see-also"></a>関連項目  
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)

