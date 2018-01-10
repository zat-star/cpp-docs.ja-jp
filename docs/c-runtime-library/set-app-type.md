---
title: _set_app_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_app_type
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
dev_langs: C++
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adfd7344b01360df6af3ccf7a153eda3451d2482
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setapptype"></a>_set_app_type
アプリがコンソール アプリと GUI アプリのどちらであるかを CRT に知らせるためにスタートアップ時に使用する内部関数です。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    ); 
```  
  
## <a name="parameters"></a>パラメーター  
 `appType`  
 アプリケーションの種類を示す値。 次の値を指定できます。  
  
|[値]|説明|  
|----------------|-----------------|  
|_crt_unknown_app|不明なアプリケーションの種類。|  
|_crt_console_app|コンソール (コマンドライン) アプリケーション。|  
|_crt_gui_app|GUI (Windows) アプリケーション。|  
  
## <a name="remarks"></a>コメント  
 通常は、この関数を呼び出す必要はありません。 この関数は、アプリ内での `main` の呼び出し前に実行される C のランタイム スタートアップ コードに含まれています。
 
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|_set_app_type|process.h|

