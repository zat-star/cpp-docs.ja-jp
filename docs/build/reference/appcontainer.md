---
title: "-APPCONTAINER |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /APPCONTAINER
dev_langs: C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 19e926cbfd1fc58e04c8370825dd83eacff05dfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="appcontainer"></a>/APPCONTAINER
アプリ コンテナーで実行する必要のある実行可能ファイルをマークします。たとえば、 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] またはユニバーサル Windows アプリをマークします。  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 **/APPCONTAINER** のオプション セットがある実行可能ファイルは、Windows 8 で導入されたプロセス分離環境であるアプリケーション コンテナーでのみ実行できます。 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] およびユニバーサル Windows アプリの場合は、このオプションを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [ユニバーサル Windows アプリとは何ですか。](http://go.microsoft.com/fwlink/p/?LinkID=522074)