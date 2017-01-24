---
title: "VCPROFILE_PATH | Microsoft Docs"
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
  - "VCPROFILE_PATH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_PATH 環境変数"
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VCPROFILE_PATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.pgc ファイルを作成するディレクトリを指定します。  
  
## 構文  
  
```  
VCPROFILE_PATH=path  
```  
  
#### パラメーター  
 `path`  
 .pgc ファイルを追加するディレクトリ パス。  
  
## 解説  
 既定では、.pgc ファイルはプロファイルされているバイナリと同じディレクトリに作成されます。ただし、バイナリの絶対パスがない場合 \(プロファイルのシナリオをバイナリのビルド先マシンと別のマシンで実行する場合など\) は、`VCPROFILE_PATH` に既存のパスを設定できます。  
  
## 使用例  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## 参照  
 [ガイド付き最適化のプロファイルの環境変数](../../build/reference/environment-variables-for-profile-guided-optimizations.md)