---
title: "Cdc::enumobjects 用コールバック関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::EnumObjects
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::EnumObjects
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: e4b24b5f5333d5514b9fdf69d204bca5d7947d7a
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcenumobjects"></a>CDC::EnumObjects 用コールバック関数
*ObjectFunc*名は、アプリケーションによって提供される関数名のプレース ホルダーです。  
  
## <a name="syntax"></a>構文  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
#### <a name="parameters"></a>パラメーター  
 *lpszLogObject*  
 指す、 [LOGPEN](../../mfc/reference/logpen-structure.md)または[LOGBRUSH](../../mfc/reference/logbrush-structure.md)オブジェクトの論理属性に関する情報を格納するデータ構造です。  
  
 `lpData`  
 アプリケーションによって提供されるデータへのポインターが渡される、`EnumObjects`関数です。  
  
## <a name="return-value"></a>戻り値  
 コールバック関数の結果、`int`です。 この戻り値の値は、ユーザー定義です。 コールバック関数は 0 を返した場合`EnumObjects`早期の列挙を停止します。  
  
## <a name="remarks"></a>コメント  
 実際の名前をエクスポートする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Cdc::enumobjects](../../mfc/reference/cdc-class.md#enumobjects)


