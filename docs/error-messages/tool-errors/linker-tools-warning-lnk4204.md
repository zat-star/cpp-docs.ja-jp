---
title: "リンカー ツールの警告 LNK4204 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4204"
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# リンカー ツールの警告 LNK4204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' に参照するモジュールのデバッグ情報がありません。デバッグ情報を無視してオブジェクトをリンクします。  
  
 .pdb ファイルのシグネチャにエラーがあります。  リンカーは、デバッグ情報なしで引き続きオブジェクトをリンクします。  [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションを使用して、オブジェクト ファイルを再コンパイルする必要があります。  
  
 LNK4204 が発生する原因として、ライブラリ内の一部のオブジェクトが、既に存在しないファイルを参照していることが考えられます。  たとえば、ソリューションをビルドし直す際、オブジェクト ファイルが削除されているために、コンパイル エラーでリビルドに失敗した場合などに発生します。  この場合は、**\/Z7** または **\/Fd** を使用してコンパイルを実行し、ライブラリごとに単一のファイルを参照する \(つまり既定の .pdb ファイルを参照しない\) ようにオブジェクトを更新します。詳細については、「[\/Fd \(プログラム データベース ファイル名\)](../../build/reference/fd-program-database-file-name.md)」を参照してください。.pdb ファイルが、ソース管理システムで更新されるたびにライブラリに保存されることを確認してください。