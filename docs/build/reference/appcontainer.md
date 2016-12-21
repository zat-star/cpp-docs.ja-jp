---
title: "/APPCONTAINER | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/APPCONTAINER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/APPCONTAINER editbin オプション"
  - "APPCONTAINER editbin オプション"
  - "-APPCONTAINER editbin オプション"
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /APPCONTAINER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリ コンテナーで実行する必要のある実行可能ファイルをマークします。たとえば、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] またはユニバーサル Windows アプリをマークします。  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## 解説  
 **\/APPCONTAINER** のオプション セットがある実行可能ファイルは、Windows 8 で導入されたプロセス分離環境であるアプリケーション コンテナーでのみ実行できます。[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] およびユニバーサル Windows アプリの場合は、このオプションを設定する必要があります。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)   
 [ユニバーサル Windows アプリとは?](http://go.microsoft.com/fwlink/p/?LinkID=522074)