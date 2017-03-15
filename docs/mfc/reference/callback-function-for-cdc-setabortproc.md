---
title: "Cdc::setabortproc 用コールバック関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::SetAbortProc
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::SetAbortProc
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1ba16ea60d8b18abd1962ded2da7e11ff2ef09a1
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcsetabortproc"></a>CDC::SetAbortProc 用コールバック関数
名前*AbortFunc*はアプリケーションによって提供される関数名のプレース ホルダーです。  
  
## <a name="syntax"></a>構文  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
#### <a name="parameters"></a>パラメーター  
 *hPr*  
 デバイス コンテキストを識別します。  
  
 `code`  
 エラーが発生したかどうかを指定します。 エラーが発生していない場合は 0 になります。 **させることでより**プリント マネージャーがディスク領域が不足が現在、多くのディスク領域は、アプリケーションが待機する場合は、使用可能になる場合。 場合`code`は**させることでより**アプリケーションは、印刷ジョブを中断する必要はありません。 そうでない場合に呼び出すことによって、印刷マネージャーを生成する必要があります、 **PeekMessage**または**GetMessage** Windows の機能です。  
  
## <a name="return-value"></a>戻り値  
 中止ハンドラー関数の戻り値は、印刷ジョブは、続行する場合は 0 以外および 0 が取り消された場合です。  
  
## <a name="remarks"></a>コメント  
 」の「解説」セクションの説明に従って実際名前をエクスポートする必要があります[cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Cdc::setabortproc](../../mfc/reference/cdc-class.md#setabortproc)


