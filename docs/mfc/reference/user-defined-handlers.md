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
- ON_REGISTERED_MESSAGE macro
- ON_MESSAGE macro
- user-defined handlers
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
caps.latest.revision: 10
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f0fc367bc19f0db23efddfc69fdeac519185ff0c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="user-defined-handlers"></a>ユーザー定義のハンドラー
関数プロトタイプに対応するマップ エントリを次に示します。  
  
|マップ エントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM、LPARAM) です。|  
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM、LPARAM) です。|  
|ON_THREAD_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM、LPARAM) です。|  
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM、LPARAM) です。|  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)   
 [Wm _ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)


