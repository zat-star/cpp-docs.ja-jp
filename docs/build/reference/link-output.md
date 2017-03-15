---
title: "LINK からの出力 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ilk ファイル"
  - "DLL [C++], リンカー出力としての"
  - "実行可能ファイル [C++], リンカー出力としての"
  - "ファイル [C++], LINK"
  - "ILK ファイル"
  - "インポート ライブラリ [C++], 作成"
  - "LINK ツール [C++], マップ ファイル"
  - "LINK ツール [C++], 出力"
  - "リンカー [C++], 出力ファイル"
  - "マップ ファイル [C++]"
  - "マップ ファイル [C++], LINK 出力"
  - "出力ファイル [C++], リンカー"
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# LINK からの出力
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンクからの出力には、.exe ファイル、DLL、マップ ファイル、およびメッセージがあります。  
  
##  <a name="_core_output_files"></a> 出力ファイル  
 LINK からの既定の出力ファイルは、.exe ファイルです。  [\/DLL](../../build/reference/dll-build-a-dll.md) オプションを指定すると、.dll ファイルが出力されます。  出力ファイル名は、[\/OUT \(出力ファイル名\)](../../build/reference/out-output-file-name.md) オプションで指定できます。  
  
 インクリメンタル モードでリンクを行うと、以降のインクリメンタル ビルドで使うステータス情報が取り込まれた .ilk ファイルが作成されます。  .ilk ファイルについては、「[リンカー入力としての .ilk ファイル](../../build/reference/dot-ilk-files-as-linker-input.md)」を参照してください。  インクリメンタル リンクについては、[\/INCREMENTAL \(インクリメンタル リンクを行う\)](../../build/reference/incremental-link-incrementally.md) オプションに関するトピックを参照してください。  
  
 LINK によって作成されるプログラムが、シンボルをエクスポートするプログラム \(通常は DLL ファイル\) の場合は、.lib ファイルも作成されます。ただし、ビルドに .exp ファイルを使った場合は作成されません。  インポート ライブラリのファイル名は [\/IMPLIB](../Topic/-IMPLIB%20\(Name%20Import%20Library\).md) オプションで指定できます。  
  
 [\/MAP \(マップ ファイルの生成\)](../../build/reference/map-generate-mapfile.md) オプションを指定すると、マップ ファイルが作成されます。  
  
 [\/DEBUG \(デバッグ情報の生成\)](../../build/reference/debug-generate-debug-info.md) オプションを指定すると、プログラムのデバッグ情報が取り込まれた PDB が作成されます。  
  
##  <a name="_core_other_output"></a> その他の出力  
 コマンド ラインでオプションを指定せずに「`link`」とだけ入力すると、LINK オプションの使い方をまとめた情報が出力されます。  
  
 [\/NOLOGO \(開始メッセージを表示しない\)](../../build/reference/nologo-suppress-startup-banner-linker.md) オプションを指定していないと、著作権メッセージとバージョン メッセージが表示され、コマンド ファイルからの入力がエコーします。  
  
 [\/VERBOSE \(詳細情報の出力\)](../../build/reference/verbose-print-progress-messages.md) オプションを使うと、ビルドに関する補足情報が出力されます。  
  
 エラー メッセージと警告メッセージは、LNK*nnnn* という形式で出力されます。  このエラー プリフィックスと番号の範囲は、LIB、DUMPBIN、および EDITBIN でも使用されます。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)