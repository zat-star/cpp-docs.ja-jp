---
title: "/BIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/bind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BIND editbin オプション"
  - "BIND editbin オプション"
  - "-BIND editbin オプション"
  - "開始ポイント"
  - "開始ポイント, アドレス"
  - "インポート アドレス テーブル"
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /BIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BIND[:PATH=path]  
```  
  
## 解説  
 このオプションでは、実行可能ファイルまたは DLL のインポート アドレス テーブルのエントリ ポイントのアドレスを設定します。  このオプションを使うと、プログラムの読み込み時間を短縮できます。  
  
 EDITBIN コマンド ラインの *files* 引数では、プログラムの実行可能ファイルと DLL を指定します。  \/BIND オプションの引数 *path* \(省略可能\) では、指定したファイルで使う DLL の場所を指定します。  複数のフォルダーを指定する場合は、フォルダーをそれぞれセミコロン \(;\) で区切ります。  パスを指定しないと、環境変数 PATH で指定されたフォルダーが検索されます。  パスを指定すると、環境変数 PATH は無視されます。  
  
 既定では、プログラムのローダーがプログラムを読み込むときに、エントリ ポイントのアドレスを設定します。  このプロセスにかかる時間は、DLL の数と、プログラム内で参照されるエントリ ポイントの数によって異なります。  プログラムが \/BIND オプションで変更されていて、実行可能ファイルと DLL のベース アドレスが既に読み込まれている DLL と矛盾しない場合は、オペレーティング システム側でこのアドレスを設定する必要はありません。  ファイルのベース アドレスが不正であると、オペレーティング システムによってプログラムの DLL が再配置され、エントリ ポイントのアドレスが再計算されます。したがって、プログラムの読み込み時間が長くなります。  
  
## 参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)