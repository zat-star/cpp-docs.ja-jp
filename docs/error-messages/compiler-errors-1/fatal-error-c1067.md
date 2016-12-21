---
title: "致命的なエラー C1067 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1067"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1067"
ms.assetid: e2c94be6-4573-4571-aac9-73d657fe9f96
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1067
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : 型のレコード サイズの制限である 64K を超えました  
  
 このエラーが発生するのは、シンボルの装飾名が 247 文字を超える場合です。このエラーを解決するには、シンボル名を短くします。  
  
 コンパイラは、デバッグ情報を生成するときに、ソース コードに出現した型を定義する型レコードを出力します。たとえば、型レコードには、単純な構造体と関数の引数リストが含まれています。型レコードが大きいリストになることもあります。  
  
 型レコードのサイズは 64 KB に制限されています。64 KB 制限を越えると、このエラーが発生します。  
  
 C1067 は、長い名前のシンボルが多数ある場合、またはクラス、構造体、または共用体のメンバーが多すぎる場合にも発生することがあります。