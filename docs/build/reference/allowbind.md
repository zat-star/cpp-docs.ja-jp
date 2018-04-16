---
title: "-ALLOWBIND |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- ALLOWBIND editbin option
- /ALLOWBIND editbin option
- -ALLOWBIND editbin option
ms.assetid: eaadbb8c-4339-4281-9a75-3a1ce2352ff8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4cbd5c619b0a9e146adb9a8ec9117f59e01b89d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="allowbind"></a>/ALLOWBIND
DLL をバインドできるかどうかを指定します。  
  
```  
  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 **/ALLOWBIND**オプションは、ビットを示す Bind.exe にバインドする、イメージが許可されている DLL のヘッダーを設定します。 バインディングは、読み込みも高速、ローダーが再配置して、参照される各 DLL のアドレスのフィックス アップを実行する必要があるないときにイメージを許可できます。 デジタル署名されている場合にバインドする DLL は好ましくありません-バインドには、署名が無効になります。 バインドも何も起こりませんアドレス space layout randomization (機能) が有効な場合、イメージを使用して**/DYNAMICBASE** ASLR をサポートする Windows のバージョンにします。  
  
 使用して**/ALLOWBIND:NO**を Bind.exe が DLL をバインドするを防ぐためにします。  
  
 詳細については、次を参照してください。、 [/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)リンカー オプション。  
  
## <a name="see-also"></a>参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)