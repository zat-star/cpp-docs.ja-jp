---
title: "プロジェクト ビルド エラー PRJ0050 | Microsoft Docs"
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
  - "PRJ0050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0050"
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルド エラー PRJ0050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

出力の登録に失敗しました。レジストリを変更するための適切なアクセス許可があるかどうかを確認してください。  
  
 Visual C\+\+ ビルド システムは、ビルドの出力 \(dll または .exe\) を登録できませんでした。  管理者としてログオンし、レジストリを変更する必要があります。  
  
 .dll をビルドしている場合、regsvr32.exe を使用して手動で .dll の登録を試みることができます。この際、ビルドが失敗した理由が表示されます。  
  
 .dll をビルドしていない場合、エラーの原因になったコマンドのビルド ログを確認します。