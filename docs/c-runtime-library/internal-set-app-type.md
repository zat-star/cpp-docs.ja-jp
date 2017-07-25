---
title: __set_app_type | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __set_app_type
- _set_app_type
apilocation:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __set_app_type
dev_langs:
- C++
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e1b14f0e4cbf4ebfeb02811ee622db6f9eeaab2b
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="setapptype"></a>__set_app_type
現在のアプリケーションの種類を設定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void __set_app_type (  
   int at  
   )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `at`  
 アプリケーションの種類を示す値。 次の値を指定できます。  
  
|値|説明|  
|-----------|-----------------|  
|_UNKNOWN_APP|不明なアプリケーションの種類。|  
|_CONSOLE_APP|コンソール (コマンドライン) アプリケーション。|  
|_GUI_APP|GUI (Windows) アプリケーション。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|__set_app_type|internal.h|
