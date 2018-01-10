---
title: "NotifyHandler |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: NotifyHandler
dev_langs: C++
helpviewer_keywords: NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11f078e6e47aa6c392de79d9811df8738ce09ed9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="notifyhandler"></a>NotifyHandler
3 番目のパラメーターで識別される関数の名前、`NOTIFY_HANDLER`メッセージ マップ マクロです。  
  
## <a name="syntax"></a>構文  
  
```  
 
    LRESULT 
    NotifyHandler 
 (
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>パラメーター  
 `idCtrl`  
 メッセージを送信するコントロールの識別子。  
  
 *pnmh*  
 アドレス、 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514)通知コードおよびその他の情報を含む構造体。 このパラメーターを持つより大きな構造体をポイントするいくつかの通知メッセージについて、 **NMHDR**構造はその最初のメンバーとして。  
  
 `bHandled`  
 メッセージ マップ セット`bHandled`に**TRUE**する前に*NotifyHandler*と呼びます。 場合*NotifyHandler* 、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示すメッセージがさらに処理を必要があります。  
  
## <a name="return-value"></a>戻り値  
 メッセージの処理の結果。 正常終了した場合は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 メッセージ マップでこのメッセージ ハンドラーを使用しての例は、次を参照してください。 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler))。  
  
## <a name="see-also"></a>参照  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

