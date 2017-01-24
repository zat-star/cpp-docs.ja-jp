---
title: "LIBRARY | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LIBRARY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIBRARY ステートメント (.def ファイル)"
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LIBRARY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DLL を作成するよう LINK に指示します。  ビルドで .exp ファイルが使用されていない場合は、同時にインポート ライブラリも作成されます。  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## 解説  
 引数 *library* には、DLL の名前を指定します。  [\/OUT](../../build/reference/out-output-file-name.md) リンカー オプションを使って、DLL の出力名を指定することもできます。  
  
 引数 BASE\=*address* には、オペレーティング システムが DLL ファイルを読み込むベース アドレスを指定します。  既定では、DLL ファイルの読み込み先は 0x10000000 になりますが、この引数でこのアドレスを変更できます。  ベース アドレスの詳細については、[\/BASE](../../build/reference/base-base-address.md) オプションの説明を参照してください。  
  
 DLL をビルドするときは、必ず [\/DLL](../../build/reference/dll-build-a-dll.md) リンカー オプションを使用してください。  
  
## 参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)