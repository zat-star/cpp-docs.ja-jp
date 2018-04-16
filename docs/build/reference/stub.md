---
title: "スタブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58430f8211f8859b65103b53d1f98a173c4635ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stub"></a>STUB
仮想デバイス ドライバー (VxD) を構築するモジュール定義ファイルで使用されているときにすることができます (WINNT で定義されている IMAGE_DOS_HEADER 構造体を含むファイル名を指定します。H) をクリックし、既定のヘッダーではなく、仮想デバイス ドライバー (VxD) で使用します。  
  
```  
STUB:filename  
```  
  
## <a name="remarks"></a>コメント  
 同等の方法を指定する*filename*では、 [/stub](../../build/reference/stub-ms-dos-stub-file-name.md)リンカー オプション。  
  
 スタブは VxD を構築するときにのみ、モジュール定義ファイルで有効です。  
  
## <a name="see-also"></a>参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)