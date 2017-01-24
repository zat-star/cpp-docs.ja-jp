---
title: "リソース コンパイラ エラー RW2003 | Microsoft Docs"
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
  - "RW2003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW2003"
ms.assetid: 9dc0ba70-6776-4aef-b316-5f1711d8e42e
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラ エラー RW2003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Generation Error  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  **Error: Bitmap file resource\-file is not in 3.00 format**  
  
     Windows Version 2.x 形式のビットマップを Version 3.x のリソース ファイルで使用することはできません。  ビットマップを再描画するか、Version 3.x 形式に変換する必要があります。  
  
2.  **Error: Old DIB in resource\-name.  Pass it through SDKPAINT**  
  
     指定したリソースのデバイスに依存しないビットマップ \(DIB\) には、Windows Version 3.0 形式との互換性がありません。  ビットマップを再描画するか、Version 3.x 形式に変換する必要があります。  
  
3.  **Error: Resource file resource\-name is not in 3.00 format**  
  
     指定したリソースのアイコンまたはカーソルは Windows の以前のバージョンの形式を使用しています。  アイコンまたはカーソルを再描画するか、Version 3.x 形式に変換する必要があります。  
  
4.  **Unknown DIB header format**  
  
     ビットマップのヘッダーが BITMAPCOREHEADER または BITMAPINFOHEADER 構造体ではありません。  
  
5.  **Unable to initialize symbol information**  
  
     このエラーは Visual C\+\+ でだけ発生します。  開いているファイルの数が多すぎる可能性があります。また、Visual C\+\+ がスクリプトのシンボルをインポートするために必要なデータ ファイルを開くこと、またはそのようなデータ ファイルに書き込むことができない場合にも、このエラーが発生することがあります。  Visual C\+\+ は **TMP** 環境変数で指定されたフォルダーにファイルを作成します。環境変数を設定していない場合は、現在のフォルダーにファイルを作成します。  
  
6.  **Unable to save symbol information**  
  
     このエラーは Visual C\+\+ でだけ発生します。  開いているファイルの数が多すぎる可能性があります。また、Visual C\+\+ がスクリプトのシンボルをインポートするために必要なデータ ファイルを開くこと、またはそのようなデータ ファイルに書き込むことができない場合にも、このエラーが発生することがあります。  Visual C\+\+ は **TMP** 環境変数で指定されたフォルダーにあるファイルを使用します。環境変数を設定していない場合は、現在のフォルダーにあるファイルを使用します。  
  
7.  **Bitmap file resource file is not in 2.03 format**  
  
     ビットマップに Version 2.03 より前の形式が使用されています。  このビットマップは、変換するか、Version 3.00 以降の形式で再描画する必要があります。  
  
8.  **Resource too large**  
  
     Windows Version 3.1 では、リソースの大きさの制限は約 65000 バイトです。  この制限を越えると、Visual C\+\+ またはコマンド ラインのリソース コンパイラでコンパイルできません。  この制限は、カーソル、アイコン、ビットマップ、またはその他のファイル ベースのリソースには適用されません。  
  
9. **Resource file is not in 3.00 format**  
  
     カーソルまたはアイコンが Version 3.0 以前の形式を使用しています。  リソースを変換するか、Version 3.00 以降の形式で再描画する必要があります。  
  
10. **Unable to open temporary file**  
  
     一時的なファイルを開くことができません。  考えられる原因は、フォルダーへの書き込み許可がないか、フォルダーが存在していないことです。  リソース コンパイラまたは Visual C\+\+ では、環境変数 **TMP** で設定されているフォルダーが使用されます。環境変数を設定していない場合は、現在のフォルダーが使用されます。