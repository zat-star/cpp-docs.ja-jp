---
title: "リンカ ツール エラー LNK1123 | Microsoft Docs"
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
  - "LNK1123"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1123"
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカ ツール エラー LNK1123
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COFF への変換中に障害が発生しました : ファイルが無効であるか、または壊れています。  
  
 入力ファイルは、COFF \(Common Object File Format\) 形式である必要があります。  入力ファイルが COFF でない場合、リンカーによって 32 ビット OMF オブジェクトが COFF に自動変換されるか、リソース ファイルを変換するための CVTRES.EXE が実行されます。  このメッセージは、リンカーがファイルを変換できなかったことを示します。  これは、Visual Studio、Windows Development Kit、または .NET Framework の別のインストールから CVTRES.EXE の非互換バージョンを使用している場合にも発生します。  
  
> [!NOTE]
>  旧バージョンの Visual Studio を実行している場合は、自動変換がサポートされない場合があります。  
  
### この問題を解決するには、次のいずれかを行います。  
  
-   Visual Studio の該当するバージョン用のすべての更新プログラムとサービス パックを適用します。  これは、Visual Studio 2010年には特に重要です。  
  
-   インクリメンタル リンクを無効にしてビルドしてみます。  メニュー バーで **\[プロジェクト\]**、**\[プロパティ\]** の順に選択します。  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]**、**\[全般\]** の順に展開します。  **\[インクリメンタル リンクを有効にする\]** の値を **\[いいえ\]** に変更します。  
  
-   PATH 環境変数で最初に見つかる CVTRES.EXE のバージョンが、プロジェクトで使用されるビルド ツールのバージョン \(プラットフォーム ツールセットのバージョン\) と一致することを確認します。  
  
-   \[埋め込みマニフェスト\] のオプションをオフにしてください。  メニュー バーで **\[プロジェクト\]**、**\[プロパティ\]** の順に選択します。  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]**、**\[マニフェスト ツール\]**、**\[入力と出力\]** の順に展開します。  **\[埋め込みマニフェスト\]** の値を **\[いいえ\]** に変更します。  
  
-   ファイルの種類が有効であることを確認します。  たとえば OMF オブジェクトが 16 ビットではなく 32 ビットであることを確認します。  詳細については、「[リンカー入力としての .obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)」および「[Microsoft PE および COFF の仕様](http://go.microsoft.com/fwlink/p/?LinkId=93292)」を参照してください。  
  
-   ファイルが破損していないことを確認してください。  必要に応じて再構築します。  
  
## 参照  
 [リンカー入力としての .obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)   
 [EDITBIN リファレンス](../Topic/EDITBIN%20Reference.md)   
 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)