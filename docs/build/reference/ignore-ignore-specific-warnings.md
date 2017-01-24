---
title: "/IGNORE (特定の警告を無視する) | Microsoft Docs"
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
  - "/ignore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNORE リンカー オプション"
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IGNORE (特定の警告を無視する)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNORE:warning[,warning]  
```  
  
## パラメーター  
 `warning`  
 抑制するリンカー警告の番号 \(範囲は 4000 ～ 4999\)。  
  
## 解説  
 既定では、LINK ではすべての警告が報告されます。  リンカーで特定の警告番号が抑制されるようにするには、**\/IGNORE:**`warning` を指定します。  複数の警告を無視するには、警告番号をコンマで区切ります。  
  
 リンカーで無視できない警告がいくつかあります。  次の表に、**\/IGNORE** によって抑制されない警告の一覧を示します。  
  
|リンカー警告||  
|------------|-|  
|LNK4017|`keyword` ステートメントはターゲット プラットフォームでサポートされていません。無視しました。|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|オプション '`option`' は無効です。無視されます。|  
|LNK4062|'`option`' は対象コンピューター '`architecture`' と互換性がありません。オプションは無視されます。|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"`option1`" は "`option2`"の指定によって無視されます。|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|エントリポイント '`function`' は '`number`' バイトの引数を持つ \_\_stdcall ではありません。イメージは動作しない可能性があります。|  
|LNK4088|\/FORCE オプションによってイメージが生成されています。イメージは動作しない可能性があります。|  
|[LNK4105](../Topic/Linker%20Tools%20Warning%20LNK4105.md)|オプション '`option`' に引数が指定されていません。オプションを無視します。|  
|LNK4203|プログラム データベース '`filename`' の読み込み中にエラーが発生しました。デバッグ情報を無視してオブジェクトをリンクします。|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|''`filename`' に参照するモジュールのデバッグ情報がありません。デバッグ情報を無視してオブジェクトをリンクします。|  
|[LNK4205](../Topic/Linker%20Tools%20Warning%20LNK4205.md)|''`filename`' に参照するモジュールの現在のデバッグ情報がありません。デバッグ情報を無視してオブジェクトをリンクします。|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|プリコンパイル済みの型情報が見つかりません。'`filename`' はリンクしていないか、上書きされています。|  
|LNK4207|''`filename`' は \/Yc \/Yu \/Z7 をコンパイルしました。PDB を作成できませんでした。\/Zi を用いて再コンパイルしてください。デバッグ情報を無視してオブジェクトをリンクします。|  
|LNK4208|'`filename`' 内の PDB 形式に互換性がありません。削除して再度ビルドしてください。デバッグ情報を無視してオブジェクトをリンクします。|  
|LNK4209|デバッグ情報が壊れています。モジュールを再コンパイルしてください。デバッグ情報を無視してオブジェクトをリンクします。|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` はサポートされていません。無視されます。|  
|LNK4228|'`option`' DLL に対して無効です。無視します。|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|無効なディレクティブ \/`directive` が見つかりました。無視します。|  
  
 一般的に、無視できないリンカー警告は、修正する必要がある、ビルドの失敗、コマンド ラインのエラーまたは構成エラーを表します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーで、**\[コマンド ライン\]** プロパティ ページを選択します。  
  
3.  **\[その他のオプション\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。