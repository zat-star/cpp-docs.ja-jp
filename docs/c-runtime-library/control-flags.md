---
title: "制御フラグ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 71e0b1d01e291a1fa48740ccb6389a1b064433b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="control-flags"></a>制御フラグ
Microsoft C ランタイム ライブラリのデバッグ バージョンは次のフラグを使用し、ヒープ割り当てとレポート プロセスを制御します。 詳細については、「[CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。  
  
|フラグ|説明|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|基本のヒープ関数をデバッグ バージョンのそれにマッピングする|  
|[_DEBUG](../c-runtime-library/debug.md)|ランタイム関数のデバッグ バージョンの使用を有効にする|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|デバッグ ヒープ マネージャーの割り当て追跡記録方法を制御する|  
  
 これらのフラグは、/D コマンドライン オプションまたは `#define` ディレクティブで定義できます。 フラグが `#define` で定義されるとき、ルーチン宣言のヘッダー ファイル インクルード ステートメントの前にディレクティブが現れるはずです。  
  
## <a name="see-also"></a>参照  
 [グローバル変数および基本データ型](../c-runtime-library/global-variables-and-standard-types.md)