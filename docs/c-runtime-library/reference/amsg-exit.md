---
title: _amsg_exit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _amsg_exit
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _amsg_exit
dev_langs:
- C++
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b9029cbcfaa3853638a5b46e2c3ee1cb56622cb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="amsgexit"></a>_amsg_exit
指定したランタイム エラー メッセージを出力した後に、エラー コード 255 でアプリケーションを終了します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `rterrnum`  
 システム定義のランタイム エラー メッセージの ID 番号。  
  
## <a name="remarks"></a>コメント  
 この関数は、ランタイム エラー メッセージをコンソール アプリケーションの **stderr** に出力するか、Windows アプリケーションのメッセージ ボックスにメッセージを表示します。 デバッグ モードでは、終了する前にデバッガーを起動できます。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|_amsg_exit|internal.h|