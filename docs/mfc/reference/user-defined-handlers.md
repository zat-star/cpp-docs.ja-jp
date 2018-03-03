---
title: "ユーザー定義のハンドラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.handlers
dev_langs:
- C++
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b276ea546d5940b78090a99f36c953afe62a67fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-handlers"></a>ユーザー定義のハンドラー
関数プロトタイプに対応するマップ エントリを次に示します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM、LPARAM) です。|  
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM、LPARAM) です。|  
|ON_THREAD_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM、LPARAM) です。|  
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM、LPARAM) です。|  
  
## <a name="see-also"></a>参照  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [WM_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)

