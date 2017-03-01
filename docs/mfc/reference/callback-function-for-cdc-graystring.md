---
title: "Cdc::graystring 用コールバック関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::GrayString
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::GrayString
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
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
ms.openlocfilehash: 3ce3afefae9618420a8a97b27994c33604745677
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcgraystring"></a>CDC::GrayString 用コールバック関数
*OutputFunc*アプリケーションによって提供されるコールバック関数名のプレース ホルダーです。  
  
## <a name="syntax"></a>構文  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
#### <a name="parameters"></a>パラメーター  
 `hDC`  
 少なくともビットマップ メモリ デバイス コンテキストを識別する幅と高さで指定された`nWidth`と`nHeight`に`GrayString`します。  
  
 `lpData`  
 描画される文字列を指します。  
  
 `nCount`  
 出力する文字数を指定します。  
  
## <a name="return-value"></a>戻り値  
 コールバック関数の戻り値である必要があります**TRUE**成功した場合は以外の場合は**FALSE**します。  
  
## <a name="remarks"></a>コメント  
 コールバック関数 (*OutputFunc*) 座標 (0,&0;) を基準としたイメージを描画する必要がなく (*x*、 *y*)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Cdc::graystring](../../mfc/reference/cdc-class.md#graystring)


