---
title: "-ALLOWISOLATION |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ba0295d73e51e28fbdd953d7d9a3a2ae5131c27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="allowisolation"></a>/ALLOWISOLATION
マニフェスト検索の動作を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 **/ALLOWISOLATION**により、オペレーティング システムはマニフェストの検索と読み込みがします。  
  
 **/ALLOWISOLATION**既定値です。  
  
 **/ALLOWISOLATION:NO**マニフェスト、および原因がない場合に、実行可能ファイルが読み込まれていることを示します[EDITBIN リファレンス](../../build/reference/editbin-reference.md)を設定する、 `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` optional ヘッダーのビット`DllCharacteristics`フィールドです。  
  
 実行可能ファイルの分離が無効の場合、Windows ローダーは、新しく作成されたプロセスに対応するアプリケーション マニフェストの検索を試行しません。 実行可能ファイル自体に、マニフェストがか、名前を持つ場合はマニフェストがある場合でも、新しいプロセスは既定のアクティベーション コンテキストにありません*実行可能ファイル名*。 exe.manifest です。  
  
## <a name="see-also"></a>参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [/ALLOWISOLATION (マニフェスト検索)](../../build/reference/allowisolation-manifest-lookup.md)   
 [マニフェスト ファイルのリファレンス](http://msdn.microsoft.com/library/aa375632.aspx)