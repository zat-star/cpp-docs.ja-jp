---
title: "致命的なエラー C1905 | Microsoft Docs"
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
  - "C1905"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1905"
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1905
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フロント エンドとバック エンドに互換性がありません \(同じプロセッサを対象としなければなりません\)。  
  
 このエラーが発生するのは、あるプロセッサ \(x86、ARM、または [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]\) を対象とするコンパイラのフロントエンド \(C1.dll\) によって .obj ファイルが生成され、別のプロセッサを対象とするバックエンド \(C2.dll\) によってそのファイルが読み取られる場合です。  
  
 この問題を解決するには、一致するフロントエンドとバックエンドを使用しているか確認します。  これは、Visual Studio に作成されたプロジェクトの既定値です。  プロジェクト ファイルを編集してコンパイラ ツールへの異なるパスを使用した場合に、このエラーが表示されることがあります。  コンパイラ ツールのパスを特に設定していない場合は、Visual Studio のインストールが破損していると、このエラーが発生することがあります。  たとえば、コンパイラの .dll ファイルを 1 つの場所から別の場所にコピーした場合です。  Windows のコントロール パネルの **\[プログラムと機能\]** を使用して修復するか、または Visual Studio を再インストールします。