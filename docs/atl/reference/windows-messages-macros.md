---
title: "Windows メッセージに関するマクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: be814c0a2ade7df8f7a4d6863627e79efe0a48bc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="windows-messages-macros"></a>Windows メッセージに関するマクロ
このマクロは、ウィンドウ メッセージを転送します。  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|処理するための別のウィンドウのウィンドウで受信メッセージの転送に使用します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>WM_FORWARDMSG  
 このマクロでは、別のウィンドウで処理するためにウィンドウが受信したメッセージを転送します。  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、メッセージが処理された場合は&0; 以外の場合。  
  
### <a name="remarks"></a>コメント  
 使用`WM_FORWARDMSG`を処理するための別のウィンドウのウィンドウで受信メッセージを転送します。 LPARAM と WPARAM のパラメーターは、次のように使用されます。  
  
|パラメーター|使用方法|  
|---------------|-----------|  
|WPARAM|ユーザーによって定義されたデータ|  
|LPARAM|ポインター、`MSG`メッセージに関する情報を格納する構造体|  
  
### <a name="example"></a>例  
 次の例で`m_hWndOther`このメッセージを受信するその他のウィンドウを表します。  
  
 [!code-cpp[NVC_ATL_Windowing #&137;](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロ](../../atl/reference/atl-macros.md)

