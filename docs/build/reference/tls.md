---
title: "-TLS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5adf246e343a16abebdc584589e9633b195444ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tls"></a>/TLS
実行可能ファイルから IMAGE_TLS_DIRECTORY 構造を表示します。  
  
## <a name="remarks"></a>コメント  
 /TLS には、TLS 構造体のフィールドだけでなく、TLS のコールバック関数のアドレスが表示されます。  
  
 プログラムにスレッド ローカル ストレージが使用していない場合、そのイメージには、TLS 構造は含まれません。  参照してください[スレッド](../../cpp/thread.md)詳細についてはします。  
  
 IMAGE_TLS_DIRECTORY は、winnt.h で定義されます。  
  
## <a name="see-also"></a>参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)