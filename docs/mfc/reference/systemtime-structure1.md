---
title: "SYSTEMTIME Structure1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
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
ms.openlocfilehash: 298b2673a3eb05525683f8269fcd415d5be1c80a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
`SYSTEMTIME` 構造体は、月、日、年、曜日、時間、分、秒、およびミリ秒の各メンバーを使用して日付と時刻を表します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _SYSTEMTIME {  
    WORD wYear;  
    WORD wMonth;  
    WORD wDayOfWeek;  
    WORD wDay;  
    WORD wHour;  
    WORD wMinute;  
    WORD wSecond;  
    WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *wYear*  
 現在の年です。  
  
 *wMonth*  
 現在の月です。1 月は 1 です。  
  
 *wDayOfWeek*  
 現在の曜日です。日曜日 は 0、月曜日 は 1 などのように指定します。  
  
 *wDay*  
 月の現在の日付です。  
  
 *wHour*  
 現在の時刻 (時間) です。  
  
 *wMinute*  
 現在の時刻 (分) です。  
  
 *wSecond*  
 現在の時刻 (秒) です。  
  
 *wMilliseconds*  
 現在の時刻 (ミリ秒) です。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#39;](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winbase.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)


