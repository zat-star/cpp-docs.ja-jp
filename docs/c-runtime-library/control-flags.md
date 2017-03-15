---
title: "制御フラグ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9e8d2030edb3c048ec67ddd5a7b0782d2bbfdd9a
ms.lasthandoff: 02/24/2017

---
# <a name="control-flags"></a>制御フラグ
Microsoft C ランタイム ライブラリのデバッグ バージョンは次のフラグを使用し、ヒープ割り当てとレポート プロセスを制御します。 詳細については、「[CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。  
  
|フラグ|説明|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|基本のヒープ関数をデバッグ バージョンのそれにマッピングする|  
|[_DEBUG](../c-runtime-library/debug.md)|ランタイム関数のデバッグ バージョンの使用を有効にする|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|デバッグ ヒープ マネージャーの割り当て追跡記録方法を制御する|  
  
 これらのフラグは、/D コマンドライン オプションまたは `#define` ディレクティブで定義できます。 フラグが `#define` で定義されるとき、ルーチン宣言のヘッダー ファイル インクルード ステートメントの前にディレクティブが現れるはずです。  
  
## <a name="see-also"></a>関連項目  
 [グローバル変数および基本データ型](../c-runtime-library/global-variables-and-standard-types.md)
