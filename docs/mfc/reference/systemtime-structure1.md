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
- SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07af222a3d51ff1cc71076d5bbcc3513a3d6cad4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winbase.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

